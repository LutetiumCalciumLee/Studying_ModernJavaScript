<details>
<summary>ENG (English Version)</summary>

## **React JSX, Components & Props**

**JSX Syntax**
- **Single Root**: All elements wrapped in one parent (`<div>`).
- **JS Expressions**: `{variable}` or `{function()}` embeds JS.
- **Attributes**: `className` (not `class`), `htmlFor` (not `for`).
- **Comments**: `{/* comment */}`.

**Styling**
- **Inline**: `style={{color: 'red', backgroundColor: 'yellow'}}` (camelCase).
- **CSS**: Import + `className="my-class"`.

**Conditional Rendering**
```
{isLoggedIn ? <Welcome/> : <Login/>}     // Ternary
{messages.length && <p>{messages.length} unread</p>}  // AND
{name || 'Guest'}                         // OR fallback
```

**Components**
| Type | Modern Choice | Features |
|------|---------------|----------|
| **Functional** | ✅ Recommended | `function MyComp({props}) { return <div/>; }` + Hooks |
| **Class** | ❌ Legacy | `class MyComp extends React.Component` + state/lifecycle |

**Props (Read-Only Data Flow)**
```jsx
// Child
function UserCard({name, age}) {  // Destructuring
  return <div>Name: {name}, Age: {age}</div>;
}

// Parent
<UserCard name="Ann" age={28} />
<UserCard name="Minsu" age={31} />
```

**Core Benefits**: Reusability, encapsulation, composability.

</details>

<details>
<summary>KOR (한국어 버전)</summary>

## **React JSX, 컴포넌트 & Props**

**JSX 문법**
- **단일 루트**: 모든 요소 하나의 부모로 감싸기 (`<div>`).
- **JS 표현식**: `{변수}` 또는 `{함수()}`.
- **속성**: `className` (class 아님), `htmlFor` (for 아님).
- **주석**: `{/* 주석 */}`.

**스타일링**
- **인라인**: `style={{color: 'red', backgroundColor: 'yellow'}}` (camelCase).
- **CSS**: import + `className="my-class"`.

**조건부 렌더링**
```
{isLoggedIn ? <Welcome/> : <Login/>}     // 삼항
{messages.length && <p>{messages.length}개 읽지 않음</p>}  // AND
{name || '손님'}                         // OR 대체값
```

**컴포넌트**
| 유형 | 모던 초이스 | 특징 |
|------|-----------|------|
| **함수형** | ✅ 권장 | `function MyComp({props})` + Hooks |
| **클래스** | ❌ 구버전 | `class MyComp extends React.Component` |

**Props (읽기 전용 데이터 전달)**
```jsx
// 자식
function UserCard({name, age}) {  // 구조분해
  return <div>이름: {name}, 나이: {age}</div>;
}

// 부모
<UserCard name="Ann" age={28} />
<UserCard name="Minsu" age={31} />
```

**핵심 장점**: 재사용성, 캡슐화, 조합성.

</details>
