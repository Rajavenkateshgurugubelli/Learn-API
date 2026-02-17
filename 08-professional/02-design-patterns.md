# API Design Patterns 🎨

Good APIs are predictable. Here are some key patterns professional developers use.

## 1. Pagination 📄
**Problem**: You have 1 million users. `GET /users` would crash the server.
**Solution**: Break it into pages.

### Offset Pagination (Simple)
`GET /users?limit=10&offset=20`
-   *Pros*: Easy to implement.
-   *Cons*: Slow for large datasets (SQL `OFFSET`).

### Cursor Pagination (Fast)
`GET /users?limit=10&after_id=1024`
-   *Pros*: Very fast, real-time friendly.
-   *Cons*: Harder to "jump" to page 50.

## 2. Filtering & Sorting 🔍
Don't create new endpoints like `/activeUsers`. Use query parameters.
-   **Filter**: `GET /users?status=active`
-   **Sort**: `GET /users?sort=-created_at` (Newest first)
-   **Fields**: `GET /users?fields=name,email` (GraphQL-lite style)

## 3. Rate Limiting 🛑
Protect your API from abuse.
-   Return header `X-RateLimit-Remaining: 49`.
-   Return `429 Too Many Requests` if they exceed the limit.

## 4. Error Handling ⚠️
Always return a consistent error structure.
```json
{
  "error": {
    "code": "resource_not_found",
    "message": "User 123 does not exist."
  }
}
```
