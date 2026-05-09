## Problems with handwritten docs

### 1. First what handwritten docs means

Handwritten documentation usually refers to documentation that humans write and maintain manually.

Common examples include:

- README.md files
- Markdown documentation files
- Wiki pages
- Google Docs
- Notion pages

These documents are:

- Written manually
- Updated manually
- Maintained by humans

At first glance, this approach feels reasonable and simple.

---

### 2. Why handwritten docs feel okay at the beginning

In small projects, handwritten documentation often feels sufficient.

This is because:

- There are only a few API endpoints
- The team size is small
- Changes happen infrequently

As a result:

- The README looks accurate
- Everyone understands how the API works
- Documentation feels good enough

This is why beginners often think:

“Why do we need Swagger at all?”

At a small scale, handwritten docs appear to work.

---

### 3. Problem 1 docs drift from reality

This is the biggest and most dangerous problem.

Code changes very fast:

- New fields are added
- Validation rules are updated
- Error responses change
- Authentication rules change

Handwritten documentation, however:

- Is not enforced
- Is not validated
- Is easy to forget updating

The result is simple but serious.

The documentation starts lying.

Lying documentation is worse than no documentation because it actively misleads developers.

---

### 4. Problem 2 no single source of truth

With handwritten documentation:

- Code lives in one place
- Documentation lives in another place

There is no guarantee that both stay in sync.

This creates confusion:

- Is the code correct?
- Or is the documentation correct?

When developers cannot trust the documentation, they stop using it entirely.

---

### 5. Problem 3 no interactivity

Markdown documentation is read-only.

You can:

- Read it

You cannot:

- Try requests
- Send real data
- Validate assumptions

Developers still need extra tools like:

- Postman
- curl
- Custom scripts

Handwritten docs describe work, but they do not reduce work.

---

### 6. Problem 4 hard to maintain consistency

Imagine an API with 50 endpoints.

In handwritten documentation:

- One endpoint returns `{ error: string }`
- Another returns `{ message: string }`
- Another returns `{ errors: [] }`

There is no system enforcing:

- Consistent response formats
- Consistent error structures
- Consistent status codes

Swagger and OpenAPI enforce structure.

Markdown does not.

---

### 7. Problem 5 hard for machines to understand

Handwritten documentation is:

- Human-readable
- Not machine-readable

Because machines cannot understand it, you cannot easily build:

- Automatic validation
- API client generation
- Contract-based testing
- Mock servers
- CI checks

Modern systems require documentation that both humans and machines can understand.

---

### 8. Problem 6 poor onboarding experience

When a new developer joins the team:

- They read the README
- They try the API
- They encounter undocumented errors
- They ask questions
- They lose confidence in the documentation

This slows onboarding and increases dependency on senior developers.

---

### 9. Problem 7 no guarantee docs are complete

Handwritten documentation often misses important details such as:

- Error cases
- Edge cases
- Authentication rules
- Rate limits
- Required headers

Swagger-based documentation forces you to define these details explicitly.

This leads to more complete and reliable documentation.

---

### 10. Final comparison to remember

Handwritten documentation describes how the API should work.

Swagger-based documentation shows how the API does work.

This difference is the reason modern API teams rely on Swagger and OpenAPI.
