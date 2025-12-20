<details>
<summary>ENG (English Version)</summary>

## **React Context & Custom Hooks**

**Hook Rules** (Strict)
- Top-level only (no loops/conditions/nested functions)
- Same order every render

**Custom Hooks** (`use` prefix)
```
const useToggle = (initial = false) => {
  const [value, setValue] = useState(initial);
  const toggle = () => setValue(prev => !prev);
  return [value, toggle];
};
// Usage: const [isOpen, toggle] = useToggle(false);
```

**useWindowSize Example**
```jsx
const useWindowSize = () => {
  const [size, setSize] = useState({width: window.innerWidth, height: window.innerHeight});
  useEffect(() => {
    const handleResize = () => setSize({width: window.innerWidth, height: window.innerHeight});
    window.addEventListener('resize', handleResize);
    return () => window.removeEventListener('resize', handleResize);
  }, []);
  return size;
};
```

**Context API** (No Props Drilling)
```
1. Create: const ThemeContext = createContext()
2. Provider: <ThemeContext.Provider value={{theme, setTheme}}>
3. Consumer: const {theme} = useContext(ThemeContext)
```

**Custom Context Hook** (Best Practice)
```jsx
export const useTheme = () => {
  const context = useContext(ThemeContext);
  if (!context) throw new Error('useTheme must be within ThemeProvider');
  return context;
};
```

**Use Cases**: Theme, auth, language, global config.

</details>

<details>
<summary>KOR (한국어 버전)</summary>

## **React Context & 커스텀 훅**

**훅 규칙** (엄격)
- 최상위 호출만 (반복문/조건/중첩함수 금지)
- 매 렌더링 동일 순서

**커스텀 훅** (`use` 접두사)
```
const useToggle = (initial = false) => {
  const [value, setValue] = useState(initial);
  const toggle = () => setValue(prev => !prev);
  return [value, toggle];
};
// 사용: const [isOpen, toggle] = useToggle(false);
```

**useWindowSize 예제**
```jsx
const useWindowSize = () => {
  const [size, setSize] = useState({width: window.innerWidth, height: window.innerHeight});
  useEffect(() => {
    const handleResize = () => setSize({width: window.innerWidth, height: window.innerHeight});
    window.addEventListener('resize', handleResize);
    return () => window.removeEventListener('resize', handleResize);
  }, []);
  return size;
};
```

**Context API** (Props Drilling 해결)
```
1. 생성: const ThemeContext = createContext()
2. Provider: <ThemeContext.Provider value={{theme, setTheme}}>
3. Consumer: const {theme} = useContext(ThemeContext)
```

**컨텍스트 커스텀 훅** (최선 실무)
```jsx
export const useTheme = () => {
  const context = useContext(ThemeContext);
  if (!context) throw new Error('useTheme must be within ThemeProvider');
  return context;
};
```

**용도**: 테마, 인증, 언어, 전역 설정.

</details>
