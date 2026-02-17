# Build an API with Python & FastAPI 🐍

**FastAPI** is a modern, fast (high-performance), web framework for building APIs with Python 3.7+.

## Prerequisites
-   [Python](https://www.python.org/) installed.
-   A terminal/command prompt.

## Step 1: Install Dependencies
Run:
```bash
pip install fastapi uvicorn
```
*`uvicorn` is the server that runs your FastAPI code.*

## Step 2: Write the Code
Create a file named `main.py`:

```python
from fastapi import FastAPI
from pydantic import BaseModel

app = FastAPI()

# Data Model
class Item(BaseModel):
    name: str
    price: float

# GET Route
@app.get("/")
def read_root():
    return {"message": "Hello from FastAPI!"}

# POST Route
@app.post("/items/")
def create_item(item: Item):
    return {"item_name": item.name, "item_price": item.price}
```

## Step 3: Run it 🏃
```bash
uvicorn main:app --reload
```
*`main` is the file name, `app` is the FastAPI instance.*

## ✨ The Magic: Auto-Documentation
Open your browser and go to: `http://127.0.0.1:8000/docs`.
FastAPI automatically generates interactive **Swagger UI** for your API. You can test your endpoints directly from the browser!
