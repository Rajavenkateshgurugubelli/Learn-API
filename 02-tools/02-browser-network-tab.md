# Debugging with Browser Network Tab 🕷️

Every modern browser (Chrome, Edge, Firefox) has a powerful API debugger built-in. You don't always need Postman!

## How to open it
1.  Right-click anywhere on a webpage -> **Inspect**.
2.  Click the **Network** tab at the top.

## How to use it
1.  Go to a site that fetches data (e.g., `twitter.com` or `reddit.com`).
2.  Refresh the page (`F5`).
3.  You will see a flood of requests! 🌊
4.  **Filter**: Type `fetch` or click **Fetch/XHR** to see only API calls (no images/CSS).

## Inspecting a Request
Click on a request (e.g., `user.json`) to see details:
-   **Headers**: What did you send? (User-Agent, Cookies, Auth tokens).
-   **Payload**: What data did you send? (for POST requests).
-   **Preview / Response**: The actual JSON data returned by the server.
-   **Timing**: How long did it take? (TTFB - Time To First Byte).

## Why is this useful?
If your frontend code isn't working, **check the Network tab first**.
-   Did the request go out?
-   Did it fail (`404` or `500`)?
-   Did the server return the wrong data?
