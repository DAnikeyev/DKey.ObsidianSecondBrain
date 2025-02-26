---
date_added: 2025-02-26
tags:
  - web
---
Up: [Web Security](Web%20Security.md)
___
 

The certificate helps verify the identity of the website. It assures users that they are communicating with the legitimate website and not an imposter.

An SSL/TLS certificate contains a public key, which is used to encrypt data. The corresponding private key, which is kept secure on the server, is used to decrypt data. This key pair is fundamental to the encryption process.

**Types of Certificates**: There are different types of SSL/TLS certificates, including:
    - **Domain Validated (DV)**: Validates only the domain ownership.
    - **Organization Validated (OV)**: Provides more assurance by validating the organization's identity.
    - **Extended Validation (EV)**: Offers the highest level of validation, often displaying a green address bar in browsers.


## **Certificate Authority (CA)**
 A trusted third-party organization that issues SSL/TLS certificates. CAs validate the identity of the certificate requester and vouch for the authenticity of the certificate.

In summary, a security certificate in HTTPS is essential for establishing a secure, encrypted connection between a client and a server, ensuring privacy, authentication, and data integrity during online communications.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
