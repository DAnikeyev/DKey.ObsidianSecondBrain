---
date_added: 2025-02-26
tags:
  - web
---
Up: [[HTTP]]
___
Also called HTTP method. Methods are not limited by the list and can be extended by the server.
1. Request Line:
    - Method (e.g., GET, POST, PUT, DELETE)
    - Request-URI (e.g., the URL of the resource being requested)
    - HTTP Version (e.g., HTTP/1.1 or HTTP/2)
2. Headers:
    - Key-value pairs that provide additional information about the request. For example, "Content-Type", "User-Agent", "Accept", etc.
3. Blank Line:
    - A blank line that indicates the end of the headers section.
4. Message Body (Optional):
    - Only present in certain requests (like POST or PUT) to carry data (e.g., form data, JSON payloads).

HTTP Response Components:

1. Status Line:
    
    - HTTP Version (e.g., HTTP/1.1)
    - Status Code (e.g., 200, 404, 500)
    - Reason Phrase (e.g., OK, Not Found, Internal Server Error)
2. Headers:
    
    - Key-value pairs providing metadata about the response, such as "Content-Type", "Content-Length", "Set-Cookie", etc.
3. Blank Line:
    
    - A blank line that separates the headers from the body.
4. Message Body (Optional):
    
    - Contains the resource data (e.g., an HTML document, JSON, images) if applicable, based on the status and type of response.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
