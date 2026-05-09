## What is a Client

### 1. What is a client

A client is any code that calls your API.

A client is not the server.  
It is the consumer of the server.

Common examples of clients:

- Frontend JavaScript applications such as React or Next.js
- Mobile applications such as Android or iOS apps
- Another backend service calling your API
- CLI tools
- Automation scripts

In very simple terms:

    Your API = server  
    Code that calls it = client

Any program that sends HTTP requests to your API is a client.

---

### 2. What does a client normally do

Without any special tooling, a client must manually handle many responsibilities.

A typical client needs to:

- Build URLs correctly
- Attach required headers
- Serialize request bodies
- Send HTTP requests
- Parse HTTP responses
- Handle error responses
- Stay in sync when the API changes

A simplified JavaScript example of a manual client call:

    fetch("https://api.example.com/users", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
        Authorization: "Bearer token"
      },
      body: JSON.stringify({ name: "Alice" })
    });

This approach is:

- Repetitive
- Easy to get wrong
- Fragile when the API evolves

---

### 3. What problem client generation solves

As APIs grow, complexity increases:

- Many endpoints
- Many clients
- Many programming languages
- Multiple API versions

When client code is written manually, common problems appear:

- Typos in URLs or headers
- Missing required fields
- Incorrect data types
- Runtime errors
- Client code drifting away from backend behavior

Client generation removes humans from this repetitive and error-prone work.

---

### 4. What OpenAPI provides that enables this

An OpenAPI document fully describes how an API works.

It contains:

- All endpoints
- HTTP methods
- Path, query, and header parameters
- Request body schemas
- Response schemas
- Status codes
- Authentication rules

Because this description is machine-readable:

- A machine can understand how to call the API
- A machine can generate code that calls the API correctly

This is the key enabler of client generation.

---

### 5. What client generation actually means

Client generation means:

Automatically creating code that knows how to call your API correctly, based entirely on the OpenAPI specification.

There is:

- No guessing
- No manual typing
- No interpretation of documentation

The OpenAPI spec becomes the single source of truth, and machines generate client code directly from it.

---

### 6. Very simple mental model

If the OpenAPI document says:

    POST /users
    Request body:
      name: string
    Response:
      id: number
      name: string

A generated client might give you:

    api.createUser({ name: "Alice" });

Instead of manually writing:

    fetch("/users", { ... });

The generated client already knows:

- The correct URL
- The HTTP method
- Required fields
- The response structure

---

### 7. What a generated client usually contains

A generated client typically includes:

1. Typed functions  
   Example:  
   createUser(data: CreateUserRequest): Promise<User>

2. URL handling  
   - Base URL
   - Path parameters
   - Query parameters

3. Headers and authentication  
   - Automatically attaches tokens
   - Knows which auth scheme to use

4. Serialization  
   - Converts objects to JSON
   - Parses JSON responses into objects

5. Error handling  
   - Knows possible error responses
   - Exposes structured error information

This removes boilerplate and makes API usage safer and cleaner.

---

### 8. What tools generate clients

Many tools can generate client code from an OpenAPI document.

All of them follow the same idea:

- Read the OpenAPI specification
- Output client code in a target language

Common examples include:

- Swagger Codegen (legacy, but historically important)
- OpenAPI Generator
- Language-specific generators such as Go, Java, or TypeScript generators

Despite different implementations, the concept is the same everywhere.

---

### 9. Common beginner confusion

Common misunderstandings to avoid:

- Client generation replaces frontend logic  
  No. It only handles API calls.

- Generated code is magic  
  No. It is simply HTTP code generated safely and consistently.

- Only large companies use this  
  Many modern teams of all sizes rely on generated clients.

---

### 10. Final takeaway

Client generation means automatically creating safe, typed, reusable API-calling code from the OpenAPI specification.

It reduces bugs, removes repetitive work, and keeps clients in sync with the API as it evolves.
