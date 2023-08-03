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
   
2. Browser needs to know how to reach the server, that is done with the help of DNS lookup (Domian name system)
DNS translates domain name to ip addresses.


* To makenDNS look up fast, DNS information is heavily cached
Browser caches it for a period of time (so looks up ip address in cache) > if not found > browser asks the operating system for it > bcs os also stores dns cache for a short period of time > if not found > browser makes a query out to the internet to a DNS resolver > this sets off a chain of the request until the IP address is solved.
   
3. After the browser gets the IP address, the browser establishes a TCP connection with the server (using TCP Handshake)

* TO keep the loading process faster, modern browsers use keep-alive connection to try to reuse an established TCP connection to the server

* If the protocol is HTTPS, establishing a connection is more evolved > SSL/TLS handshake is used > to establish an encrypted connection between the browser and server

* SSl/TLS handshake is expensive >ao to lower the cost > browser uses tricks like SSL session resumption

4. Finally, Browser sends HTTP request to the server over the established TCP connection

5. The server processes the request and sends back a HTTP response

6. The browser receives the response and renders HTML content, images javascript bundle etc
