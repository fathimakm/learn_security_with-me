# security_learn_notes
## SSL 
*SSL Secure Socket Layer*
---
* It is a security protocol used to establish an encrypted link between a web server and a web browser.
- ensures that the data transmitted between the server and the browser remains private and secure.
+ SSL works through a process called encryption. Encryption converts the data into a code that can only be understood by the intended recipient, which is the Web Server.

**What happens when you connect to a website using SSL**
1. The web server sends its SSL certificate to your browser.__The certificate contains a public key, which is used to encrypt the data.__
2. The browser checks the SSL certificate to ensure it is valid and issued by a trusted authority. It also verifies that the website's domain matches the information in the certificate.
3. If the certificate is valid, your browser generates a session key, which is a unique encryption code.
4. Your browser encrypts the session key using the web server's public key and sends it back to the server.
5. The web server uses its private key to decrypt the session key.
6. Both the browser and the web server have the same session key. They use this key to encrypt and decrypt all the data transmitted between them during the session.

**Advantages of using SSL**
*  sensitive information like credit card numbers, login credentials, and personal data are protected from being intercepted and read by unauthorized individuals.
- ensure the confidentiality and integrity of data
_It's important to note that SSL has been succeeded by a newer protocol called Transport Layer Security (TLS). However, SSL is still commonly used as a general term to refer to both SSL and TLS protocols._**

***



