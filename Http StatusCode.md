# 🌐 HTTP Status Codes for Spring Boot and Web APIs

## ✅ 1xx – Informational
These codes indicate a provisional response.

- **100 Continue** – Initial part of request received; client should continue.
- **101 Switching Protocols** – Server agrees to switch protocols (e.g., WebSockets).

---

## 🟢 2xx – Success
The request was successfully received, understood, and accepted.

- **200 OK** – ✅ Standard response for successful GET, POST, PUT, DELETE.
- **201 Created** – ✅ Resource successfully created (commonly used with POST).
- **202 Accepted** – Request accepted for processing, but not completed yet.
- **204 No Content** – ✅ Successful request but no content to return (used for DELETE).

---

## 🟡 3xx – Redirection
Client must take additional action to complete the request.

- **301 Moved Permanently** – Resource permanently moved to a new URL.
- **302 Found** – Resource temporarily moved to a different URL.
- **304 Not Modified** – Cached version is still valid; no need to re-download.

---

## 🔴 4xx – Client Errors
The request has a problem on the **client side** (bad input, unauthorized, etc.).

- **400 Bad Request** – 🚫 Malformed request (e.g., missing fields or invalid JSON).
- **401 Unauthorized** – 🔒 Authentication required or failed (e.g., invalid token).
- **403 Forbidden** – 🛑 User is authenticated but not allowed to access this resource.
- **404 Not Found** – ❌ Resource doesn't exist at the requested URL.
- **405 Method Not Allowed** – Using wrong HTTP method (e.g., PUT instead of GET).
- **409 Conflict** – Conflict in request (e.g., duplicate resource creation).
- **429 Too Many Requests** – Client has sent too many requests in a given time (rate limiting).

---

## 🔥 5xx – Server Errors
These errors mean something went wrong **on the server side**.

- **500 Internal Server Error** – 🧨 Generic error (e.g., null pointer, crash).
- **501 Not Implemented** – Server doesn't support the functionality required.
- **502 Bad Gateway** – Server received an invalid response from upstream server.
- **503 Service Unavailable** – Server temporarily unable to handle the request (overloaded or down).
- **504 Gateway Timeout** – Server didn’t receive a timely response from another server.

---

## ✅ Quick Summary Table

| Code | Meaning                  | When to Expect It                                |
|------|---------------------------|--------------------------------------------------|
| 200  | OK                        | Request succeeded (GET, POST, etc.)             |
| 201  | Created                   | New resource created (POST)                     |
| 202  | Accepted                  | Request received, processing later              |
| 204  | No Content                | Success, but no data to return (e.g., DELETE)   |
| 400  | Bad Request               | Invalid input / request format                  |
| 401  | Unauthorized              | Missing or invalid authentication               |
| 403  | Forbidden                 | Access denied despite authentication            |
| 404  | Not Found                 | URL or resource doesn’t exist                   |
| 409  | Conflict                  | Duplicate or conflicting data                   |
| 500  | Internal Server Error     | Generic server-side error                       |
| 503  | Service Unavailable       | Server overloaded, under maintenance, or down   |

---

> **Tip:** In Spring Boot, you can handle and customize these status codes using `@ControllerAdvice` and `@ExceptionHandler` or customize `ErrorController`.

