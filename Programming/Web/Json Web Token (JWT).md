---
date_added: 2024-11-13
tags:
  - web
  - access
---
Up: [Authorization](Authorization.md)
___
 JWT is a standard for creating access tokens that can be used to authenticate [Web User](Web%20User.md). It is a compact and self-contained way for securely transmitting information between parties as a [[JSON]] object. This information can be verified and trusted because it is digitally signed. JWTs can be signed using a secret (with the HMAC algorithm) or a public/private key pair using RSA or ECDSA.
 
# Example
 ![](Pasted%20image%2020241113235613.png)
Format X.Y.Z where X is a header, Y is a payload, and Z is a signature.
Header contains the type of token and the signing algorithm being used.
Payload contains the claims. Claims are statements about an entity (typically, the user) and additional data.
Signature is used to verify that the sender of the JWT is who it says it is and to ensure that the message wasn't changed along the way.
# Usage
JWT is more secure in this example than cookies, because of encoding and inability to be changed on a client side.
![](Pasted%20image%2020241113235714.png)
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
