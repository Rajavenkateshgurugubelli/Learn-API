# Consuming APIs with Code 💻

Postman is great for testing, but in the real world, your **code** needs to talk to APIs.

## JavaScript (Frontend/Node.js) using `fetch`
The modern way to make requests in JS is the `fetch` API.

```javascript
// GET Request
fetch('https://official-joke-api.appspot.com/random_joke')
  .then(response => response.json()) // Parse JSON
  .then(data => {
    console.log(data); // { type: "general", setup: "...", ... }
  })
  .catch(error => console.error('Error:', error));

// Async/Await (Cleaner syntax)
async function getJoke() {
  try {
    const response = await fetch('https://official-joke-api.appspot.com/random_joke');
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}
```

## Python using `requests`
Python's `requests` library is legendary for its simplicity.
*(Requires: `pip install requests`)*

```python
import requests

# GET Request
response = requests.get('https://official-joke-api.appspot.com/random_joke')

if response.status_code == 200:
    data = response.json()
    print(data)
else:
    print("Error:", response.status_code)
```

## Task 🎯
1.  Create a file named `joke_client.js` or `joke_client.py`.
2.  Paste the code above.
3.  Run it (`node joke_client.js` or `python joke_client.py`) and see the joke in your terminal!
