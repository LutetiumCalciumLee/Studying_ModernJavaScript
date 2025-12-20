<details>
<summary>ENG (English Version)</summary>

## **REST API & JSON-Server**

**REST Fundamentals**
- **Resources** via URLs + **HTTP methods** (GET/POST/PUT/PATCH/DELETE)
- **Stateless**: All info in each request

**HTTP Methods**
| GET | POST | PUT | PATCH | DELETE |
|-----|------|-----|-------|--------|
| Read | Create | Replace | Partial Update | Delete |

**JSON-Server** (Mock Backend)
```
npm install json-server
npx json-server --watch db.json --port 3001
```

**db.json → Auto APIs**
```json
{
  "posts": [...], "users": [...]
}
```
→ `localhost:3001/posts`, `localhost:3001/users`

**React fetch Examples**
```jsx
// GET
fetch('http://localhost:3001/users').then(res => res.json())

// POST
fetch('/users', {method: 'POST', headers: {'Content-Type': 'application/json'}, body: JSON.stringify(user)})

// PUT (full replace)
fetch('/users/1', {method: 'PUT', body: JSON.stringify(fullUser)})

// PATCH (partial)
fetch('/users/1', {method: 'PATCH', body: JSON.stringify({name: 'New'})})

// DELETE
fetch('/users/1', {method: 'DELETE'})
```

**Project**: Todo CRUD app (React 3000 + JSON-Server 3001).

</details>

<details>
<summary>KOR (한국어 버전)</summary>

## **REST API & JSON-Server**

**REST 기본**
- **URL 자원** + **HTTP 메서드** (GET/POST/PUT/PATCH/DELETE)
- **Stateless**: 모든 정보 요청마다 포함

**HTTP 메서드**
| GET | POST | PUT | PATCH | DELETE |
|-----|------|-----|-------|--------|
| 조회 | 생성 | 전체 교체 | 부분 업데이트 | 삭제 |

**JSON-Server** (모의 백엔드)
```
npm install json-server
npx json-server --watch db.json --port 3001
```

**db.json → 자동 API**
```json
{
  "posts": [...], "users": [...]
}
```
→ `localhost:3001/posts`, `localhost:3001/users`

**React fetch 예제**
```jsx
// GET
fetch('http://localhost:3001/users').then(res => res.json())

// POST
fetch('/users', {method: 'POST', headers: {'Content-Type': 'application/json'}, body: JSON.stringify(user)})

// PUT (전체 교체)
fetch('/users/1', {method: 'PUT', body: JSON.stringify(전체User)})

// PATCH (부분)
fetch('/users/1', {method: 'PATCH', body: JSON.stringify({name: '신규'})})

// DELETE
fetch('/users/1', {method: 'DELETE'})
```

**프로젝트**: Todo CRUD 앱 (React 3000 + JSON-Server 3001).

</details>
