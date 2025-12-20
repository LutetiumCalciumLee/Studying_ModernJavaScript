<details>
<summary>ENG (English Version)</summary>

## **React useEffect Hook**

**Purpose**: Side effects (API calls, subscriptions, DOM changes) in functional components; replaces class lifecycle methods.

**Dependency Patterns**
```
useEffect(() => {}, []);           // Mount only (componentDidMount)
useEffect(() => {}, [userId]);     // Mount + userId changes
useEffect(() => {});               // Every render
```

**Cleanup Function**
```jsx
useEffect(() => {
  const timer = setInterval(tick, 1000);
  return () => clearInterval(timer);  // Runs before unmount/re-run
}, []);
```

**Data Persistence**
```jsx
const [todos, setTodos] = useState(JSON.parse(localStorage.getItem('todos') || '[]'));

useEffect(() => {
  localStorage.setItem('todos', JSON.stringify(todos));
}, [todos]);  // Save on every todos change
```

**Key Timing**:
- Effect: After render
- Cleanup: Before unmount OR before effect re-runs

</details>

<details>
<summary>KOR (한국어 버전)</summary>

## **React useEffect 훅**

**목적**: 함수형 컴포넌트의 부수효과(API 호출, 구독, DOM 변경); 클래스 라이프사이클 대체.

**의존성 패턴**
```
useEffect(() => {}, []);           // 마운트 시 1회 (componentDidMount)
useEffect(() => {}, [userId]);     // 마운트 + userId 변경 시
useEffect(() => {});               // 모든 렌더링 후
```

**정리 함수**
```jsx
useEffect(() => {
  const timer = setInterval(tick, 1000);
  return () => clearInterval(timer);  // 언마운트 전 / 재실행 전
}, []);
```

**데이터 지속성**
```jsx
const [todos, setTodos] = useState(JSON.parse(localStorage.getItem('todos') || '[]'));

useEffect(() => {
  localStorage.setItem('todos', JSON.stringify(todos));
}, [todos]);  // todos 변경 시 저장
```

**실행 순서**:
- Effect: 렌더링 후
- Cleanup: 언마운트 전 또는 effect 재실행 전

</details>
