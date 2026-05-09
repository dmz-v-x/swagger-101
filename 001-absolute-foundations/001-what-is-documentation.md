## Introduction to Documentation

### 1. Forget tech for a moment

Before we talk about Swagger, APIs, or software, we need to reset our thinking.

Think about **any product you have used in real life**:

- A phone  
- A washing machine  
- A game  
- A medicine  

Every one of these products comes with **instructions**.

Those instructions tell you:
- What the product is
- What it does
- How to use it safely
- What happens if you use it incorrectly

Those instructions are called **documentation**.

This idea exists *before* software, *before* APIs, and *before* Swagger.

Documentation is not a technical invention.  
It is a **human necessity**.

---

### 2. What is documentation in plain English

Let’s define documentation using very simple language.

Documentation is **written information** that explains:

- What something is  
- How it works  
- How to use it correctly  
- What to expect from it  

Nothing more.

No technical jargon.
No tools yet.
No frameworks yet.

If someone can read it and understand how to use something, that text is documentation.

---

### 3. Documentation answers four basic questions

Good documentation always answers **four core questions**.

If even one of these is missing, the documentation is weak.

The four questions are:

1. What is this?
2. Why does it exist?
3. How do I use it?
4. What happens if I use it wrong?

Let’s relate this to real life.

A medicine leaflet:
- What is this? A painkiller
- Why does it exist? To reduce pain
- How do I use it? One tablet after food
- What happens if I use it wrong? Side effects or overdose

The same logic applies to software.

---

### 4. Documentation in software very simple

In software, documentation explains things at a **human level**, not a machine level.

It explains:

- What a system does  
- What inputs it expects  
- What outputs it produces  
- What rules it follows  

Example written like a human explanation:

“This API lets you create users.  
You must send a name and an email.  
It returns a user ID.”

That explanation is documentation.

It does not show code.
It does not explain algorithms.
It explains **usage**.

---

### 5. Documentation is not the code

This is one of the most important ideas to understand early.

- Code is written for computers
- Documentation is written for humans

Even if your code feels clear to you today:

- A new developer does not know your intent
- An external user does not know how to use it
- Your future self will forget details

Code explains **how** something works internally.  
Documentation explains **what** it does and **how to use it**.

Documentation explains **intent**, not implementation.

---

### 6. Who documentation is for

Documentation is never written “for the system”.

It is written for **people**, such as:

- Other backend developers
- Frontend developers
- Mobile developers
- QA testers
- DevOps engineers
- Your future self

If a human needs to interact with, understand, test, or integrate your system, documentation is required.

No exceptions.

---

### 7. Very simple backend example

Imagine an API endpoint:

POST /users

Without documentation, a developer will ask:

- What fields should I send?
- Which fields are required?
- Is the data JSON or form data?
- What errors can occur?
- What status codes are returned?

With documentation, the developer sees:

- Input structure
- Output structure
- Error cases
- Example requests
- Example responses

The API itself did not change.  
Only the **documentation** changed.

Usability improved drastically.

---

### 8. Final simple definition

Documentation is human-readable information that explains how a system should be understood and used.

This concept is the foundation.

Swagger exists to **formalize and standardize this documentation for APIs**, which we will build on step by step next.
