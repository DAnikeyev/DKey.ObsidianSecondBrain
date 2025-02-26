---
date_added: 2025-02-26
tags:
  - web
---
Up: [Http Request](Http%20Request.md)
___
 POST is used to send data to a server to create/update a resource.
 - POST requests are never cached
- POST requests do not remain in the browser history
- POST requests cannot be bookmarked
- POST requests have no restrictions on data length

## Comparison

| Feature                        | GET                                                                                           | POST                                                                                           |
|--------------------------------|-----------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|
| BACK button/Reload             | Harmless                                                                                      | Data will be re-submitted (the browser should alert the user that the data are about to be re-submitted) |
| Bookmarked                     | Can be bookmarked                                                                             | Cannot be bookmarked                                                                           |
| Cached                         | Can be cached                                                                                 | Not cached                                                                                     |
| Encoding type                  | application/x-www-form-urlencoded                                                             | application/x-www-form-urlencoded or multipart/form-data. Use multipart encoding for binary data |
| History                        | Parameters remain in browser history                                                          | Parameters are not saved in browser history                                                    |
| Restrictions on data length    | Yes, when sending data, the GET method adds the data to the URL; and the length of a URL is limited (maximum URL length is 2048 characters) | No restrictions                                                                                |
| Restrictions on data type      | Only ASCII characters allowed                                                                 | No restrictions. Binary data is also allowed                                                   |
| Security                       | GET is less secure compared to POST because data sent is part of the URL. Never use GET when sending passwords or other sensitive information! | POST is a little safer than GET because the parameters are not stored in browser history or in web server logs |
| Visibility                     | Data is visible to everyone in the URL                                                        | Data is not displayed in the URL                                                               |

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
