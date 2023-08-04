# Security Learning Notes

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
`sha256sum a1.txt >> a1filehash

sha256sum a2.txt >> a2filehash

to compare both 
use cmp
cmp a1filehash a2filehash`

****
 ## Acess Control

  The security controls that manage access, authorization, and accountability of information

 __AAA Framework__
 These systems are commonly broken down into three separate, yet related functions known as the __authentication, authorization, and accounting__ framework. Each control has its own protocol and systems that make them work. 

1. **Authentication**
 - The three factors of **authentication are: characteristic, ownership, and knowledge**. Ownership is used to verify a user's identity using something the user possesses, like a one-time passcode 

 - __SSO__, is a technology that combines several different logins into one.
        SSO technology is great, but not if it relies on just a single factor of authentication. Adding more authentication factors strengthen these systems.
        - __Multi-factor authentication__, or MFA, is a security measure, which requires a user to verify their identity in two or more ways to access a system or network. MFA combines two or more independent credentials, like knowledge and ownership, to prove that someone is who they claim to be.
            - SSO and MFA are often used in conjunction with one another to layer the defense capabilities of authentication systems. When both are used, organizations can ensure convenient access that is also secure.

    - SSO solutions use trusted third-parties to prove that a user is who they claim to be. This is done through the exchange of encrypted access tokens between the identity provider and the service provider.
    - SSO implementations commonly rely on two different authentication protocols: LDAP and SAML. LDAP, which stands for Lightweight Directory Access Protocol, is mostly used to transmit information on-premises; SAML, which stands for Security Assertion Markup Language, is mostly used to transmit information off-premises, like in the cloud.
        - LDAP and SAML protocols are often used together


    - three factors (3FA) to authenticate their identification
                Something a user knows: most commonly a username and password

                Something a user has: normally received from a service provider, like a one-time passcode (OTP) sent via SMS

                Something a user is: refers to physical characteristics of a user, like their fingerprints or facial scans

2. **Authorization**

Authorization controls are linked to the *separation of duties and the principle of least privilege.* 

__principle of least privilege__ in which a user is only granted the minimum level of access and authorization required to complete a task or function.

__Separation of duties__ is the principle that users should not be given levels of authorization that will allow them to misuse a system. Separating duties reduces the risk of system failures and inappropriate behavior from users.


*frequently used access controls* - __HTTP basic auth and OAuth.__

1. HTTP basic auth-  It stands for hypertext transfer protocol, which is how communications are established over network. HTTP uses what is known as basic auth, the technology used to establish a user's request to access a server. Basic auth works by sending an identifier every time a user communicates with a web page. ( vulnerable to attacks because it transmits usernames and password openly over the network)
    - Most websites today use HTTPS instead, which stands for hypertext transfer protocol secure. This protocol doesn't expose sensitive information, like access credentials, when communicating over the network.

2. OAuth is an open-standard authorization protocol that shares designated access between applications. For example, you can tell Google that it's okay for another website to access your profile to create an account. Instead of requesting and sending sensitive usernames and passwords over the network, OAuth uses API tokens to verify access between you and a service provider.

*API token is a small block of encrypted code that contains information about a user. These tokens contain things like your identity, site permissions, and more.*

- OAuth sends and receives access requests using API tokens by passing them from a server to a user's device.
- API tokens serve as an additional layer of encryption that helps to keep your Google password safe in the event of a breach on another platform.
- Basic auth and OAuth are just a couple of examples of authorization tools that are designed with the principles of least privilege and separation of duty in mind.

3. **Accounting**

- Accounting is the practice of monitoring the access logs of a system. These logs contain information like who accessed the system, and when they accessed it, and what resources they used.

- helpful way to identify trends, like failed login attempts.

- used to uncover hackers who have gained access to a system, and for detecting an incident, like a data breach.

- Anytime a user accesses a system, a session is initiated. 
        - A session is a sequence of network HTTP basic auth requests and responses associated with the same user, like when you visit a website. Access logs are essentially records of sessions that capture the moment a user enters a system until the moment they leave it.
- Two actions are triggered when the session begins. 
    1. The first is the creation of a session ID. A session ID is a unique token that identifies a user and their device while accessing the system. Session IDs are attached to the user until they either close their browser or the session times out.
    2. The second action that takes place at the start of a session is an exchange of session cookies between a server and a user's device. A session cookie is a token that websites use to validate a session and determine how long that session should last. When cookies are exchanged between your computer and a server, your session ID is read to determine what information the website should show you.

- Cookies make web sessions safer and more efficient. The exchange of tokens means that no sensitive information, like usernames and passwords, are shared. Session cookies prevent attackers from obtaining sensitive data.

- However, there's other damage that they can do. With a stolen cookie, an attacker can impersonate a user using their session token. This kind of attack is known as session hijacking.
    - *Session hijacking* is an event when attackers obtain a legitimate user's session ID. During these kinds of attacks, cyber criminals impersonate the user, causing all sorts of harm. Money or private data can be stolen. If, for example, hijackers obtain a single sign-on credential from stolen cookies, they can even gain access to additional systems that otherwise seem secure.


**Identity and access management (IAM)** is a collection of processes and technologies that helps organizations manage digital identities in their environment. Both AAA and IAM systems are designed to authenticate users, determine their access privileges, and track their activities within a system.

- *User provisioning* is the process of creating and maintaining a user's digital identity. For example, a college might create a new user account when a new instructor is hired. The new account will be configured to provide access to instructor-only resources while they are teaching. Security analysts are routinely involved with provisioning users and their access privileges.

***

If the right user has been authenticated, the network should ensure the right resources are made available. There are ***three common frameworks*** that organizations use to handle this step of ***IAM***:

1. Mandatory access control (MAC)

    MAC is the strictest of the three frameworks. Authorization in this model is based on a strict need-to-know basis. Access to information must be granted manually by a central authority or system administrator. For example, MAC is commonly applied in law enforcement, military, and other government agencies where users must request access through a chain of command. MAC is also known as non-discretionary control because access isn’t given at the discretion of the data owner.



2. Discretionary access control (DAC)

    DAC is typically applied when a data owner decides appropriate levels of access. One example of DAC is when the owner of a Google Drive folder shares editor, viewer, or commentor access with someone else.



3. Role-based access control (RBAC)

    RBAC is used when authorization is determined by a user's role within an organization. For example, a user in the marketing department may have access to user analytics but not network administration.




*****

## Vulnerabilities

* Vulnerability - A weakness that can be exploited by a threat.
* exploit - taking advantage of a vulnerability
- Threat - any circumstance or event that can negactively impact assets.
* exposure - a mistake that can be exploited by threat

+ vulnerability management- process of finding and patching vulnerability
            1. identify vulnerabilities
            2. consider potential exploites
            3. prepare defenses against threats
            4. evaluate those defenses


- Zero day Expolit - an explot that was previously unknown (the term zero means that it's happening in real time with zero days to fix it)



* Defense in depth - A **layered approach** to vulnerability management that reduces risk (known as castle approach because it resembles the layered defenses of a castle)
        layers: perimeter layer, network layer, endpoint layer, application layer, data layer


* *One of the most popular libraries of vulnerabilities and exposures is the CVE list*. The common vulnerabilities and exposures list, or CVE list, is an openly accessible dictionary of known vulnerabilities and exposures. It is a popular resource.

   

    - The main purpose of the CVE list is to offer a standard way of identifying and categorizing known vulnerabilities and exposures. 
    
    - Most CVEs in the list are reported by independent researchers, technology vendors, and ethical hackers, but anyone can report one. Before a CVE can make it onto the CVE list, it first goes through a strict review process by a CVE Numbering Authority, or CNA.

     - CVE LIST CRITERIA
            independent of other issues, recognized as a potential security risk, submitted with supporting evidence, only affect one codebase

    - The NIST National Vulnerabilities Database uses what's known as the common vulnerability scoring system, or CVSS, which is a measurement system that scores the severity of a vulnerability.

    - Security teams use CVSS as a way of calculating the impact a vulnerability could have on a system. They also use them to determine how quickly a vulnerability should be patched.


    - CVSS that scores below a 4.0 is considered to be low risk and doesn't require immediate attention. However, anything above a 9.0 is considered to be a critical risk to company assets that should be addressed right away.


-__Vulnerability scanner__: Software that automatically compares existing common vulnerabilities and exposures against the technologies on the network

*****

## OWASP 


__OWASP__ is a nonprofit foundation that works to improve the security of software. OWASP is an open platform that security professionals from around the world use to share information, tools, and events that are focused on securing the web.

### The OWASP Top 10
One of OWASP’s most valuable resources is the OWASP Top 10. The organization has published this list since 2003 as a way to spread awareness of the web’s most targeted vulnerabilities. The Top 10 mainly applies to new or custom made software. Many of the world's largest organizations reference the OWASP Top 10 during application development to help ensure their programs address common security mistakes.

Pro tip: OWASP’s Top 10 is updated every few years as technologies evolve. Rankings are based on how often the vulnerabilities are discovered and the level of risk they present.

Note: Auditors also use the OWASP Top 10 as one point of reference when checking for regulatory compliance.

- Common vulnerabilities
Businesses often make critical security decisions based on the vulnerabilities listed in the OWASP Top 10. This resource influences how businesses design new software that will be on their network, unlike the CVE® list, which helps them identify improvements to existing programs. These are the most regularly listed vulnerabilities that appear in their rankings to know about:

1. Broken access control
Access controls limit what users can do in a web application. For example, a blog might allow visitors to post comments on a recent article but restricts them from deleting the article entirely. Failures in these mechanisms can lead to unauthorized information disclosure, modification, or destruction. They can also give someone unauthorized access to other business applications.

2. Cryptographic failures
Information is one of the most important assets businesses need to protect. Privacy laws such as General Data Protection Regulation (GDPR) require sensitive data to be protected by effective encryption methods. Vulnerabilities can occur when businesses fail to encrypt things like personally identifiable information (PII). For example, if a web application uses a weak hashing algorithm, like MD5, it’s more at risk of suffering a data breach.

3. Injection
Injection occurs when malicious code is inserted into a vulnerable application. Although the app appears to work normally, it does things that it wasn’t intended to do. Injection attacks can give threat actors a backdoor into an organization’s information system. A common target is a website’s login form. When these forms are vulnerable to injection, attackers can insert malicious code that gives them access to modify or steal user credentials. 

4. Insecure design
Applications should be designed in such a way that makes them resilient to attack. When they aren’t, they’re much more vulnerable to threats like injection attacks or malware infections. Insecure design refers to a wide range of missing or poorly implemented security controls that should have been programmed into an application when it was being developed.

5. Security misconfiguration
Misconfigurations occur when security settings aren’t properly set or maintained. Companies use a variety of different interconnected systems. Mistakes often happen when those systems aren’t properly set up or audited. A common example is when businesses deploy equipment, like a network server, using default settings. This can lead businesses to use settings that fail to address the organization's security objectives.

6. Vulnerable and outdated components
Vulnerable and outdated components is a category that mainly relates to application development. Instead of coding everything from scratch, most developers use open-source libraries to complete their projects faster and easier. This publicly available software is maintained by communities of programmers on a volunteer basis. Applications that use vulnerable components that have not been maintained are at greater risk of being exploited by threat actors.

7. Identification and authentication failures
Identification is the keyword in this vulnerability category. When applications fail to recognize who should have access and what they’re authorized to do, it can lead to serious problems. For example, a home Wi-Fi router normally uses a simple login form to keep unwanted guests off the network. If this defense fails, an attacker can invade the homeowner’s privacy.

8. Software and data integrity failures
Software and data integrity failures are instances when updates or patches are inadequately reviewed before implementation. Attackers might exploit these weaknesses to deliver malicious software. When that occurs, there can be serious downstream effects. Third parties are likely to become infected if a single system is compromised, an event known as a supply chain attack.

- A famous example of a supply chain attack is the 
    SolarWinds cyber attack (2020)
    where hackers injected malicious code into software updates that the company unknowingly released to their customers.

9. Security logging and monitoring failures
In security, it’s important to be able to log and trace back events. Having a record of events like user login attempts is critical to finding and fixing problems. Sufficient monitoring and incident response is equally important.

10. Server-side request forgery
Companies have public and private information stored on web servers. When you use a hyperlink or click a button on a website, a request is sent to a server that should validate who you are, fetch the appropriate data, and then return it to you.

Server-side request forgeries (SSRFs) are when attackers manipulate the normal operations of a server to read or update other resources on that server. These are possible when an application on the server is vulnerable. Malicious code can be carried by the vulnerable app to the host server that will fetch unauthorized data.






OSINT is the collection and analysis of information from publicly available sources to generate usable intelligence. It's commonly used to support cybersecurity activities, like identifying potential threats and vulnerabilities. 




*****

## How to find Vulnerability

__vulnerability Assessment__ -  internal review process of an organization's security systems. These assessments work similar to the process of identifying and categorizing vulnerabilities on the CVE list. The main difference is the organization's security team performs, evaluates, scores, and fixes them on their own.

- The goal of a vulnerability assessment is to identify weak points and prevent attacks.

- Once they decide what to focus on, vulnerability assessments typically follow a four-step process

    1. Identification
    2. Vulnerability analysis
    3. Risk Assessment
    4. Remediation (vulnerabilities that can impact the organization are addressed)


   - A vulnerability scanner is software that automatically compares known vulnerabilities and exposures against the technologies on the network


   - A __patch update__ is a software and operating system update that addresses security vulnerabilities within a program or product. Patches usually contain bug fixes that address common security vulnerabilities and exposures.

    patches address common vulnerabilities and exposures before malicious hackers find them. However, patches are sometimes developed as a result of a zero-day, which is an exploit that was previously unknown.

    - __End of Life__
    All software has a lifecycle. It begins when it’s produced and ends when a newer version is released. At that point, developers must allocate resources to the newer versions, which leads to EOL software. While the older software is still useful, the manufacturer no longer supports it. 



    ******

    # Penetration Testing

    A penetration test, or pen test, is a simulated attack that helps identify vulnerabilities in systems, networks, websites, applications, and processes. The simulated attack in a pen test involves using the same tools and techniques as malicious actors in order to mimic a real life attack. Since a pen test is an authorized attack, it is considered to be a form of ethical hacking. Unlike a vulnerability assessment that finds weaknesses in a system's security, a pen test exploits those weaknesses to determine the potential consequences if the system breaks or gets broken into by a threat actor.


1. Red team tests simulate attacks to identify vulnerabilities in systems, networks, or applications.

2. Blue team tests focus on defense and incident response to validate an organization's existing security systems.

3. Purple team tests are collaborative, focusing on improving the security posture of the organization by combining elements of red and blue team exercises.


## common penetration testing strategies: 

 __Open-box testing__ is when the tester has the same privileged access that an internal developer would have—information like system architecture, data flow, and network diagrams. This strategy goes by several different names, including internal, full knowledge, white-box, and clear-box penetration testing.

__Closed-box testing__ is when the tester has little to no access to internal systems—similar to a malicious hacker. This strategy is sometimes referred to as external, black-box, or zero knowledge penetration testing.  (Closed box testers tend to produce the most accurate simulations of a real-world attack)

__Partial knowledge testing__ is when the tester has limited access and knowledge of an internal system—for example, a customer service representative. This strategy is also known as gray-box testing.


***

__An attack surface__ is all the potential vulnerabilities that a threat actor could exploit. Analyzing the attack surface is usually the first thing security teams do.

The __digital attack surface__ includes everything that's beyond our organization's firewall. In other words, it includes anything that connects to an organization online.

***

*Simulating threats*
One method of applying an attacker mindset is using attack simulations. These activities are normally performed in one of two ways: proactively and reactively. Both approaches share a common goal, which is to make systems safer.

1. Proactive simulations assume the role of an attacker by exploiting vulnerabilities and breaking through defenses. This is sometimes called a red team exercise.

2. Reactive simulations assume the role of a defender responding to an attack. This is sometimes called a blue team exercise.
***

__Threat actors__(5 categories)

A threat actor is any person or group who presents a security risk. This broad definition refers to people inside and outside an organization. It also includes individuals who intentionally pose a threat, and those that accidentally put assets at risk.


1. Competitors refers to rival companies who pose a threat because they might benefit from leaked information.

2. State actors are government intelligence agencies.

3. Criminal syndicates refer to organized groups of people who make money from criminal activity.

4. Insider threats can be any individual who has or had authorized access to an organization’s resources. This includes employees who accidentally compromise assets or individuals who purposefully put them at risk for their own benefit.

5. Shadow IT refers to individuals who use technologies that lack IT governance. A common example is when an employee uses their personal email to send work-related communications.


***


__Types of hackers__

1. Unauthorized hackers (an individual who uses their programming skills to commit crimes. )

2. Authorized, or ethical, hackers(individuals who use their programming skills to improve an organization's overall security. )

3. Semi-authorized hackers (individuals who might violate ethical standards, but are not considered malicious. )

***

- __An advanced persistent threat (APT)__ refers to instances when a threat actor maintains unauthorized access to a system for an extended period of time. 

__Attack Vector__ - The pathways attacker use to penetrate security defenses

__Attack tree__: A diagram that maps threats to assets
*****

 ## brute force attacks


 1. Simple brute force attacks are an approach in which attackers guess a user's login credentials. They might do this by entering any combination of username and password that they can think of until they find the one that works.

 2. Dictionary attacks are a similar technique except in these instances attackers use a list of commonly used credentials to access a system. This list is similar to matching a definition to a word in a dictionary.

3. Reverse brute force attacks are similar to dictionary attacks, except they start with a single credential and try it in various systems until a match is found.

4. Credential stuffing is a tactic in which attackers use stolen login credentials from previous data breaches to access user accounts at another organization. A specialized type of credential stuffing is called pass the hash. These attacks reuse stolen, unsalted hashed credentials to trick an authentication system into creating a new authenticated user session on the network.\

5. encrypted information can sometimes be brute forced using a technique known as exhaustive key search.

* common brute forcing tools:
Aircrack-ng (to test a Wi-Fi network for vulnerabilities to brute force attack.)
Hashcat 
John the Ripper
Ophcrack
THC Hydra


* Prevention measures:
Hashing and salting
Multi-factor authentication (MFA)
CAPTCHA
Password policies(standard good password practices )




*****


- __Social engineering__ is a manipulation technique that exploits human error to gain private information, access, or valuables.

__stages__: 
prepare
establish trust
use persuation tactics
disconnect from the target


__prevention__:
implementing mangerial controls
staying informed of trends
sharing knowledge with others


__Signs of an attack__:
- baiting (example is USB baiting that relies on someone finding an infected USB drive and plugging it into their device.)


- phishing ( to trick people into revealing sensitive data or deploying malicious software. It is one of the most common forms of social engineering, typically performed via email.)


- quid pro quo (used to trick someone into believing that they’ll be rewarded in return for sharing access, information, or money)


- Tailgating is a social engineering tactic in which unauthorized people follow an authorized person into a restricted area. This technique is also sometimes referred to as piggybacking.


- watering hole- a type of attack when a threat actor compromises a website frequently visited by a specific group of users. Oftentimes, these watering hole sites are infected with malicious software. An example is the Holy Water attack of 2020 that infected various religious, charity, and volunteer websites.

***
**Phishing**

phishing Kit - a collection of software tools needed to launch a phishing campaign

3 main tools that are found inside a phishing kit
* malicious attachments
* fake data- collection forms
* fraudulent web links

__forms of phishing__:

* Email phishing

* smishing - the use of text messages to obtain sensitive info or to inpersonate a known source.

* vishing - the expolitation of electronic voice communication to obtain sensitive information or impersonate a known source

* Spear phishing is a subset of email phishing in which specific people are purposefully targeted  such as the accountants of a small business.

    * Whaling refers to a category of spear phishing attempts that are aimed at high-ranking executives in an organization.

*  Angler phishing is a technique where attackers impersonate customer service representatives on social media. (evolved in the 2010)
They then trick the angry customers into sharing sensitive information with the promise of fixing their problem.


****
####  Malware
Malware is software designed to harm devices or networks. Malware, which is short for malicious software, can be spread in many ways. For example, it can be spread through an infected USB drive. Or also commonly spread between computers online.


**types of malware:**

* virus - When the infected program is launched, the virus clones itself and spreads to other files on the device. An important characteristic of viruses is that they have to be activated by the user to start the infection.
* worm -doesn't have this limitation. A worm is malware that can duplicate and spread itself across systems on its own*
* trojan - malware that looks like a legitimate file or program. 
* ransomware - Attackers often use trojans to gain access and install another kind of malware called ransomware. Ransomware is a type of malicious attack where attackers encrypt an organization's data and demand payment to restore access
* spyware - Spyware is malware that's used to gather and sell information without consent. Consent is a keyword in this case. (to collect data like login credentials, account PINs, and other types of sensitive information for their own personal gain.)





Additional Info:

* scareware. This type of malware employs tactics to frighten users into infecting their own device. 

* Fileless malware does not need to be installed by the user because it uses legitimate programs that are already installed to infect a computer. This type of infection resides in memory where the malware never touches the hard drive.

* A rootkit is malware that provides remote, administrative access to a computer. Most attackers use rootkits to open a backdoor to systems, allowing them to install other forms of malware or to conduct network security attacks.
    -This kind of malware is often spread by a combination of two components: a dropper and a loader. A dropper is a type of malware that comes packed with malicious code which is delivered and installed onto a target system. 
            - For example, a dropper is often disguised as a legitimate file, such as a document, an image, or an executable to deceive its target into opening, or dropping it, onto their device. If the user opens the dropper program, its malicious code is executed and it hides itself on the target system.

            - Multi-staged malware attacks, where multiple packets of malicious code are deployed, commonly use a variation called a loader. A loader is a type of malware that downloads strains of malicious code from an external source and installs them onto a target system. Attackers might use loaders for different purposes, such as to set up another type of malware---a botnet.


            -  botnet, short for “robot network,” is a collection of computers infected by malware that are under the control of a single threat actor, known as the “bot-herder.” Viruses, worms, and trojans are often used to spread the initial infection and turn the devices into a bot for the bot-herder. The attacker then uses file sharing, email, or social media application protocols to create new bots and grow the botnet. When a target unknowingly opens the malicious file, the computer, or bot, reports the information back to the bot-herder, who can execute commands on the infected computer.



*****
CryptoJacking - when someone's computing resources are illegally hijacked to mine cryptocurrencies.

*****

# Cross- site scripting (XSS)

__Web-based exploits__ are malicious code or behavior that's used to take advantage of coding flaws in a web application

__An injection attack__ is malicious code inserted into a vulnerable application. 

XSS attacks are delivered by exploiting the two languages used by most websites, __HTML and JavaScript__.

A common and dangerous type of injection attack that's a threat to web apps is **cross-site scripting**. Cross site scripting, or XSS, is an injection attack that inserts code into a vulnerable website or web application. These attacks are often delivered by exploiting the two languages used by most websites, HTML and JavaScript. Both can give cybercriminals access to everything that loads on the infected web page. This can include session cookies, geolocation, and even webcams and microphones.

types of XSS attacks: reflected, stored, and DOM-based.

__reflected__ A reflected XSS attack is an instance where a malicious script is sent to the server and activated during the server's response. A common example of this is the search bar of a website. In a reflected XSS attack, criminals send their target a web link that appears to go to a trusted site. When they click the link, it sends a HTTP request to the vulnerable site server. The attacker script is then returned or reflected back to the innocent user's browser. Here, the browser loads the malicious script because it trusts the server's response. With the script loaded, information like session cookies are sent back to the attacker.

In a __stored__ XSS attack, the malicious script isn't hidden in a link that needs to be sent to the server. Instead a stored XSS attack is an instance when malicious script is injected directly on the server. Here, attackers target elements of a site that are served to the user. This could be things like images and buttons that load when the site is visited. Infected elements activate the malicious code when a user simply visits the site. Stored XSS attacks can be damaging because the user has no way of knowing the site is infected beforehand.


 __DOM-based XSS__. DOM stands for Document Object Model, which is basically the source code of a website. A DOM-based XSS attack is an instance when malicious script exists in the web page a browser loads. Unlike reflected XSS, these attacks don't need to be sent to the server to activate.

In a DOM-based attack, a malicious script can be seen in the URL. In this example, the website's URL contains parameter values. The parameter values reflect input from the user. Here, the site allows users to select color themes. When the user makes a selection, it appears as part of the URL. In a DOM-based attack, criminals change the parameter that suspecting an input. For example, they could hide malicious JavaScript in the HTML tags. The browser would process the HTML and execute the JavaScript.

******
## SQL Injection
__ SQL injection__ is an attack that executes unexpected queries on a database. Like cross-site scripting, SQL injection occurs due to a lack of sanitized input. The injections take place in the area of the website that are designed to accept user input. A common example is the login form to access a site. One of these forms might trigger a backend SQL statement like this when a user enters their credentials. Web forms, like this one, are designed to copy user input into the statement exactly as they're written.

The statement then sends a request to the server, which runs the query. Websites that are vulnerable to SQL injection insert the user's input exactly as it's entered before running the code.

__how to prevent:__
1. Prepared statements: a coding technique that executes SQL statements before passing them on to a database

2. Input sanitization: programming that removes user input which could be interpreted as code.

3. Input validation: programming that ensures user input meets a system's expectations.

__categories of SQL injection:__

* In-band(uses the same communication channel to launch the attack and gather the results.)

* Out-of-band(uses a different communication channel  to launch the attack and gather the results.)

* Inferential (occurs when an attacker is unable to directly see the results of their attack. Instead, they can interpret the results by analyzing the behavior of the system.)



*****

__Threat modeling__

How to prepare for threats - by threat modeling 
`a process of identifying assets, their vulnerabilities, and how each is exposed to threats.`  

6 steps of a threat model:

1. define the scopes
2. identify threats
3. characterize the environment
4. analyze threats
5. Mitigate threats
6. evaluate findings


When performing threat modeling, there are multiple methods that can be used, such as:

- STRIDE
- PASTA
- Trike
- VAST


__PASTA__
Process of Attack Simulation and Threat Analysis (PASTA) is a risk-centric **threat modeling process** developed by two OWASP leaders and supported by a cybersecurity firm called VerSprite. Its main focus is to discover evidence of viable threats and represent this information as a model. PASTA's evidence-based design can be applied when threat modeling an application or the environment that supports that application. Its seven stage process consists of various activities that incorporate relevant security artifacts of the environment, like vulnerability assessment reports.

PASTA Threat model framework
1. define the business and security obsjectives
2. define the technical scope
3. decompose the application
4. perform a threat analysis
5. perform a vulnerability analysis
6. conduct attack modeling
7. analyse risk and impact

******


