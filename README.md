<details>
<summary>ENG (English Version)</summary>

## **Modern JavaScript 1**

**Overview**: ES6+ features and tooling ecosystem for React/Vue/Angular; emphasizes functional patterns and immutability with package managers, bundlers, transpilers.

### **Variables & Scope**
- **let/const** over **var**: Block-scoped, safer; **const** prevents reassignment (mutable contents), **let** allows reassignment.

### **Hoisting & TDZ**
- **var**: Hoisted + initialized (undefined), accessible pre-declaration.
- **let/const**: Hoisted but uninitialized (Temporal Dead Zone/ReferenceError).

### **Key ES6+ Features**
- **Template Literals**: `` `Hello ${name}` `` for interpolation.
- **Arrow Functions**: `() => value`; lexical `this` binding.
- **Destructuring**: `{name, age} = user`; `[first, ...rest] = array`.
- **Spread/Rest**: Spread merges/copies; Rest collects args (`...args`).

### **Array Methods Pipeline**
```
data.map(x => x.score + 10)  // Transform
  .filter(x => x.score >= 80) // Filter
  .reduce((sum, x) => sum + x.score, 0) // Aggregate
```
**Common**: Filter (≥60) → Map (extract names).

**Core Principle**: Immutable updates via functional methods (map/filter/reduce) + spread operator.

</details>

<details>
<summary>KOR (한국어 버전)</summary>

## **모던 자바스크립트 1**

**개요**: ES6+ 기능 + React/Vue/Angular 도구 생태계; 함수형 패턴과 불변성 강조.

### **변수 & 스코프**
- **let/const** 우선: 블록 스코프; **const** 재할당 방지(내용 변경 가능), **let** 재할당 가능.

### **Hoisting & TDZ**
- **var**: 선언 전 undefined로 초기화.
- **let/const**: 선언 전 TDZ(ReferenceError).

### **주요 ES6+ 기능**
- **템플릿 리터럴**: `` `안녕 ${name}` ``.
- **화살표 함수**: `() => value`; 렉시컬 `this`.
- **구조 분해**: `{name, age} = user`; `[first, ...rest] = array`.
- **전개/나머지**: 전개(병합/복사), 나머지(`...args`).

### **배열 메서드 파이프라인**
```
data.map(x => x.score + 10)     // 변환
  .filter(x => x.score >= 80)   // 필터
  .reduce((sum, x) => sum + x.score, 0) // 집계
```
**일반 패턴**: 점수 필터(≥60) → 이름 추출 map.

**핵심 원칙**: map/filter/reduce + 전개 연산자로 불변 업데이트.

</details>
