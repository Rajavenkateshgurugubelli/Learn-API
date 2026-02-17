# REST Architecture
**REST** stands for **Representational State Transfer**. It's a set of rules (architectural style) for building APIs.

## The 6 Constraints of REST (Simplified)
To be "RESTful", an API typically follows these principles:

1.  **Client-Server**: The client (frontend) and server (backend) are separate. They can evolve independently.
2.  **Stateless**: The server doesn't remember previous requests. Every request must contain all the information needed to process it (like your ID card).
3.  **Cacheable**: Responses should say if they can be saved (cached) to speed things up later.
4.  **Uniform Interface**:
    -   **Resources**: Everything is a resource (User, Photo, Post).
    -   **URIs**: Resources are identified by URLs (`/users/123`).
    -   **Standard Methods**: Use standard HTTP methods (`GET`, `POST`, `PUT`, `DELETE`).
5.  **Layered System**: The client doesn't need to know if it's talking directly to the server or a load balancer/proxy in between.
6.  **Code on Demand (Optional)**: Servers can send executable code (like Java Applets, rarely used now).

## Resource Naming Best Practices
-   Use **nouns**, not verbs.
    -   ✅ `GET /users` (Get all users)
    -   ❌ `GET /getUsers` (Don't use the verb in the URL)
-   Use **plurals**.
    -   ✅ `/products/1`
    -   ❌ `/product/1`
-   Use nesting for relationships.
    -   `GET /users/1/orders` (Get orders for user #1)
