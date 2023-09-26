
# Cookies

- Cookies are used to store session information and other dta sent from the server on the client side

- Cookies are small text files stored by websites on a user's computer or device to identify them and store information like login sessions, site preferences, shopping cart items etc.

## Cookie attributes

1. session iD - random strin that is used for session management
2. expires: exp. date for the cookie
3. Domain - specifies the domain where the cookie can be used
4. path - resource or path where this cookie is valid
5. httponly - if enabled, this prevents the cookie from being accessed via JS on the client side
6. secure - if enabled, the cookie will be send only over HTTPS
7. isSession - if enabled, forces the cookie to expire at the end of session (can be set manually)

* Session ID - unique identifiers that are used to identify users with their respective sessions (stored in cookies , URL) -> they are random and unique, send securely, lengthy, never reused

********

# JSON Web Token

WWW.jsonwebtoken.io  is used to decode json token

- decoded part has 3 parts:

Header, Payload, Signature
All are seperated by a dot

- In Header, there will be type of token and hashing algorithm used.
- In payload, we gwt status code, if any data was passed like id, email , password etc.
- if we find the method of hashing applied to password (hash identifier), we can decode the pass( ex if MD5, use MD5 decryption)
- how to recognize if it is a MD5 hashing ( 32 characters long, hexadecimal characters, which are 0-9 and A-F, No special characters etc )



#### Cookie stealing
- the malicious practice of obtaining unauthorized access to cookies stored on a user's device and using them to gain access to the user's accounts or sensitive information


- __if we set httponly as false__, then cookie can be accessed by client side javascript, becomes vulnerable to xss
- an attacker can use JavaScript to read the cookie value and steal sensitive information like session IDs.
- With HttpOnly=false, the cookie value is transmitted in clear text over the network and can be viewed by sniffing the traffic.
- Session hijacking becomes easier
- exposed to man-in-the-middle attacks. A MITM attacker can intercept and read the cookie if it is not HttpOnly.

directory discovery tools like bust or go bust

## Spidering
 means to identify scope


 __Web Application Firewall Detection With WAFW00F__
