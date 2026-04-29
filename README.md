# JavaScript Fetch API HTTP Client Architecture

> A practical case study demonstrating how modern web applications use the Fetch API to perform HTTP requests and manage asynchronous data flows.

![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-yellow?style=for-the-badge&logo=javascript)
![Fetch](https://img.shields.io/badge/API-Fetch-blue?style=for-the-badge)
![HTTP](https://img.shields.io/badge/Protocol-HTTP-green?style=for-the-badge)
![Async](https://img.shields.io/badge/Async-await-purple?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Case%20Study-black?style=for-the-badge)

---

## Overview

The Fetch API is the modern standard for making HTTP requests in JavaScript.

It replaces legacy approaches like XMLHttpRequest and enables:

- Cleaner syntax
- Promise-based architecture
- Better async control
- Integration with async/await

---

## The Problem

Legacy HTTP communication:

```text
Verbose code
Callback-based logic
Hard error handling
Low readability
```

Fetch solves this with a modern, promise-based approach.

## Architecture

```text
User Action
    ↓
JavaScript Function
    ↓
Fetch API
    ↓
HTTP Request
    ↓
Server
    ↓
HTTP Response
    ↓
JSON Parsing
    ↓
UI Update
```

## Request Flow

```text
1. Trigger action
2. Call fetch()
3. Await response
4. Parse JSON
5. Update UI
```

## Example: GET Request

```js
async function carregarUsuarios() {
  const response = await fetch("https://reqres.in/api/users");

  if (!response.ok) {
    throw new Error("Erro na requisição");
  }

  const data = await response.json();

  console.log(data);
}
```

```js
async function criarUsuario() {
  const response = await fetch("https://reqres.in/api/users", {
    method: "POST",
    headers: {
      "Content-Type": "application/json"
    },
    body: JSON.stringify({
      nome: "Thiago",
      email: "thiago@email.com"
    })
  });

  const data = await response.json();

  console.log(data);
}
```

| Feature | XMLHttpRequest | Fetch |
| :--- | :--- | :--- |
| **Syntax** | Complex | Clean |
| **Promises** | No | Yes |
| **Async/Await** | No | Yes |
| **Streaming** | Limited | Supported |
| **Modern Standard** | No | Yes |

## Architecture Insight

```text
Fetch = HTTP client layer
Async/Await = control flow
JSON = data format
UI = presentation layer
```

## Real Engineering Use Cases

```text
API integration
Frontend-backend communication
Data synchronization
Microservices communication
Third-party APIs
```

## Error Handling Pattern

```js
async function fetchData() {
  try {
    const response = await fetch("https://reqres.in/api/users");

    if (!response.ok) {
      throw new Error(`HTTP error: ${response.status}`);
    }

    return await response.json();

  } catch (error) {
    console.error(error);
  }
}
```

## Performance Considerations

```text
Avoid unnecessary requests
Use caching strategies
Batch requests
Handle loading states
```

## Common Mistakes

❌ Not checking response.ok
❌ Ignoring error handling
❌ Blocking UI
❌ Mixing network and UI logic
❌ Not handling JSON parsing errors

## Advanced Topics
```text
Request cancellation (AbortController)
Retry strategies
Exponential backoff
Caching (LocalStorage / IndexedDB)
Streaming responses
```

## Demo
## Layout Fetch

[![Assista ao vídeo do Fetch](https://github.com/Thiago771414/imagensProjetos/blob/main/slices/mobile/fetch.png)](https://youtu.be/w6dAdzXYJrU)

*Click on the image above to watch the demonstration.*

---

## Summary
Fetch is the foundation of modern HTTP communication in the browser.
```text
Request = intent
Fetch = transport
Response = data
UI = representation
```

## Author

Thiago Lima
Software Engineer | System Design | API Communication
