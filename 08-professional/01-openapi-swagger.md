# OpenAPI / Swagger Specs 📜

**OpenAPI** (formerly Swagger) is the standard way to describe your API.
Instead of writing a PDF or Word doc, you write a **YAML** file that machines can read.

## Why use it?
1.  **Automation**: Generate clients (SDKs) and server stubs automatically.
2.  **Documentation**: Using tools like Swagger UI, it creates beautiful interactive docs.
3.  **Contract-First**: You agree on the API design *before* writing code.

## Example `openapi.yaml`
```yaml
openapi: 3.0.0
info:
  title: Sample API
  version: 1.0.0
paths:
  /users:
    get:
      summary: Returns a list of users.
      responses:
        '200':
          description: A JSON array of user names
          content:
            application/json:
              schema: 
                type: array
                items: 
                  type: string
```

## Tools
-   **Swagger Editor**: Online editor to write and preview YAML.
-   **Swagger UI**: Visualizes the YAML as a website (FastAPI does this automatically!).
