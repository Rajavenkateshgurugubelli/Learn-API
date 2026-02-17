# Postman Basics 🚀
**Postman** is a popular tool for testing APIs without writing code.

## Why use Postman?
-   **Visual Interface**: See your request and response clearly.
-   **History**: Saves your past requests.
-   **Collections**: Group requests together (like "User API" or "Payment API").
-   **Automation**: Run tests automatically.

## Getting Started
1.  **Download & Install**: Get it from [postman.com](https://www.postman.com/downloads/).
2.  **Create a Collection**: Click "New" -> "Collection". Name it "Learn API".
3.  **Add a Request**:
    -   Click "Add a request".
    -   Name it "Get Public Joke".
    -   Set the method to `GET`.
    -   Enter URL: `https://official-joke-api.appspot.com/random_joke`
    -   Click **Send**.

## Analyzing the Result
Look at the bottom pane:
-   **Status**: Should be `200 OK`.
-   **Time**: How long it took.
-   **Body**: The JSON response (the joke!).

```json
{
    "type": "general",
    "setup": "Why did the scarecrow win an award?",
    "punchline": "Because he was outstanding in his field.",
    "id": 348
}
```

## Try it yourself!
Try changing the method to `POST` on a `GET` only URL and see what error you get (`404` or `405 Method Not Allowed`). Exploring errors is a great way to learn!
