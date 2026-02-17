# API Testing Strategies 🧪

Testing ensures your API works as expected and doesn't break when you change code.

## Why Test?
-   **Reliability**: Catch bugs before users do.
-   **Confidence**: Refactor code without fear.
-   **Documentation**: Tests show how the API is supposed to be used.

## Types of Tests

### 1. Unit Tests 🔍
Test a single function or component in isolation.
-   *Example*: Does the `calculateTotal(price, tax)` function return the correct number?
-   *Tools*: Jest (Node.js), Pytest (Python).

### 2. Integration Tests 🔗
Test how multiple parts work together (e.g., API Endpoint + Database).
-   *Example*: Does `POST /users` actually save the user to the database?

### 3. End-to-End (E2E) Tests 🏁
Test the entire flow from the user's perspective.
-   *Example*: User logs in -> Creates a post -> Sees the post on the feed.

## Tools of the Trade
-   **Postman**: Great for manual testing and running simple automated suites.
-   **Newman**: Runs Postman collections in the command line (good for CI/CD).
-   **Jest / Supertest**: Popular for Node.js API testing.
-   **Pytest**: Standard for Python testing.

## Example (Pseudo-code)
```javascript
test('GET /health returns 200', async () => {
  const response = await request(app).get('/health');
  expect(response.status).toBe(200);
  expect(response.body.message).toBe('OK');
});
```
