
# Cookies

Cookies are small text files stored by websites on a user's computer or device to identify them and store information like login sessions, site preferences, shopping cart items etc.



# JSON Web Token

WWW.jsonwebtoken.io  is used to decode json token

- decoded part has 3 parts:

Header, Payload, Signature
All are seperated by a dot

- In Header, there will be type of token and hashing algorithm used.
- In payload, we gwt status code, if any data was passed like id, email , password etc.
- if we find the method of hashing applied to password, we can decode the pass( ex if MD5, use MD5 decryption)



#### Cookie stealing
- the malicious practice of obtaining unauthorized access to cookies stored on a user's device and using them to gain access to the user's accounts or sensitive information


- __if we set httponly as false__, then cookike can be accessed by client side javascript, becomes vulnerable to xss
- an attacker can use JavaScript to read the cookie value and steal sensitive information like session IDs.
- With HttpOnly=false, the cookie value is transmitted in clear text over the network and can be viewed by sniffing the traffic.
- Session hijacking becomes easier
- exposed to man-in-the-middle attacks. A MITM attacker can intercept and read the cookie if it is not HttpOnly.

directory discovery tools like bust or go bust