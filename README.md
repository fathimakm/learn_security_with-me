# security_learn_notes
## SSL Secure Socket Layer
---
* It is a security protocol used to establish an encrypted link between a web server and a web browser.
- ensures that the data transmitted between the server and the browser remains private and secure.
+ SSL works through a process called encryption. Encryption converts the data into a code that can only be understood by the intended recipient, which is the Web Server.

__What happens when you connect to a website using SSL__**
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

### Difference between SSL and TLS


* TLS can work with SSL-enabled systems, but SSL cannot work with TLS-only systems.
- SSL 3.0 had several security vulnerabilities. TLS was designed to address these vulnerabilities and provide enhanced security features.
+ TLS introduced new encryption algorithms, key exchange methods, and hash functions, offering stronger cryptographic options compared to SSL. This allows for a stronger and more secure connections.
* The TLS handshake process is slightly different from SSL. TLS added additional steps to enhance security during the handshake, such as improved authentication and key exchange methods.
- TLS introduced optimizations to improve performance. It reduces latency and connection setup time, making TLS connections faster compared to earlier versions.

***

## Digital Certicicate and Signatures

* Digital certificates and digital signatures are essential components of modern cryptographic systems used to ensure the authenticity, integrity, and security of digital information.


__Digital Certificate:__**
- A digital certificate is a digital document that verifies the identity of an entity, such as a website, organization, or individual, in an online environment.
+ It is issued by a trusted third party called a Certificate Authority (CA).

* Digital certificates contain the following information

1. Public Key : A digital certificate includes a public key that corresponds to a unique private key held by the entity.
The public key is used for encryption, authentication, and establishing secure connections.
2. Entity Information: The certificate contains information about the entity, such as its name, domain, and other relevant details. This information is used to verify the identity of the entity.
3. Certificate Authority Information: The digital certificate also includes information about the issuing CA, such as its name, digital signature, and public key. This allows the recipient to verify the authenticity and trustworthiness of the certificate.

__Digital Signature__**
+ cryptographic mechanism used to verify the integrity and authenticity of digital data.
- It provides assurance that the data has not been tampered with and that it originated from the claimed source
- Digital signatures work as follows:

1. Hashing: A cryptographic hash function takes the original data (message, file, etc.) and generates a fixed-length string of characters called a hash value or message digest. The hash function is designed in such a way that even a small change in the input data will produce a significantly different output.


2. Private Key Encryption: The hash value is then encrypted using the sender's private key. This encrypted hash value is the digital signature. The private key ensures that only the sender, with their unique private key, can create the signature.

3. Verification: The recipient of the data uses the sender's public key, obtained from their digital certificate, to decrypt the digital signature. This produces the original hash value.

4. Hash Comparison: The recipient independently calculates the hash value of the received data using the same hash function. They compare this calculated hash value with the decrypted hash value. If they match, it verifies that the data has not been modified during transmission and that it was indeed signed by the sender.

***
## SSRF server-side request forgery

- ability to manipulate a web application into sending unauthorized requests to a third-party site or resource is known as Server Side Request Forgery (SSRF).


+ Attack surface mapping is the process of analyzing an application's core functionality, business logic, and control flow to identify potential inputs or vectors through which an attacker could try to enter an application environment


- A service commonly exploited by attackers in third-party cloud environments is REST-based web services known as __cloud metadata endpoints__. If configured, a metadata endpoint provides programmatic access to a cloud server’s system configuration, networking details, authentication access keys, etc. 


-  IAM Roles?  
    *One way is to use the role to access resources that the attacker would not otherwise be able to access. For example, if an attacker has an IAM role that allows them to access the EC2 metadata service, they could use that role to make requests to other AWS services, such as S3 or DynamoDB.*

    *Another way to use IAM roles in SSRF attacks is to use the role to impersonate another user. For example, if an attacker has an IAM role that allows them to assume the role of another user, they could use that role to make requests to AWS services as if they were the other user.*


- The AWS Command Line Interface (AWS CLI) is an open-source tool that enables authorized users to interact with AWS services using a command-line shell.

- The NIST Cybersecurity Framework (NIST CSF) is a set of guidelines for mitigating organizational cybersecurity risks, published by the US National Institute of Standards and Technology based on existing standards, guidelines, and practices.

***
## Cybersecurity Tools

__Log__
    A record of events that occur in an organization system.
    ex: employees signing in to their computers.
    - helps identify vulnerabilities and potential security breaches.

1. __SIEM tool__
    *Security information and event management*
     - An application that collects and analyzes log data to monitor critical activities in an organization.
     - reduce the amount of data an analyst must review by providing alerts for specific types of threats, risks, and vulnerabilities.
     - provides a series of dashboards that visually organize data into categories, allowing users to select the data they wish to analyze.
     - SIEM tools also come with different hosting options, including on-premise and cloud. cloud-hosted version(recommended) tends to be easier to set up, use, and maintain than an on-premise version(used by less experienced people)
        examples of tools: splunk and chronicle
        __splunk__ is a data analysis platform. splunk enterprice provides SIEM solution.
        Splunk Enterprise is a self-hosted tool used to retain, analyze, and search an organization's log data.
        __Chronicle.__ is a cloud-native SIEM tool that stores security data for search and analysis. 
        Cloud-native means that Chronicle allows for fast delivery of new features.

2. __playbook__ is a manual that provides details about any operational action, such as how to respond before, during and after a security incident. 
     In a forensic analysis, there wil be two type of playbooks that would need to be handled.
     - chain of custody ( Chain of custody is the process of documenting evidence possession and control during an incident lifecycle. )
     - protecting and preserving evidence playbook (Protecting and preserving evidence is the process of properly working with fragile and volatile digital evidence. )


***

User Interface  (a program that allows a user to control the functions of the operating system)
GUI - Graphical user Interface
    - A GUI is a user interface that uses icons on the screen to manage different tasks on the computer. (ex: a start menu with program groups, a task bar for launching programs, and a desktop with icons and shortcuts)
    - allows only one request at a time
CLI - Command Line Interface is a text-based user interface that uses commands to interact with the computer. 
    - allows multiple request at a time
