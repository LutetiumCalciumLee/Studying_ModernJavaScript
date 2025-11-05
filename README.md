## REST API & JSON-Server

### REST API Fundamentals

**REST (Representational State Transfer)** is a web design principle that uses HTTP protocol to manage resources. Key concepts:

- **Resource**: Server data (user information, posts, products, etc.)
- **Representation**: Data format (JSON, XML, etc.)
- **State Transfer**: Exchanging resource states via HTTP methods

REST operates by specifying resources via URLs and defining actions through HTTP methods.

### Six REST Principles

1. **Client-Server Architecture**: Client handles UI; server manages data
2. **Statelessness**: Server doesn't store request state; all info must be in each request
3. **Cacheability**: Clients can cache responses
4. **Layered System**: Clients don't need to know backend structure
5. **Uniform Interface**: Consistent resource access patterns
6. **Code on Demand (Optional)**: Server can send executable code to client

### HTTP Methods & Operations

| Operation | HTTP Method | Example |
|-----------|-------------|---------|
| Retrieve data | GET | `/users` (all) or `/users/1` (specific) |
| Create data | POST | `/users` |
| Update (full) | PUT | `/users/1` |
| Update (partial) | PATCH | `/users/1` |
| Delete data | DELETE | `/users/1` |

### JSON-Server: Quick Backend Mock

**JSON-Server** is a Node.js tool that instantly creates a mock REST API from a local JSON file. Perfect for frontend testing without a real backend.

**Key Features:**
- Simple installation and fast execution
- Auto-generates API server from `db.json`
- Supports full CRUD operations
- Works with `fetch()` and `axios` like real servers

### Installation & Setup

**Local Installation (Recommended):**

```bash
npm install json-server
npx json-server --watch db.json --port 3001
```

**Important**: Create `db.json` in your project root before running the server. The port change to 3001 avoids conflicts with React's default port 3000.

### db.json Structure

The file is simple JSON:

```json
{
  "posts": [
    { "id": 1, "title": "First Post", "author": "John" },
    { "id": 2, "title": "Second Post", "author": "Jane" }
  ],
  "comments": [
    { "id": 1, "body": "Great!", "postId": 1 }
  ]
}
```

Top-level keys become API endpoints:
- `http://localhost:3001/posts`
- `http://localhost:3001/comments`

### Calling REST APIs in React

Using the `fetch()` API:

**GET (Read):**
```javascript
const [users, setUsers] = useState([]);
useEffect(() => {
  fetch("http://localhost:3001/users")
    .then((res) => res.json())
    .then((data) => setUsers(data));
}, []);
```

**POST (Create):**
```javascript
fetch("http://localhost:3001/books", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify(newBook)
})
.then((res) => res.json())
.then((data) => console.log("Added:", data));
```

**PUT (Replace all fields):**
```javascript
fetch("http://localhost:3001/books/1", {
  method: "PUT",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({
    id: "1",
    title: "Updated Title",
    author: "New Author",
    year: 2025
  })
});
```

**PATCH (Update specific fields only):**
```javascript
fetch("http://localhost:3001/books/1", {
  method: "PATCH",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({ year: 1995 })
});
```

**DELETE:**
```javascript
fetch(`http://localhost:3001/books/${id}`, {
  method: "DELETE"
});
```

### Key Differences: PUT vs PATCH

- **PUT**: Completely replaces the resource (all fields must be included)
- **PATCH**: Only updates specified fields (safer and more efficient)

### Practical Project: Todo List

The document includes a mini-project using JSON-Server to build a task management app with full CRUD functionality. The setup requires:

1. Create `db.json` with initial todo data
2. Run JSON-Server on port 3001
3. Run React app on port 3000
4. Use separate terminals for both servers
5. Implement CRUD functions connected to the mock API
