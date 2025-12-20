<details>
<summary>ENG (English Version)</summary>

## **Modern JavaScript 2: Ternary & Logical Operators**

**Ternary Operator**
- **Syntax**: `condition ? trueValue : falseValue`
- React conditional UI: `isLoggedIn ? 'Welcome!' : 'Please login'`
- Examples: Even/odd check, member status messages.

**Logical Operators**
- **OR (||)**: Left falsy → returns right (`nickname || 'Anonymous'`)
- **AND (&&)**: Left truthy → executes right (`score > 80 && showBadge()`).

**Practice**
```
const message = sum > 100 ? 'Over limit!' : 'Under limit';
// Short-circuit: userName || 'Guest', isPremium && 'VIP Badge'
```

**Mini App: Dynamic UI**
```
- HTML: User card + login toggle button
- ES6: let/const state, {name, status} destructuring
- `${isLoggedIn ? 'Welcome' : 'Login'}` ternary + template
- `isLoggedIn && card.classList.add('green')` conditional styling
- Arrow function event: `toggle.addEventListener('click', () => { isLoggedIn = !isLoggedIn; render(); })`
```

**Core Patterns**: `const/let + destructuring + template literals + ternary/&& ||` for reactive UI.

</details>

<details>
<summary>KOR (한국어 버전)</summary>

## **모던 자바스크립트 2: 삼항 및 논리 연산자**

**삼항 연산자**
- **문법**: `조건 ? 참값 : 거짓값`
- React 조건부 UI: `isLoggedIn ? '환영!' : '로그인'`
- 예제: 짝/홀수 판별, 회원 상태 메시지.

**논리 연산자**
- **OR (||)**: 좌측 falsy → 우측 반환 (`nickname || '익명'`)
- **AND (&&)**: 좌측 truthy → 우측 실행 (`score > 80 && 배지표시()`).

**연습**
```
const 메시지 = 합계 > 100 ? '초과!' : '미만';
// 단축 평가: userName || '손님', isPremium && 'VIP 배지'
```

**미니 앱: 동적 UI**
```
- HTML: 사용자 카드 + 로그인 토글 버튼
- ES6: let/const 상태, {name, status} 구조분해
- `${isLoggedIn ? '환영' : '로그인'}` 삼항 + 템플릿
- `isLoggedIn && card.classList.add('green')` 조건부 스타일
- 화살표 이벤트: `toggle.addEventListener('click', () => { isLoggedIn = !isLoggedIn; render(); })`
```

**핵심 패턴**: `const/let + 구조분해 + 템플릿 + 삼항/&& ||`로 반응형 UI 구현.

</details>
