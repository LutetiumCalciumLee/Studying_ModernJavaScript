## JSX (JavaScript + XML)

JSX is a syntax extension for JavaScript used in React to describe what the UI should look like. It allows you to write HTML-like code, making it intuitive.

### Key JSX Syntax Features

*   **Single Root Element**: All JSX elements must be wrapped in a single parent element.
    ```jsx
    // Incorrect example
    // return (
    //   <h1>Hello</h1>
    //   <h2>World</h2>
    // );

    // Correct example
    return (
      <div>
        <h1>Hello</h1>
        <h2>World</h2>
      </div>
    );
    ```
*   **Using JavaScript Expressions**: You can embed JavaScript expressions, such as variables or function results, directly into JSX by wrapping them in curly braces `{}`.
    ```jsx
    const name = "React";
    return (
      <h1>Hello, {name}!</h1>
    );
    ```
*   **Differences from HTML Attributes**: You must use `className` instead of `class` and `htmlFor` instead of `for`.
    ```jsx
    <div className="App">
      <label htmlFor="input">Name:</label>
      <input id="input" />
    </div>
    ```
*   **Comments**: Comments within JSX are written as `{/* comment content */}`.

### Applying Styles

1.  **Inline Styles**: Styles are applied to the `style` attribute as a JavaScript object. Property names use camelCase.
    ```jsx
    <h1 style={{ backgroundColor: "yellow", color: "red" }}>Hello, React!</h1>
    ```
2.  **External CSS Files**: You can import a CSS file and apply styles using the `className` attribute.

### Conditional Rendering

This is used to display different UI based on conditions. In JSX, this is typically handled with the ternary operator and logical operators (`&&`, `||`) .

*   **Ternary Operator**: `condition ? UI_to_show_if_true : UI_to_show_if_false`
    ```jsx
    const isLoggedIn = true;
    return (
      <div>
        {isLoggedIn ? <p>Welcome!</p> : <p>Please log in.</p>}
      </div>
    );
    ```
*   **AND (&&) Operator**: Renders a specific UI element only if the condition is `true`.
    ```jsx
    const messages = ['msg1', 'msg2'];
    return (
      <div>
        {messages.length > 0 && <h2>You have {messages.length} unread messages.</h2>}
      </div>
    );
    ```
*   **OR (||) Operator**: Useful for rendering fallback content, such as showing a default value when data is missing .
    ```jsx
    const name = undefined;
    return (
      <h2>Hello, {name || 'Guest'}!</h2>
    );
    ```

## Components

Components are independent, reusable building blocks for the UI in React. Using components improves code reusability and simplifies maintenance.

### Component Features

*   **Reusability**: Common UI elements like buttons or input fields can be created as components and reused.
*   **Independence (Encapsulation)**: Logic and styles are managed separately for each component, making maintenance easier.
*   **Composability**: Smaller components can be combined to create larger, more complex components.

### Types of Components

| Category | Functional Component | Class Component |
| :--- | :--- | :--- |
| **Description** | Written as a JavaScript function, this is the recommended approach in modern React . | An ES6 class that extends `React.Component`, commonly used in older versions of React . |
| **Features** | Accepts `props` as an argument and returns JSX. Can manage state and lifecycle with Hooks (e.g., `useState`, `useEffect`) . | Manages state and complex logic using `state` and lifecycle methods . |
| **Example** | `function Welcome(props) { return <h1>Hello, {props.name}</h1>; }` | `class Welcome extends React.Component { render() { return <h1>Hello, {this.props.name}</h1>; } }` |

## Props

`Props` (short for properties) are objects used to pass data from a parent component to a child component. Props are **read-only** and cannot be modified directly within the child component .

**Example Usage:**
1.  **Child Component (`UserCard.js`)**
    ```jsx
    function UserCard(props) {
      return (
        <div>
          <h3>Name: {props.name}</h3>
          <p>Age: {props.age}</p>
        </div>
      );
    }
    ```

2.  **Parent Component (`App.js`)**
    ```jsx
    import UserCard from './UserCard';

    function App() {
      return (
        <div>
          <UserCard name="Ann" age={28} />
          <UserCard name="Minsu" age={31} />
        </div>
      );
    }
    ```
