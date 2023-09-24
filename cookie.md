





# JSON Web Token

WWW.jsonwebtoken.io  is used to decode json token

- decoded part has 3 parts:

Header, Payload, Signature
All are seperated by a dot

- In Header, there will be type of token and hashing algorithm used.
- In payload, we gwt status code, if any data was passed like id, email , password etc.
- if we find the method of hashing applied to password, we can decode the pass( ex if MD5, use MD5 decryption)