# API Security Risks (OWASP) 🛡️

You built it, but can you protect it? Here are the top risks you need to know.

## 1. Broken Object Level Authorization (BOLA)
*Aka "IDOR" (Insecure Direct Object Reference)*
-   **Scenario**: User A is logged in. They change the URL ID from `/users/A` to `/users/B`.
-   **Risk**: If you don't check permissions, User A sees User B's data!
-   **Fix**: Always check: "Does `currentUser` own `requestedResource`?"

## 2. Broken Authentication
-   **Scenario**: Letting users use weak passwords, or allowing "Brute Force" attacks (guessing passwords millions of times).
-   **Fix**: Use strong password policies, Rate Limiting, and MFA (Multi-Factor Auth).

## 3. Excessive Data Exposure
-   **Scenario**: Your DB has a user object with `{ name, password_hash, address }`. You send the **whole object** to the frontend, relying on the frontend to hide the password.
-   **Risk**: Hacker inspects the Network tab and sees the hidden data.
-   **Fix**: Use DTOs (Data Transfer Objects) to only send exactly what is needed (e.g., just `name`).

## 4. Lack of Rate Limiting
-   **Scenario**: Hacker sends 10,000 requests/second to crash your server (DDoS).
-   **Fix**: Implement limits (e.g., 100 requests/minute per IP).
