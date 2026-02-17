# GraphQL vs REST 🥊

**GraphQL** is a newer way to build APIs, developed by Facebook.

## The Problem with REST
Imagine you want to show a user profile with their 3 latest posts.
In REST, you might need 2 requests:
1.  `GET /users/1` (Gets user details, but maybe *too much* info like address, email, etc. -> **Over-fetching**)
2.  `GET /users/1/posts` (Gets posts, but you only need the titles -> **Under-fetching** initially)

## The GraphQL Solution
With GraphQL, you ask for **exactly what you want** in a single request.

**Request:**
```graphql
query {
  user(id: 1) {
    name
    posts(limit: 3) {
      title
    }
  }
}
```

**Response:**
```json
{
  "data": {
    "user": {
      "name": "Raja",
      "posts": [
        {"title": "Hello World"},
        {"title": "GraphQL is cool"},
        {"title": "API tips"}
      ]
    }
  }
}
```

## Summary
-   **REST**: Multiple endpoints, fixed data structure.
-   **GraphQL**: Single endpoint, flexible data structure.
