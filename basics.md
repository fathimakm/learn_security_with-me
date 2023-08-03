# URL
Universe Resource Locator

`https://example.com/product/electric/phone`
- it has 4 parts:
1. Scheme: tells the browser to connect to the server using http, https protocols
2. Domain: it is the domain name of the site (example.com)
3. path:  (product/electric)
4. Resource  (phone)

***
# working
1. user enters URL
   
2. Browser needs to know how to reach the server, that is done with the help of __DNS lookup (Domian name system)__
DNS translates domain name to ip addresses.


* To makenDNS look up fast, DNS information is heavily cached
- Browser caches it for a period of time (so looks up ip address in cache) > if not found > browser asks the operating system for it > bcs os also stores dns cache for a short period of time > if not found > browser makes a query out to the internet to a DNS resolver > this sets off a chain of the request until the IP address is solved.
   
3. After the browser gets the IP address, the browser establishes a TCP connection with the server (using TCP Handshake)

* TO keep the loading process faster, modern browsers use keep-alive connection to try to reuse an established TCP connection to the server

* If the protocol is HTTPS, establishing a connection is more evolved > SSL/TLS handshake is used > to establish an encrypted connection between the browser and server

* SSl/TLS handshake is expensive >ao to lower the cost > browser uses tricks like SSL session resumption

4. Finally, Browser sends HTTP request to the server over the established TCP connection

5. The server processes the request and sends back a HTTP response

6. The browser receives the response and renders HTML content, images javascript bundle etc

***
# SSL/TLS, HTTPs :)

## HTTPS

- If we use http(hyper text tranfer protocol), the information can be read by anyone who intercepts it. 
This limitation is solved by HTTPS.
- If we use HTTPS, the data send over the internet is unreadable by anyone other than the sender and reciever
- HTTPS is an extension of the HTTP protocol
- With HTTPS, the data is send in an encrypted form using __TLS__ , __Transport Layer Security__ (if an attacker tried to intercept > they would only get jumbled unreabdable data)



## TLS 

steps:
1. __TLS HAndshake__
 The browser establishes a tcp connection with the server 
`TCP SYN, TCP SYN + ACK, TCP ACK` (with these three steps, connection is established)

2. __Certificate Check__
    * the browser `client hello` which contains > 1. what TLS version it can support (TLS 1.2, TLS 1.3 etc) > 2. which cyber suite browser supports (cyber suit is a set of encryption algorithms to use to encrypt data)

    * after server receives client hello > it sends __two__ things> 1. it can choose cyber suite and the TLS version based on the option it got from the browser > server sends those info in the `server hello` to the browser. 2. The server also send `certificate` > which contains a lot of things > it contains public key for the server.

        -  The client uses public key in something called **assymmentric encryption** (A piece of data that is encypted using public key can only be decrypted by the private key)

    * `server hello done`


3. __Key Exchange__

    * The step where the client and the server comes up with a share encryption key to use to encrypt data
    * the data send by the client is encrypteed using server's public key and can only be decryped by server's private key
    * this is how the client sneds an encryption key safely to server
    * All this is done in the `client key exchange` message. >exact details vary depending on the cyber suite used.

    ### RSA
    1. the client generates an encryption key (aka session key) > this  generates session key is encrypted using server's public key > Encrypted session key is send over to the internet

    2. The server recieves th encryped session key and decrypts it with server's private key 


4. Data Transmission

    - Now both client and server holds the same session key > This is where the session key and the agreed upon cyber suite is used to send encrypted data back and forth in a secure bi-directional channel.

* **Asymmetric encryption is computationally expensive**, so it is not suitable for bulk data transmission

 In the above example, we use TLS 1.2 version and encryption algorithm as RSA. TLS 1.2 uses two network round trips to complete

 TLV 1.3 is the latest version and is supportes on all major browsers, RSA is not supportes by TLS 1.3, rather diffie -hellman is used for exchanging session keys. TLS 1.3 optimizes the handshake to reduce the number of network round trips to one.


# TCP

**Transmission control Protocol** 
* Connection Oriented protocol > it establishes a connection between two devices before transfering data and maintains that connection throughout the tranfer process.

- used when no loss of data is tolerated
- ex:surfing the web(HTTPS), sending email (SMTS), Transferring Files(FTP)

To establish connection - 3 way handshke 
`Syn, Syn-Ack, Ack`
To disconnect
`Fin, Ack`


# UDP

**Connectionless Protocol**- (aka Fire and Target since it doesn't gaurantee that all data is successfully transferred) 

- used when some data loss is acceptable and speed is important

- ex: Video, audio, online games

