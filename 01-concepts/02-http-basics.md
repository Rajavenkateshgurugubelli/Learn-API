# HTTP Basics
APIs communicate using the web's language: **HTTP (HyperText Transfer Protocol)**.

## The Request 📨
When you send a request, it usually contains:
1.  **URL (Address)**: Where are you sending the request? (e.g., `https://api.example.com/users`)
2.  **Method (Action)**: What do you want to do?
    -   `GET`: Retrieve data (Read).
    -   `POST`: Create new data (Write).
    -   `PUT` / `PATCH`: Update existing data.
    -   `DELETE`: Remove data.
3.  **Headers**: Meta-information (e.g., "I want the response in JSON format").
4.  **Body**: The data you are sending (used in POST/PUT).

## The Response 📦
The server replies with:
1.  **Status Code**: Did it work?
    -   `200 OK`: Success! ✅
    -   `201 Created`: Successfully created something. 🎉
    -   `400 Bad Request`: You sent something wrong. ❌
    -   `401 Unauthorized`: You need to log in. 🔒
    -   `404 Not Found`: The resource doesn't exist. 🤷‍♂️
    -   `500 Internal Server Error`: The server acted up. 🔥
2.  **Body**: The actual data requested (usually JSON).

## Example
**Request:**
`GET https://api.github.com/users/octocat`

**Response (Simplified):**
```json
{
  "login": "octocat",
  "id": 1,
  "name": "The Octocat"
}
```
