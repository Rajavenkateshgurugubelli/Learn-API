# REST Architecture
**REST** stands for **Representational State Transfer**. It's a set of rules (architectural style) for building APIs.

## The 6 Constraints of REST (Simplified)
To be "RESTful", an API typically follows these principles:
1.  **Client-Server**: The client (frontend) and server (backend) are separate.
2.  **Stateless**: The server doesn't remember previous requests.
3.  **Cacheable**: Responses should say if they can be saved (cached).
4.  **Uniform Interface**: Standard methods and URLs.
5.  **Layered System**: You might be talking to a proxy, not the server directly.
6.  **Code on Demand (Optional)**.

## Resource Naming Best Practices 🏷️
REST is all about **Resources** (Nouns), not Actions (Verbs).

### Bad API Design (RPC Style) ❌
You might see this in old systems. It uses verbs in the URL.
```python
# Bad: The URL tells you the action
requests.post('https://api.com/getAllUsers')
requests.post('https://api.com/createUser')
requests.post('https://api.com/deleteUser?id=1')
```

### Good REST Design ✅
Use the **Standard HTTP Methods** to define the action. The URL should just be the "Thing" (Resource).

#### Get All Users
```python
# GET /users
requests.get('https://api.com/users')
```

#### Create a User
```python
# POST /users
requests.post('https://api.com/users', json={...})
```

#### Delete a User
```python
# DELETE /users/1
requests.delete('https://api.com/users/1')
```

## Nested Resources
How to get "Orders for User 1"?
-   ✅ `GET /users/1/orders`
-   ❌ `/getOrdersForUser?id=1`
