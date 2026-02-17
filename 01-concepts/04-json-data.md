# JSON Data Explained 📦

**JSON (JavaScript Object Notation)** is the standard language APIs use to talk.

## Why JSON?
It is **lightweight** and easy for both humans and machines to read.
It looks almost exactly like a **Python Dictionary** or a **JavaScript Object**.

## Syntax Rules
1.  Data is in name/value pairs: `"name": "Raja"`
2.  Data is separated by commas: `"age": 25, "city": "New York"`
3.  Curly braces `{}` hold objects.
4.  Square brackets `[]` hold arrays (lists).

## Example
```json
{
  "user": {
    "id": 101,
    "name": "Raja Venkatesh",
    "is_student": true,
    "skills": ["Java", "Python", "API"],
    "address": null
  }
}
```

## Mapping to Your Languages
-   **JavaScript**: `JSON.parse()` turns this string into a standard JS Object.
-   **Python**: `json.loads()` turns this string into a `dict`.
-   **Java**: Libraries like Jackson or Gson map this to a `Class`.
