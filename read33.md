# Authentication & Production Server



## What is JSON Web Token?
JSON Web Token (JWT) is an open standard (RFC 7519) that defines a compact and self-contained way for securely transmitting information between parties as a JSON object. 

## When should you use JSON Web Tokens?

- `Authorization`: This is the most common scenario for using JWT
- `Information Exchange`: JSON Web Tokens are a good way of securely transmitting information between parties.

## What is the JSON Web Token structure?

- Header

he header typically consists of two parts: the type of the token, which is JWT, and the signing algorithm being used, such as HMAC SHA256 or RSA.

- Payload

The second part of the token is the payload, which contains the claims. Claims are statements about an entity (typically, the user) and additional data. 

- Signature

To create the signature part you have to take the encoded header, the encoded payload, a secret, the algorithm specified in the header, and sign that.


## Why should we use JSON Web Tokens?
- As JSON is less verbose than XML, when it is encoded its size is also smaller, making JWT more compact than SAML. This makes JWT a good choice to be passed in HTML and HTTP environments.

- Security-wise, SWT can only be symmetrically signed by a shared secret using the HMAC algorithm. However, JWT and SAML tokens can use a public/private key pair in the form of a X.509 certificate for signing. Signing XML with XML Digital Signature without introducing obscure security holes is very difficult when compared to the simplicity of signing JSON.

- JSON parsers are common in most programming languages because they map directly to objects. Conversely, XML doesn’t have a natural document-to-object mapping. This makes it easier to work with JWT than SAML assertions.

- Regarding usage, JWT is used at Internet scale. This highlights the ease of client-side processing of the JSON Web token on multiple platforms, especially mobile.