<details>
<summary>ENG (English Version)</summary>

## **Modern JavaScript & React**

### **1. Modern JavaScript Core Concepts**
- ES6+ features: `let`, `const`, template literals, arrow functions, destructuring assignment, default parameters, spread syntax, rest parameters, shorthand properties, map/filter/reduce functions, ternary/logical operators, and DOM manipulation.
- Variable declaration uses `let` and `const` for block scope and immutability.
- Arrow functions simplify code and retain `this` context.
- Destructuring and spread/rest syntax enhance readable data handling.
- Array and object transformation use `map`, `filter`, and `reduce`.
- Ternary and logical operators streamline conditional logic.

### **2. JSX & Component Structure**
- JSX: JavaScript extension allowing HTML-like markup in code.
- Must use a single top-level tag, curly braces for JS expressions and proper attribute naming (`className`, `htmlFor`).
- Conditional rendering utilizes ternary and logical operators.
- Components are reusable UI building blocks; can be function or class-based; support props for data passing.
- Props: Read-only data from parent to child; destructuring and default props supported.
- Children props allow flexible content injection in component tags.

### **3. State & Event Handling in React**
- State: Internal, mutable data managed per component (via `useState` hook).
- State updates trigger rerendering.
- Props: External, read-only data from parent components.
- Controlled components: User form inputs managed by state.
- Event handling uses camelCase and passes functions directly, supporting parameter/event object handling.
- Can use function props to let children trigger parent state changes.

### **4. Dynamic Rendering & List Management**
- Rendering lists with `map`, using `key` for efficient updates.
- Filtering and searching lists with `filter`, maintaining immutability.
- CRUD flows: Adding, updating, toggling, deleting list items.
- Components can separate, pass props, and be reused for modular design.

### **5. useEffect & Lifecycle Hooks**
- `useEffect`: Handles side effects (API calls, subscriptions) after render.
- Dependency array controls execution: no array (every render), empty array (mount only), value array (on specific changes).
- Clean-up function in `useEffect`—runs on unmount or dependency change.
- Integrates with `useRef` for direct DOM access and focus control.

### **6. Form Handling**
- Controlled components manage input, textarea, and select tags via state.
- `useState` objects efficiently track multiple fields.
- Support for multi-select in `<select>`, using event handlers to collect options.

### **7. LocalStorage Integration**
- Persistence: Save/load state to localStorage with `JSON.stringify`/`JSON.parse`.
- Maintains state across browser sessions.

### **8. React Project Structure & Environment**
- SPA and MPA concepts compared; React optimizes SPA for performance.
- Setup: Node.js, npm/yarn, VSCode, Prettier.
- Projects created with Create React App, structured in `/src`, `/public`.
- Use dependency managers to add packages (npm/yarn).
- Practice: Components, props, event handling, CRUD.

### **9. REST API & JSON Server**
- RESTful principles: client-server separation, statelessness, caching, consistent interface.
- JSON Server: Easy mock API for local development and testing.
- CRUD operations: GET, POST, PUT/PATCH, DELETE to interact with data resources.

### **10. Practical React Patterns**
- Complex UIs handled via functional components, props, children, reusable layouts.
- Efficient event handling and state management for forms, lists, shopping carts, user inputs.
- Sample code shows form submission, list filtering, item rendering, and REST API requests.

</details>

<details>
<summary>KOR (한국어 버전)</summary>

## **모던 자바스크립트 & 리액트 – 요약**

### **1. 모던 자바스크립트 핵심**
- ES6+ 문법: `let`, `const`, 템플릿 리터럴, 화살표 함수, 구조분해할당, 디폴트값, 스프레드/나머지 매개변수, 속성 생략, 배열/객체 고차 함수(map/filter/reduce), 삼항/논리 연산자, DOM 조작.
- 변수 선언은 `let`, `const`로 블록 스코프와 불변성 구현.
- 화살표 함수로 코드 축약 및 this 컨텍스트 유지.
- 구조분해 및 전개 구문으로 데이터 처리 간결화.
- 배열/객체 변환과 조건부 로직에 map/filter/reduce/삼항연산자 활용.

### **2. JSX와 컴포넌트 구조**
- JSX: 자바스크립트에서 HTML 유사 문법 사용; 최상위 태그 필수, JS 표현식은 중괄호, 속성은 카멜케이스(`className`, `htmlFor`).
- 조건부 렌더링에 삼항/논리연산자 활용.
- 컴포넌트: 함수형/클래스형, 독립·재사용 UI 단위, props 통해 데이터 전달.
- Props: 부모→자식 데이터 전달(읽기전용); 비구조화·기본값 가능.
- children props: 태그 내부 콘텐츠 유연 전달.

### **3. 리액트에서 상태와 이벤트 처리**
- State: 컴포넌트 내부 변경 값 관리(`useState` 훅); 변경시 자동 렌더.
- Props: 부모로부터 전달된 읽기 전용 값.
- Controlled Component: 폼 입력값을 상태로 제어.
- 이벤트 핸들러는 카멜케이스, 함수 직접 전달; 매개변수·이벤트 객체 처리 지원.
- 자식→부모 상태 변경은 핸들러 함수(props) 방식 활용.

### **4. 동적 렌더링과 리스트 관리**
- map 함수로 리스트 렌더링, key props로 효율적 업데이트.
- filter 함수로 조건 검색·삭제, 불변성 유지.
- CRUD 흐름: 항목 추가/수정/토글/삭제.
- 컴포넌트 분리와 props 이용한 모듈형 설계.

### **5. useEffect와 생명주기 관리**
- useEffect: 렌더 후 부수효과(API, 이벤트, 타이머) 처리.
- 의존성 배열로 실행시점(빈 배열: 최초 1회, 변동 값 배열: 해당 값 바뀔때만).
- cleanup 함수로 컴포넌트 언마운트/자원 회수 처리.
- useRef로 직접 DOM 접근·포커스 제어 구현.

### **6. 폼 입력 처리**
- 입력, textarea, select 등 Controlled Component 구조에서 상태(`useState`)로 모든 값 관리.
- 다중 선택(select) 이벤트, 객체 상태 활용.

### **7. 로컬스토리지 연동**
- 브라우저 로컬스토리지에 JSON.stringify/parse로 데이터 저장·불러오기; 새로고침/세션 유지 가능.

### **8. 리액트 프로젝트 환경과 구성**
- SPA·MPA 개념, 성능 최적화, 컴포넌트 기반 구조.
- 환경: Node.js, npm/yarn, VSCode, Prettier.
- CRA로 프로젝트 생성, src/public 폴더 구조.
- 의존성 관리, 컴포넌트 개발, CRUD 실습.

### **9. REST API와 JSON 서버**
- REST 원칙: 클라이언트-서버 분리, 무상태성, 캐시, 일관 인터페이스.
- JSON 서버: 로컬 mock API 신속 생성·테스트.
- CRUD 연산: GET, POST, PUT/PATCH, DELETE로 리소스 관리.

### **10. 리액트 실전 패턴**
- 함수형 컴포넌트, props, children, 재사용 렌더링, 이벤트, 상태 관리, 폼·리스트·장바구니·입력·REST API 등 실습 예제 포함.

</details>
