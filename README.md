<details>
<summary>ENG (English Version)</summary>

## **React: Props, State, Events & Forms**

**Props & Composition**
- **defaultProps**: `{name = "Guest"}` destructuring in params.
- **children**: `props.children` receives content between tags (layouts/cards).
- **Destructuring**: `function Profile({name, age})` vs `props.name`.

**useState Management**
```
const [count, setCount] = useState(0);
// Props: read-only (parent → child)
// State: mutable (internal component)
```
**Parent State Pattern**: Parent passes `setParentState` as prop to child.

**Event Handling**
```
<button onClick={handleClick}>Click</button>  // Function reference
<button onClick={() => handleClick('arg')}>  // Arrow wrapper
e.target.value, e.preventDefault()           // SyntheticEvent
```

**Controlled Forms**
```
const [formData, setFormData] = useState({});
<input 
  name="email" 
  value={formData.email} 
  onChange={(e) => setFormData({...formData, [e.target.name]: e.target.value})}
/>
```
**Single Source**: State = form value truth; `name` attribute enables dynamic updates.

</details>

<details>
<summary>KOR (한국어 버전)</summary>

## **React: Props, State, 이벤트 & 폼**

**Props & 조합**
- **기본값**: `{name = "Guest"}` 매개변수 구조분해.
- **children**: 태그 사이 콘텐츠 자동 수신 (레이아웃/카드).
- **구조분해**: `function Profile({name, age})`.

**useState 관리**
```
const [count, setCount] = useState(0);
// Props: 읽기전용 (부모→자식)
// State: 변경가능 (내부)
```
**부모 상태 패턴**: 부모 `setParentState`를 props로 자식 전달.

**이벤트 처리**
```
<button onClick={handleClick}>클릭</button>    // 함수 참조
<button onClick={() => handleClick('인자')}>  // 화살표 래퍼
e.target.value, e.preventDefault()            // SyntheticEvent
```

**제어된 폼**
```
const [formData, setFormData] = useState({});
<input 
  name="email" 
  value={formData.email} 
  onChange={(e) => setFormData({...formData, [e.target.name]: e.target.value})}
/>
```
**단일 진리원천**: 상태 = 폼 값; `name` 속성으로 동적 업데이트.

</details>
