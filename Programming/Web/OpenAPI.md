---
date_added: 2025-02-24
tags:
  - web
---
Up: [REST API](REST%20API.md)
___
 OpenAPI is a specification for building [[API]]s It uses [YAML](YAML.md)
  
Key features of OpenAPI include:

1. **Standardization**: It provides a common framework for defining APIs, which helps in maintaining consistency across different services.
    
2. **Documentation**: OpenAPI can be used to automatically generate documentation for APIs, making it easier for developers to understand how to interact with them.
    
3. **Tooling**: There are many tools available that support OpenAPI, such as Swagger, which can generate client libraries, server stubs, and API documentation.
    
4. **Interoperability**: By adhering to a standard specification, APIs can be more easily integrated with other services and tools.
    
5. **Versioning**: OpenAPI supports versioning, allowing developers to manage changes to the API over time.
## Example
 ```cs
 openapi: 3.0.0
info:
  title: Library API
  description: A simple API to manage a library of books.
  version: 1.0.0
servers:
  - url: https://api.example.com/v1
paths:
  /books:
    get:
      summary: List all books
      responses:
        '200':
          description: A list of books
          content:
            application/json:
              schema:
                type: array
                items:
                  $ref: '#/components/schemas/Book'
    post:
      summary: Add a new book
      requestBody:
        description: Book to add
        required: true
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/Book'
      responses:
        '201':
          description: Book created
  /books/{bookId}:
    get:
      summary: Get a book by ID
      parameters:
        - name: bookId
          in: path
          required: true
          description: ID of the book to retrieve
          schema:
            type: string
      responses:
        '200':
          description: A single book
          content:
            application/json:
              schema:
                $ref: '#/components/schemas/Book'
        '404':
          description: Book not found
    delete:
      summary: Delete a book by ID
      parameters:
        - name: bookId
          in: path
          required: true
          description: ID of the book to delete
          schema:
            type: string
      responses:
        '204':
          description: Book deleted
        '404':
          description: Book not found
components:
  schemas:
    Book:
      type: object
      properties:
        id:
          type: string
          example: "1"
        title:
          type: string
          example: "The Great Gatsby"
        author:
          type: string
          example: "F. Scott Fitzgerald"
        publishedDate:
          type: string
          format: date
          example: "1925-04-10"
 ```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
