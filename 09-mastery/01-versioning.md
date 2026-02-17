# API Versioning Strategies 🔄

APIs change. Features are added, and sometimes features are removed. You must manage this without breaking the app for existing users.

## When to Version?
-   **Breaking Change**: You change the data format (e.g., renaming `id` to `userId`). -> **New Version Needed**.
-   **Non-breaking Change**: You add a new field (e.g., `email`). -> **No Version Needed** (clients usually ignore extra fields).

## Strategies

### 1. URI Versioning (Most Common)
Put the version in the URL.
-   `GET /v1/users`
-   `GET /v2/users`
-   *Pros*: Very easy to see and use.
-   *Cons*: Clutters the URL.

### 2. Header Versioning (Cleaner)
Send the version in a custom header.
-   `GET /users`
-   Header: `X-API-Version: 1`
-   *Pros*: URLs stay clean.
-   *Cons*: Harder to test in a browser address bar.

### 3. Media Type Versioning (The "Right" Way?)
Use the `Accept` header.
-   `Accept: application/vnd.myapi.v1+json`
-   *Pros*: strictly follows REST principles.
-   *Cons*: Complex to implement.

## Best Practice
Start with **URI Versioning** (`/v1`). It's pragmatic and everyone understands it.
