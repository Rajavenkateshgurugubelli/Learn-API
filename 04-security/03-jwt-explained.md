# JWT Explained 🎫

**JWT** (pronounced "jot") stands for **JSON Web Token**. It is a compact way to securely transmit information between parties as a JSON object.

## Structure
A JWT looks like `aaaaa.bbbbb.ccccc`. It has 3 parts separated by dots:

1.  **Header**: What type of token it is (JWT) and the signing algorithm (HS256).
2.  **Payload**: The data (Claims). "User ID is 123", "Role is Admin".
3.  **Signature**: Using a secret key to ensure the token hasn't been tampered with.

## Why use JWT?
**Stateless Authentication**.
-   **Traditional Session**: The server keeps a record of logged-in users in memory/database.
-   **JWT**: The server **doesn't** need to keep a record. When the client sends the token, the server just checks the signature. If the signature is valid, the token is valid.

## Example Flow
1.  User logs in with username/password.
2.  Server verifies credentials and generates a **JWT**.
3.  Server sends JWT to Client.
4.  Client stores JWT (e.g., in LocalStorage).
5.  Client sends JWT in the `Authorization` header for every request.
    ```http
    Authorization: Bearer <token>
    ```
6.  Server verifies signature and processes request.

## ⚠️ Warning
**Do not put sensitive info (like passwords) in the Payload!**
Base64 decoding is easy, so anyone who sees the token can read the payload. The Signature only prevents *modification*, not *reading*.
