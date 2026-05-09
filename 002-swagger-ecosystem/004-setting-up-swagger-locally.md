## Setting up Swagger Locally

### 1. What “setting up Swagger locally” actually means

Before touching any commands, let’s be very clear about the goal.

When people say:

“Set up Swagger on my machine”

They usually mean one or more of these:

- Be able to **write and validate OpenAPI specs locally**
- Be able to **view Swagger UI locally**
- Be able to **use Swagger with a backend project**
- Be able to **share Swagger docs during development**

Swagger is not a single binary you install once.
You set it up in **pieces**, depending on what you want to do.

We will do this step by step.

---

### 2. What you need before starting

You need only three basic things:

- A computer with internet
- A terminal (Command Prompt, PowerShell, or Terminal)
- One of the following:
  - Node.js installed (recommended)
  - OR Docker installed (alternative)

We will first cover the **Node.js way**, because it is easiest for beginners.
Docker will be shown after.

---

### 3. Step 1: Verify Node.js is installed

Open your terminal and run:

    node -v
    npm -v

If you see version numbers, Node.js is installed.
If not, install Node.js from the official site and come back.

Swagger tools themselves do not require Node.js, but **running Swagger UI locally becomes very easy with it**.

---

### 4. Step 2: Create a workspace folder

Create a new folder anywhere on your machine:

    mkdir swagger-demo
    cd swagger-demo

This folder will hold:

- Your OpenAPI file
- Swagger UI setup
- Any helper files

---

### 5. Step 3: Create your first OpenAPI file

Inside the folder, create a file named:

    openapi.yaml

Add this minimal valid OpenAPI spec:

    openapi: 3.0.3
    info:
      title: Demo API
      version: 1.0.0
    paths:
      /health:
        get:
          summary: Health check
          responses:
            '200':
              description: API is healthy

This file is the **single source of truth**.
Everything Swagger does depends on this file.

---

### 6. Step 4: Validate the OpenAPI file locally

Swagger Editor can be used online, but you can also validate locally.

Install Swagger Editor locally using Docker is easiest, but for now we will validate visually using Swagger UI in the next step.

---

### 7. Step 5: Set up Swagger UI locally using Node.js

Initialize a small Node project:

    npm init -y

Install Swagger UI distribution:

    npm install swagger-ui-dist

This package contains the Swagger UI static files.

---

### 8. Step 6: Create a simple server to serve Swagger UI

Create a file named:

    server.js

Add the following code:

    const express = require("express");
    const path = require("path");

    const app = express();

    app.use("/swagger-ui", express.static(
      path.join(__dirname, "node_modules/swagger-ui-dist")
    ));

    app.get("/openapi.yaml", (req, res) => {
      res.sendFile(path.join(__dirname, "openapi.yaml"));
    });

    app.get("/", (req, res) => {
      res.redirect("/swagger-ui/?url=/openapi.yaml");
    });

    app.listen(3000, () => {
      console.log("Swagger UI running at http://localhost:3000");
    });

Install Express:

    npm install express

---

### 9. Step 7: Run Swagger UI locally

Start the server:

    node server.js

Open your browser and visit:

    http://localhost:3000

You should now see:

- Swagger UI running locally
- Your `/health` endpoint listed
- The ability to expand it and inspect responses

At this point, Swagger is successfully set up on your machine.

---

### 10. Step 8: Edit OpenAPI and see live updates

Now try this:

- Open `openapi.yaml`
- Add a new endpoint
- Refresh the browser

Swagger UI immediately reflects your changes.

This confirms:

- OpenAPI is the source of truth
- Swagger UI is only a visual layer

---

### 11. Optional: Using Swagger Editor locally with Docker

If you want a full OpenAPI editor locally, Docker is the easiest way.

Run:

    docker run -p 8080:8080 swaggerapi/swagger-editor

Open browser:

    http://localhost:8080

This gives you:

- Full OpenAPI editor
- Live validation
- Error highlighting
- YAML/JSON editing

This is optional but very useful.

---

### 12. How Swagger fits into real backend projects

In real backend work, the setup usually looks like this:

- Backend framework generates or serves `openapi.yaml`
- Swagger UI is hosted at `/docs` or `/swagger`
- OpenAPI file lives close to backend code
- CI validates the OpenAPI file
- Clients are generated from OpenAPI

The local setup you just did mirrors real production setups.

---

### 13. Common beginner mistakes to avoid

- Thinking Swagger is installed once globally
- Editing Swagger UI instead of OpenAPI
- Treating Swagger UI as the source of truth
- Forgetting to version OpenAPI files

Always remember:

OpenAPI defines.
Swagger visualizes.

---

### 14. Final mental checklist

After setup, you should clearly understand:

- Where `openapi.yaml` lives
- How Swagger UI reads it
- How changes flow from OpenAPI to UI
- That Swagger itself does not define APIs

Once this setup feels comfortable, the next step is integrating Swagger into a real backend framework like Express, Fastify, or Spring Boot.
