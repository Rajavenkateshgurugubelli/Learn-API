# Build an API with Node.js & Express 🟢

**Express** is the most popular web framework for Node.js. It's fast, unopinionated, and minimalist.

## Prerequisites
-   [Node.js](https://nodejs.org/) installed.
-   A terminal/command prompt.

## Step 1: Initialize Project
Open your terminal and run:

```bash
mkdir my-api
cd my-api
npm init -y  # Creates package.json with defaults
npm install express
```

## Step 2: Write the Code
Create a file named `index.js` and add:

```javascript
const express = require('express');
const app = express();
const PORT = 3000;

// Middleware to parse JSON bodies
app.use(express.json());

// A simple GET route
app.get('/', (req, res) => {
    res.json({ message: "Hello from Node.js!" });
});

// A POST route
app.post('/echo', (req, res) => {
    const data = req.body;
    res.json({ yourData: data });
});

app.listen(PORT, () => {
    console.log(`Server running on http://localhost:${PORT}`);
});
```

## Step 3: Run it 🏃
```bash
node index.js
```
Open your browser and visit `http://localhost:3000`. You should see the JSON message!

## Next Steps
-   Try creating a standard "TODO List" API with `GET`, `POST`, `PUT`, `DELETE`.
