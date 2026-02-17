# API Keys 🔑

## What is an API Key?
An **API Key** is a unique string of code that identifies the calling program (you/your app) to the API.

Think of it like a **ticket to a concert**:
-   It proves you bought a ticket.
-   It lets you in.
-   It doesn't necessarily say *who* you are (Authentication), just that you have permission (Authorization).

## Why use them?
1.  **Tracking**: The API provider can see who is using their API.
2.  **Rate Limiting**: They can stop you if you make too many requests (e.g., 1000 per day).
3.  **Monetization**: They can charge you based on usage.

## How to use it?
Usually, you send it in the **Header** or **Query Parameter**.

**Header Example:**
```http
GET /weather
Authorization: Api-Key 12345abcdef
```

**Query Param Example:**
```http
GET /weather?api_key=12345abcdef
```

## ⚠️ Security Best Practice
**NEVER share your API Key!**
-   Do not commit it to GitHub (use environment variables).
-   If someone steals it, they can use your quota and you might get the bill! 💸
