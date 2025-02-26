---
date_added: 2025-02-26
tags:
  - web
---
Up: [Http Request](Http%20Request.md)
___
 HEAD is almost identical to [Http GET](Http%20GET.md), but without the response body.
In other words, if GET /users returns a list of users, then HEAD /users will make the same request but will not return the list of users.

A HEAD request is useful for checking what a GET request will return before actually making a GET request - a HEAD request can read the Content-Length header to check the size of the file, without actually downloading the file.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
