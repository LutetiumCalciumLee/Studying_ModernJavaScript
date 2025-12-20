<details>
<summary>ENG (English Version)</summary>

## **React useRef Hook**

**Purpose**: Mutable reference persisting across renders **without re-rendering**; DOM access + internal state storage.

**vs useState**
```
useState: value changes → re-render
useRef:  ref.current changes → NO re-render
```

**DOM Access**
```jsx
const inputRef = useRef(null);
<input ref={inputRef} />
inputRef.current.focus();  // Programmatic focus/scroll/measure
```

**Mutable Storage**
```jsx
const timerRef = useRef(null);
timerRef.current = setInterval(...);  // Store IDs/flags
return () => clearInterval(timerRef.current);
```

**Multi-Input Forms**
```jsx
const [formData, setFormData] = useState({id:'', pw:''});
const handleChange = (e) => {
  const {name, value} = e.target;
  setFormData({...formData, [name]: value});
};
// Single handler for all inputs via `name` attribute
```

**Key Use Cases**: Focus control, timer IDs, previous values, DOM measurements.

</details>

<details>
<summary>KOR (한국어 버전)</summary>

## **React useRef 훅**

**목적**: 렌더링 간 **변경가능 참조** (리렌더링 **없이**); DOM 접근 + 내부 상태 저장.

**vs useState**
```
useState: 값 변경 → 리렌더링
useRef:  ref.current 변경 → 리렌더링 없음
```

**DOM 접근**
```jsx
const inputRef = useRef(null);
<input ref={inputRef} />
inputRef.current.focus();  // 포커스/스크롤/측정
```

**가변 저장**
```jsx
const timerRef = useRef(null);
timerRef.current = setInterval(...);  // ID/플래그 저장
return () => clearInterval(timerRef.current);
```

**다중 입력 폼**
```jsx
const [formData, setFormData] = useState({id:'', pw:''});
const handleChange = (e) => {
  const {name, value} = e.target;
  setFormData({...formData, [name]: value});
};
// `name` 속성으로 모든 입력 하나의 핸들러
```

**주요 용도**: 포커스 제어, 타이머 ID, 이전값, DOM 측정.

</details>
