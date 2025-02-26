---
date_added: 2025-02-26
tags:
  - web
---
Up: [Http Request](Http%20Request.md)
___
 is a component of the header section of request and response messages. 
 Headers are **key-value pairs** that provide essential information about the request or response, or about the object sent in the message body.

### Simple text-based format
Header-Name: Header-Value

## Common Headers

is document outlines some of the key HTTP headers that are commonly used in web communication.

### Request Headers

- **Accept**  
    Specifies the media types that the client is willing to receive.  
    _Example:_ `Accept: text/html, application/json`
    
- **Accept-Encoding**  
    Indicates the content encodings (e.g., gzip, deflate) that the client can understand.
    
- **Authorization**  
    Contains credentials for authenticating the client to the server.  
    _Example:_ `Authorization: Bearer <token>`
    
- **Cache-Control**  
    Provides directives for caching mechanisms in both requests and responses.
    
- **Content-Type**  
    Indicates the media type of the body of the request.  
    _Example:_ `Content-Type: application/json`
    
- **User-Agent**  
    Contains information about the client software making the request.  
    _Example:_ `User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64)`
    
- **Referer** (sometimes spelled **Referrer**)  
    Provides the address of the previous web page from which a request was made.


## Response Headers

- **Content-Type**  
    Specifies the media type of the resource returned by the server.  
    _Example:_ `Content-Type: text/html; charset=utf-8`
    
- **Content-Length**  
    Indicates the size of the response body in bytes.
    
- **ETag**  
    Provides a unique identifier for a specific version of the returned resource, useful for cache validation.
    
- **Cache-Control**  
    Directs how caching should be managed by browsers and intermediate caches.
    
- **Set-Cookie**  
    Sends cookies from the server to the client to maintain session state or store other relevant data.
    
- **Location**  
    Used for redirection, indicating the URL to which the client should navigate.
    
- **Server**  
    Provides information about the server handling the request.
    
- **WWW-Authenticate**  
    Sent along with a 401 Unauthorized response, detailing the authentication scheme that should be used.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
