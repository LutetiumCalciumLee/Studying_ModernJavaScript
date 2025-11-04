## Context and Custom Hooks


### Hook Usage Rules

React hooks must follow strict calling conventions:

- Hooks must be called at the **top level** of function components only
- They must be called in the **same order** every time the component renders
- **Never call hooks inside conditions, loops, or nested functions**

Violating these rules causes unpredictable behavior since React tracks hooks by their call order, not by identity.

### Custom Hooks

**Custom hooks** are reusable functions that encapsulate state management and side effects logic. They allow developers to extract complex component logic into shareable packages.

Naming convention: Custom hooks must start with the `use` prefix (e.g., `useFetchData`, `useWindowSize`, `useToggle`).

#### Example 1: useToggle Hook

The useToggle hook encapsulates toggling functionality (open/close, show/hide) that appears in multiple components. Without it, the toggle logic gets duplicated:

**Problem (Code Duplication):**

```javascript
// ModalButton.js
function ModalButton() {
  const [isOpen, setIsOpen] = useState(false);
  const toggle = () => setIsOpen(prev => !prev);
  // ...
}

// DropdownMenu.js
function DropdownMenu() {
  const [isExpanded, setIsExpanded] = useState(false);
  const toggle = () => setIsExpanded(prev => !prev);
  // ...
}
```

**Solution (Custom Hook):**

```javascript
// useToggle.js
const useToggle = (initialValue = false) => {
  const [value, setValue] = useState(initialValue);
  const toggle = () => setValue(prev => !prev);
  return [value, toggle];
};
```

Both components now simply call `const [isOpen, toggleModal] = useToggle(false)`, eliminating duplication and simplifying maintenance.

#### Example 2: useWindowSize Hook

This hook encapsulates **window resize event subscription**. It manages:

1. Window width and height state
2. Event listener registration on component mount
3. Event listener cleanup to prevent memory leaks

```javascript
const useWindowSize = () => {
  const [windowSize, setWindowSize] = useState({
    width: window.innerWidth,
    height: window.innerHeight,
  });

  useEffect(() => {
    const handleResize = () => {
      setWindowSize({
        width: window.innerWidth,
        height: window.innerHeight,
      });
    };
    
    window.addEventListener('resize', handleResize);
    
    return () => {
      window.removeEventListener('resize', handleResize); // Cleanup
    };
  }, []);

  return windowSize;
};
```

This hook enables responsive design. Components can conditionally render based on screen size:

```javascript
function MobileWarning() {
  const { width } = useWindowSize();
  const isMobile = width < 768;
  
  return (
    <div>
      {isMobile ? (
        <p>Mobile environment!</p>
      ) : (
        <p>Desktop environment.</p>
      )}
    </div>
  );
}
```

### Context API: Solving Props Drilling

**Props drilling** occurs when data passes through many intermediate components that don't use it, only to reach deeply nested components. This bloats code and hurts maintainability.

**Example of Props Drilling:**

```javascript
function App() {
  return <Toolbar theme="dark" />;
}

function Toolbar(props) {
  return <ThemedButton theme={props.theme} />; // Just passing through
}

function ThemedButton(props) {
  return <Button theme={props.theme} />; // Just passing through
}

function Button(props) {
  return <button style={{ color: props.theme === 'dark' ? 'white' : 'black' }}>;
}
```

The `theme` prop unnecessarily passes through `Toolbar` and `ThemedButton`.

### Context Solution

**Context** provides a centralized storage system where any component can access data without prop passing. It consists of three parts:

#### 1. Create Context

```javascript
import { createContext } from 'react';
export const ThemeContext = createContext('light'); // Default value
```

#### 2. Provider (Data Supplier)

The Provider wraps components and supplies the context value:

```javascript
function ContextApp() {
  const [theme, setTheme] = useState('light');

  return (
    <ThemeContext.Provider value={{ theme, setTheme }}>
      <Button /> {/* Button can now access theme without props */}
    </ThemeContext.Provider>
  );
}
```

#### 3. Consumer (Data Getter)

Components access context data using the `useContext` hook:

```javascript
function Button() {
  const { theme, setTheme } = useContext(ThemeContext);
  
  const toggleTheme = () => {
    setTheme(theme === 'light' ? 'dark' : 'light');
  };

  return (
    <button onClick={toggleTheme}>
      Theme: {theme.toUpperCase()}
    </button>
  );
}
```

### Custom Hook for Context (Best Practice)

Wrapping `useContext` in a custom hook improves safety and usability:

```javascript
export const useTheme = () => {
  const context = useContext(ThemeContext);
  
  if (context === undefined) {
    throw new Error('useTheme must be used within a ThemeProvider');
  }
  
  return context;
};
```

Components then simply call `const { theme, setTheme } = useTheme()`, eliminating the need to import the context object directly.

### Common Context Use Cases

Context works best for **global, infrequently-changing** data like:

- Theme settings (dark/light mode)
- User authentication (logged-in user, permissions)
- Language settings
- Application-wide configuration

### Practical Example: Theme and Font Size Manager

The document includes a practice project combining Context and Custom Hooks to build a settings application with:

- **SettingsContext**: Manages global theme and font size state
- **useSettings Hook**: Custom hook for easy context access
- **Header Component**: Contains theme toggle and font size controls
- **Content Component**: Applies theme and font size styling
- **App Component**: Acts as the Provider

