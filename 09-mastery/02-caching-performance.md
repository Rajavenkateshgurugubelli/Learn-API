# Caching & Performance 🚀

The fastest API request is the one you don't have to make.

## Types of Caching

### 1. Client-Side Caching (HTTP Headers)
The server tells the browser (Client) to save the response.
-   **`Cache-Control: max-age=3600`**: "Don't ask me again for this data for 1 hour (3600 seconds)."
-   *Use Case*: User profile picture, list of countries.

### 2. Conditional Requests (ETag)
1.  Server sends data + an ID (`ETag: "v1"`).
2.  Client saves it.
3.  Next time, Client asks: "I have `v1`, is it still good?" (`If-None-Match: "v1"`).
4.  Server says: `304 Not Modified` (No data sent, huge bandwidth saving!) OR sends new data.

### 3. Server-Side Caching (Redis)
The server saves the result of a slow database query in memory (RAM).
-   *Request 1*: App -> DB (Slow, 200ms) -> Save to Redis -> Client.
-   *Request 2*: App -> Redis (Fast, 5ms) -> Client.

## Other Tips
-   **Compression**: Enable GZIP or Brotli compression to shrink JSON size by ~70%.
-   **Pagination**: Never return "all" records (see Design Patterns).
