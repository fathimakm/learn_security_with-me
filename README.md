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

__User Interface__  (a program that allows a user to control the functions of the operating system)
GUI - Graphical user Interface
    - A GUI is a user interface that uses icons on the screen to manage different tasks on the computer. (ex: a start menu with program groups, a task bar for launching programs, and a desktop with icons and shortcuts)
    - allows only one request at a time
CLI - Command Line Interface is a text-based user interface that uses commands to interact with the computer. 
    - allows multiple request at a time


__Linux__
- components
    -applictaion(program that performs a specific tasks)
    -shell( processes commands and outputs the results)
    -Filesystem Hierarchy Standard, or FHS(organizes data). 
    -kernel(manages processes and memory)
    -hardware(physical componemt of a computer ex: CPU, mouse, keyboard)

- kali linux derived from debian, has pre-installed tools related to penetration testing and digital forensics.(parrot also have tools for penetration)

+ KALI LINUX, Ubuntu, Parrot, Red Hat(not free, subscription based), and CentOS are all widely used Linux distributions.

KALI LINUX, Ubuntu, Parrot - debian based, open source

- penetration testing tools in Kali linux
    -metasploit(to look for and exploit vulnerabilities on machines.)
    -burpsuite(to look for and exploit vulnerabilities on machines.)
    -john the ripper( tool used to guess passwords)


- Digital forensics is the process of collecting and analyzing data to determine what has happened after an attack.
    tools:
        1. tcpdump(used to capture network traffic)
        2.  Wireshark. It has a graphical user interface that can be used to analyze live and captured network traffic
        3. Autopsy is a forensic tool used to analyze hard drives and smartphones.

- Advanced package tool

    - Suricata, a network analysis tool used for intrusion detection
    - tcpdump application. This is a command-line tool that can be used to capture network traffic in a Linux Bash shell.

    sudo apt install (application name)
    sudo apt remove (application name)
    apt list --installed 
    echo 
    expr
    clear

    __cat__ command displays the content of a file
    cat access.txt
    __head__ command displays just the beginning of a file, by default 10 lines
    __tail__ command can be used to display just the end of a file, by default 10 lines
    __less__ command returns the content of a file one page at a time. 

     The __grep__ command searches a specified file and returns all lines in the file containing a specified string. The grep command commonly takes two arguments: a specific string to search for and a specific file to search through. (grep OS updates.txt returns all lines containing OS in the updates.txt file. )

     grep OS updates.txt

     __Piping__ sends the standard output of one command as standard input to another command for further processing. pipe character (|)

      ls /home/analyst/reports | grep users
      returns the file and directory names in the reports directory that contain users.

    The __find__ command searches for directories and files that meet specified criteria.
     find /home/analyst/projects searches for everything starting at the projects directory. 

    __Options__ modify the behavior of a command and commonly begin with a hyphen (-). 
    1.    -name and -iname
         -name is case-sensitive, and -iname is not. 
             ex: find /home/analyst/projects -name "*log*"
            find /home/analyst/projects -iname "*log*"
        The specific string you are searching for must be entered in quotes after the -name or -iname options.
        * is used as a wildcard to represent zero or more unknown characters.

    
    2.    -mtime (to find files or directories last modified within a certain time frame)
        find /home/analyst/projects -mtime -3 //returns file or directories that was modfied within the last 3 days.

        -mtime +1 // last modified more than one day ago 
        -mtime -1 //  last modified less than one day ago

         -mmin //  search on minutes rather than days



    mkdir  // creates a new directory
    rmdir // removes, deletes a directory
    touch // creates a new file
    rm // removes, deletes a file
    mv // moving a file
    cp //copying a file
    nano s a command line file editor  Ex: nano report.txt
    to save a file in anano ctrl+o, to exit ctrl+x

    __> and >>__
    In addition to the pipe (|), use right angle bracket (>) and double right angle bracket (>>) operators to redirect standard output.

    > overwrites your existing file, and >> adds your content to the end of the existing file instead of overwriting it.

    When you’re inside the directory containing the permissions.txt file, entering echo "last updated date" >> permissions.txt adds the string “last updated date” to the file contents. Entering echo "time" > permissions.txt after this command overwrites the entire file contents of permissions.txt with the string “time”.

     Both the > and >> operators will create a new file if one doesn’t already exist with your specified name.


---


### Permissions

* Types of permission
__rwx__
user(owner), group, global(other)
rwxrwxrwx

-rwxrwxrwx //normal file starts with hyphen
drwxrwxrwx //directory

-l // to display permissions
ls -l //displays files and their respective permissions
-a // displays all files including hidden files
ls -la // displays all files including hidden ones and their respective functions.


- changing permissions
__chmod__ 
changes permissions on files and directories
user -u
group -g
other -o

ex:  chmod g-x, o+r access.txt

chmod 760 access.txt
user -rwx, g-rw, o-no access



- *__root user:__* A user with high priviliges to modify the system. ( can create, modify, or delete any file and run any program.)(only root user can add new users)
problems: security issues, accountability, irreversable mistakes.


- __sudo__  - A command that temporarily grants elevated permissions to specific users.
sudo comes from super-user-do and lets you execute commands as an elevated user without having to sign in and out of another account.

 sudoers file - a configuration file to use sudo.

*useradd* // add a user to the s/m
sudo useradd abcname


*userdel* // deletes a user
sudo userdel abcname

-g: Sets the user’s default group, also called their primary group

sudo useradd -g security abc1 // adds a new user abc1 and assigns their primary group to be security


-G: Adds the user to additional groups, also called supplemental or secondary groups

sudo useradd -G finance,admin abc1 //  adds a new user and adds them to the existing finance and admin groups.


__usermod__ - modifies existing user accounts
-g and -G can be used with usermod

sudo usermod -g executive abc1 //  changed primary group to the executive group


sudo usermod -a -G marketing fgarcia  // to use -G , -a is also used (add user to the secondary marketing group.)(Using -a with -G ensures that the new groups are added but existing groups are not replaced.)


-d: Changes the user’s home directory.
-l: Changes the user’s login name.
-L: Locks the account so the user can’t log in.

__chown__
changes ownership of a file or directory (can change user or group ownership. )


sudo chown abc1 access.txt.  // ownership changed to abc1
sudo chown :security access.txt  //enter a colon (:) before security to designate it as a group name.




__man__ displays information on other commands and how they work (like an documentation or manual)

man chown

 __whatis__ command displays a description of a command on a single line

whatis userdel

 __apropos__ command searches the man page descriptions for a specified string.

apropos password
apropos -a change password       //(include the -a option to search for multiple words.)



***


__Database and SQL__
DB - organized collection of information or data 


Relational DB - A structured database containing tables that are related to each other.



- Tables contain rows(records) and columns
    - if two tables have common column they are connected
    - The columns that relate two tables to each other are called keys (there are two type of keys)

    * The primary key refers to a column where every row has a unique entry. The primary key must not have any duplicate values, or any null or empty values. 

    * The foreign key is a column in a table that is a primary key in another table. Foreign keys, can have empty values and duplicates.

    * table can only have one primary key, but multiple foreign keys.

SQL Structured Query Language
A progaramming language used to create, interact and request information from a database.

Query - request for data from table or combination of tables
`
SELECT customerid, city, country
FROM customers
ORDER BY city;


(ASC,DESC)



SELECT customerid, city, country
FROM customers
ORDER BY country, city;

SELECT firstname, lastname, title, email
FROM employees
WHERE title = 'IT Staff';
`

*Filtering for patterns*
`wildcard % and _
            - percentage sign substitutes for any number of other characters
            - The underscore symbol only substitutes for one other character
`    
    

LIKE operator
    to apply wildcards to the filter, you need to use the LIKE operator instead of an equals sign (=). 
        `SELECT lastname, firstname, title, email
FROM employees
WHERE title LIKE 'IT%';`



BETWEEN is used with AND operator
`SELECT firstname, lastname, hiredate
FROM employees
WHERE hiredate BETWEEN '2002-01-01' AND '2003-01-01';`


when we filter for strings, dates, and times, we use quotation marks to specify what we're looking for. However, for numbers, we don't use quotation marks.



*AND*
`SELECT firstname, lastname, email, country, supportrepid
FROM customers
WHERE supportrepid = 5 AND country = 'USA';
`

*OR*
`SELECT firstname, lastname, email, country
FROM customers
WHERE country = 'Canada' OR country = 'USA';`

*NOT*
`SELECT firstname, lastname, email, country
FROM customers
WHERE NOT country = 'USA';`


`SELECT firstname, lastname, email, country
FROM customers
WHERE NOT country = 'Canada' AND NOT country = 'USA';`

__Join__


SELECT *
FROM employees
INNER JOIN machines ON employees.device_id = machines.device_id; 

ON keyword and the = operator to indicate the column you are joining the tables on. 

`SELECT *
FROM employees
RIGHT JOIN machines ON employees.device_id = machines.device_id;`



`SELECT *
FROM machines
RIGHT JOIN employees ON employees.device_id = machines.device_id;`

-All joins return the records that match on a specified column. INNER JOIN will return only these records. Outer joins also return all other records from one or both of the tables. LEFT JOIN returns all records from the first or left table, RIGHT JOIN returns all records from the second or right table, and FULL OUTER JOIN returns all records from both tables. 

`SELECT *
FROM employees
FULL OUTER JOIN machines ON employees.device_id = machines.device_id;`



- AGGREGATE FUNCTIONS 
(COUNT, SUM, and AVG )

COUNT returns a single number that represents the number of rows returned from your query.

AVG returns a single number that represents the average of the numerical data in a column.

SUM returns a single number that represents the sum of the numerical data in a column. 



`SELECT COUNT(firstname)
FROM customers
WHERE country = 'USA';`
















***************

## Risk and Assets
 - Risk: Anything that can impact the confidentiality, integrity, or availability of an asset
    * Likelihood: Score from 1-3 of the chances of a vulnerability being exploited. A 1 means there's a low
    likelihood, a 2 means there's a moderate likelihood, and a 3 means there's a high likelihood.
    * Severity: Score from 1-3 of the potential damage the threat would cause to the business. A 1 means a
    low severity impact, a 2 is a moderate severity impact, and a 3 is a high severity impact.
    * Priority: How quickly a risk should be addressed to avoid the potential incident. Use the following
    formula to calculate the overall score: Likelihood x Impact Severity = Risk

 **Likelihood x Impact = Risk**

- Threat: Any circumstance or event that can negatively impact assets

- Vulnerability: A weakness that can be exploited by a threat

- **States of data : data in use, in transit, or at rest.**
    Data: Information that is translated, processed, or stored by a computer

    Data at rest: Data not currently being accessed

    Data in transit: Data traveling from one point to another

    Data in use: Data being accessed by one or more users

- **Information security (InfoSec)**: The practice of keeping data in all states away from unauthorized users

- __Asset management__ is the process of tracking assets and the risks that affect them. The idea behind this process is simple: you can only protect what you know you have. 


Restricted is the highest level. This category is reserved for incredibly sensitive assets,  like need-to-know information.

Confidential refers to assets whose disclosure may lead to a significant negative impact on an organization.

Internal-only describes assets that are available to employees and business partners.

Public is the lowest level of classification. These assets have no negative consequences to the organization if they’re released.



__cloud computing as, “An on-demand, massively scalable service, hosted on shared infrastructure, accessible via the internet.__

- There are three main categories of cloud-based services:

Software as a service (SaaS) - front-end applications that users access via a web browse

Platform as a service (PaaS) - back-end application development tools that clients can access online.

Infrastructure as a service (IaaS) - remote access to a range of back-end systems that are hosted by the cloud service provider. This includes data processing servers, storage, networking resources, and more

__Cloud security is a growing subfield of cybersecurity that specifically focuses on the protection of data, applications, and infrastructure in the cloud.__

        
    Cloud security challenges
            Misconfiguration is one of the biggest concerns. Customers of cloud-based services are responsible for configuring their own security environment. Oftentimes, they use out-of-the-box configurations that fail to address their specific security objectives.

            Cloud-native breaches are more likely to occur due to misconfigured services.

            Monitoring access might be difficult depending on the client and level of service.

            Meeting regulatory standards is also a concern, particularly in industries that are required by law to follow specific requirements such as HIPAA, PCI DSS, and GDPR

    

__Elements of security plan__
Three basic elements: policies, standards, and procedures.  

Security plans address risks such as damage to assets, loss of information, and disclosure of data. Shifting market conditions are a reality of doing business in an open market that is not addressed by security plans.

__NIST Cybersecurity Framework (CSF)__
- voluntary framework that consists of standards, guidelines, and best practices to manage cybersecurity risk.

+ flexible and can be applied to any industry.


1. __core__
- Three main components of NIST CSF : `the core, tiers, and profiles`

` The five NIST Cybersecurity Framework (CSF) core functions are identify, protect, detect, respond, and recover. `

The core is a simplified version of the **functions or duties of a security plan**. Think of these functions as a checklist for reducing security risk.
Used to understand ways to detect attacks and develop response and recovery plans should an attack happen.

2. __Tiers__
- The CSF tiers are a way of **measuring the sophistication of an organization's cybersecurity program**. CSF tiers are measured on a scale of 1 to 4. Tier 1 is the lowest score, indicating that a limited set of security controls have been implemented. Overall, CSF tiers are used to assess an organization's security posture and identify areas for improvement.

3. __Profiles__
- The CSF profiles are **pre-made templates** of the NIST CSF that are developed by a team of industry experts. CSF profiles are tailored to address the specific risks of an organization or industry. They are used to help organizations develop a baseline for their cybersecurity plans, or as a way of comparing their current cybersecurity posture to a specific industry standard.

**Compliance is the process of adhering to internal standards and external regulations**
 compliance is a way of measuring how well an organization is protecting their assets.

__Guidance that any organization can use to implement the CSF.__**

Create a current profile of the security operations and outline the specific needs of your business.

Perform a risk assessment to identify which of your current operations are meeting business and regulatory standards.

Analyze and prioritize existing gaps in security operations that place the businesses assets at risk.

Implement a plan of action to achieve your organization’s goals and objectives.

Always consider current risk, threat, and vulnerability trends when using the NIST CSF. 

***
**Security controls**

 safeguards designed to reduce specific security risks.
 They include a wide range of tools that protect assets before, during, and after an event.

 security controls are technical, operational, and managerial. Each type of security control plays a key role in effective information privacy.

 1. The principle of least privilege is a security control in which a user is only granted the minimum level of access and authorization required to complete a task or function.


 * There are three common approaches to auditing user accounts:

Usage audits

Privilege audits

Account change audits


__The data Lifecycle__
 the data lifecycle has five stages. Each describe how data flows through an organization from the moment it is created until it is no longer useful:
    -Collect
    -Store
    -Use
    -Archive
    -Destroy

__Data governance__
- set of processes that define how an organization manages information.
- specifies how to keep data private, accurate, available, and secure throughout its lifecycle.

Data owner: the person that decides who can access, edit, use, or destroy their information.

Data custodian: anyone or anything that's responsible for the safe handling, transport, and storage of information.

Data steward: the person or group that maintains and implements data governance policies set by an organization.


__Type of Information__
__PII__ is any information used to infer an individual's identity. Personally identifiable information, or PII, refers to information that can be used to contact or locate someone.

__PHI__ stands for protected health information.  In the U.S., it is regulated by the Health Insurance Portability and Accountability Act (HIPAA), which defines PHI as “information that relates to the past, present, or future physical or mental health or condition of an individual.” In the EU, PHI has a similar definition but it is regulated by the General Data Protection Regulation (GDPR).

__SPII__ is a specific type of PII that falls under stricter handling guidelines. The S stands for sensitive, meaning this is a type of personally identifiable information that should only be accessed on a need-to-know basis, such as a bank account number or login credentials.


***

A __security audit__ is a review of an organization's security controls, policies, and procedures against a set of expectations.

A __security assessment__ is a check to determine how resilient current security implementations are against threats.

***

## Cryptography

The process of transforming information into a form that unintended readers can't understand.In cryptography, a __cipher__ is used to hide, or encrypt information.

Cryptographic __Key__ - A mechanism that decrypts ciphertext

- __Brute Force attack__ - A trial and error process of discovering private information

-  caesor cipher
not used because of its limitations (relies on single key)

- __Public Key Infrastructure__
An encryption framework that secures the exchange of information online.
makes access of information fast, easy, secure

- it is a two step proccess
1. exchange of encrypted information (this involves symmetric encryption, asymmetric encryption or both)

**Asymmetric Encryption** 
The use of a public key and a private key for encryption and decryption of data.


**Symmetric Encryption**  (faster and simpler)
Uses a single secret key to exchange information, but less secure

Public key infrastructure uses both encryption and sometimes together depending on whether speed or security is the priority.

2. PKI addresses the vulnerability of key sharing by establishing trust using a system of digital certificates between computers and network.

A digital certificate binds the data's public key to the verified identity of a website, individual, organization, device, or server.


Digital Certificate - a file that verifies the identity of a public key holder.

**Approved Algolithms**
*Symmetric Algorithm*
1. Triple DES (3DES) is known as a block cipher because of the way it converts plaintext into ciphertext in “blocks.” 
    - Triple DES generates keys that are 192 bits, or three times as long.
    - limitations on the amount of data that can be encrypted. 

2. Advanced Encryption Standard (AES) is one of the most secure symmetric algorithms today. AES generates keys that are 128, 192, or 256 bits. 

    + Cryptographic keys of this size are considered to be safe from brute force attacks.

    - It’s estimated that brute forcing an AES 128-bit key could take a modern computer billions of years!

*Asymmetric algorithms*

1.  RSA is one of the first asymmetric encryption algorithms that produces a public and private key pair. 
    - Asymmetric algorithms like RSA produce even longer key lengths. In part, this is due to the fact that these functions are creating two keys. RSA key sizes are 1,024, 2,048, or 4,096 bits. 

    - RSA is mainly used to protect highly sensitive data.
2. Digital Signature Algorithm (DSA) is a standard asymmetric algorithm that was introduced by NIST

-  DSA also generates key lengths of 2,048 bits. This algorithm is widely used today as a complement to RSA in public key infrastructure.


**Generating keys**

- OpenSSL, which is an open-source command line tool that can be used to generate public and private keys. 

- OpenSSL is commonly used by computers to verify digital certificates that are exchanged as part of public key infrastructure.


***
## Hashing

- A __hash function__ is an algorithm that produces a code that can't be decrypted. 

- Unlike asymmetric and symmetric algorithms, hash functions are one-way processes that do not generate decryption keys. 

- Instead, these algorithms produce a unique identifier known as a hash value, or digest.

- In security, hashes are primarily used as a way to determine the __integrity of files and applications__.

Hashing algorithm - __sha256__ (commonly used)
sha256sum newfile.txt


 (__VirusTotal__ This is a popular tool among security practitioners that's useful for analyzing suspicious files, domains, IPs, and URLs.)



 __MD5__ works by converting data into a 128-bit value

 In a hash table, this appears as a string of 32 characters. Altering anything in the source file generates an entirely new hash value.

  **flaws in MD5** happens to be a characteristic of all hash functions. Hash algorithms map any input, regardless of its length, into a fixed-size value of letters and numbers

  - MD5 values are limited to 32 characters in length. Due to the limited output size, the algorithm is considered to be vulnerable to hash collision, an instance when different inputs produce the same hash value. 
  - Because hashes are used for authentication, a hash collision is similar to copying someone’s identity.
  - Attackers can carry out collision attacks to fraudulently impersonate authentic data.

  - MD5's shortcomings gave way to a new group of functions known as the **Secure Hashing Algorithms, or SHAs.**

  -Except for SHA-1, which produces a 160-bit digest, these algorithms are considered to be collision-resistant. However, that doesn’t make them invulnerable to other exploits.

  - Five functions make up the SHA family of algorithms:
   ` SHA-1

    SHA-224

    SHA-256

    SHA-384

    SHA-512 `


- __rainbow table__ is a file of pre-generated hash values and their associated plaintext.
- They’re like dictionaries of weak passwords.
- Attackers capable of obtaining an organization’s password database can use a rainbow table to compare them against all possible values.


- Functions with larger digests are less vulnerable to collision and rainbow table attacks.

- __Salting__ is an additional safeguard that's used to strengthen hash functions. A salt is a random string of characters that's added to data before it's hashed. The additional characters produce a more unique hash value, making salted data resilient to rainbow table attacks.

- For example, a database containing passwords might have several hashed entries for the password "password." If those passwords were all salted, each entry would be completely different. That means an attacker using a rainbow table would be unable to find matching values for "password" in the database.
- the longer and more complex a salt is, the harder it is to crack.


***


- to move hash value of a1.txt to a1file
`sha256 a1.txt >> a1file

sha256 a2.txt >> a2file

to compare both 
use cmp
cmp a1file a2file`

