<details>
<summary>ENG (English Version)</summary>

## **React Router**

**Purpose**: Enables SPA routing - dynamic content changes without page reloads.

**Core Components**
```
BrowserRouter  // Wraps app (HTML5 History API)
Routes         // Groups Route components
Route          // path="/about" element={<About/>}
Link           // <Link to="/about">About</Link>
```

**Setup**
```
npm install react-router-dom
// index.js
<BrowserRouter>
  <App/>
</BrowserRouter>
```

**Routing Flow**
```
<Link to="/about"> → URL changes → Routes finds matching Route → Renders <About/>
```

**404 & Redirects**
```
<Routes>
  <Route path="/" element={<Home/>} />
  <Route path="/about" element={<About/>} />
  <Route path="*" element={<NotFound/>} />        {/* Catch-all */}
  {/* OR */}
  <Route path="*" element={<Navigate to="/" replace/>} />
</Routes>
```

**Dynamic Routes (Params)**
```
<Route path="/user/:userId" element={<UserDetail/>} />
// Access: const {userId} = useParams();
// Navigate: const navigate = useNavigate(); navigate(`/user/${id}`);
```

**Project**: Home/About/Products/ProductDetail + 404 handling.

</details>

<details>
<summary>KOR (한국어 버전)</summary>

## **React Router**

**목적**: SPA 라우팅 - 페이지 새로고침 없이 동적 콘텐츠 변경.

**핵심 컴포넌트**
```
BrowserRouter  // 앱 감싸기 (HTML5 History API)
Routes         // Route 그룹화
Route          // path="/about" element={<About/>}
Link           // <Link to="/about">About</Link>
```

**설치/설정**
```
npm install react-router-dom
// index.js
<BrowserRouter>
  <App/>
</BrowserRouter>
```

**라우팅 흐름**
```
<Link to="/about"> → URL 변경 → Routes가 매칭 Route 찾음 → <About/> 렌더링
```

**404 & 리다이렉트**
```
<Routes>
  <Route path="/" element={<Home/>} />
  <Route path="/about" element={<About/>} />
  <Route path="*" element={<NotFound/>} />         {/* 모든 경로 */}
  {/* 또는 */}
  <Route path="*" element={<Navigate to="/" replace/>} />
</Routes>
```

**동적 라우트 (Params)**
```
<Route path="/user/:userId" element={<UserDetail/>} />
// 사용: const {userId} = useParams();
// 이동: const navigate = useNavigate(); navigate(`/user/${id}`);
```

**프로젝트**: Home/About/Products/ProductDetail + 404 처리.

</details>
