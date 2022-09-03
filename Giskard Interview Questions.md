# Giskard interview Questions - Software Engineer 
 - Explain OSI model
 - How would you implement a Load Balancer ? 
 - What is HTTPs and how it works ?
 - Symetric vs Asymetric encryption 
 - How to share data & link components together in Angular/React
 -  On what protocol is based HTTP ? (TCP vs UDP)
 - Difference between HTTP 1.0 and HTTP 2.0
 - How can data be compromised in a website ? (XSS and SQL Injection)
 - How to process user's input data ? 
 - What is a cookie and how it works ? 
 - Can a website have access to another website's cookies ?
 - How to share data across several servers ? ( What is sharding ? )
 - How to improve SQL queries performance 
 - How to implement authentification in a website ? (hashing...)
 - Difference between push and pull notifications 
 
 ### Explain OSI model 
 ![enter image description here](https://miro.medium.com/max/400/1*ENCFIf2iPSoctG1mHW132w.jpeg)

### Load Balancers
-   Load balancers are generally grouped into two categories: Layer 4 and Layer 7.
- https://medium.com/must-know-computer-science/system-design-load-balancing-1c2e7675fc27

### What is HTTPs and how it works ?
HTTPS takes the well-known and understood HTTP protocol, and simply layers a SSL/TLS (hereafter referred to simply as “SSL”) encryption layer on top of it. Servers and clients still speak exactly the same HTTP to each other, but over a secure SSL connection that encrypts and decrypts their requests and responses. The SSL layer has 2 main purposes:

-   Verifying that you are talking directly to the server that you think you are talking to
-   Ensuring that only the server can read what you send it and only you can read what it sends back

The really, really clever part is that anyone can intercept every single one of the messages you exchange with a server, including the ones where you are agreeing on the key and encryption strategy to use, and still not be able to read any of the actual data you send.

https://robertheaton.com/2014/03/27/how-does-https-actually-work/

### Symetric vs Asymetric encryption
Difference Between Symmetric and Asymmetric Encryption

-   Symmetric encryption uses a single key that needs to be shared among the people who need to receive the message while asymmetric encryption uses a pair of public key and a private key to encrypt and decrypt messages when communicating.
-   Symmetric encryption is an old technique while asymmetric encryption is relatively new.
-   Asymmetric encryption was introduced to complement the inherent problem of the need to share the key in symmetric encryption model, eliminating the need to share the key by using a pair of public-private keys.
-   Asymmetric encryption takes relatively more time than the symmetric encryption 
![enter image description here](https://miro.medium.com/max/640/1*23RpkZuWAeSP7x0YdMtsdQ.png)

### How to share data & link components together in Angular/React
-   Parent to child component
-   Child to parent component
-   Sharing data between sibling components
-   Sharing data using ViewChild property
-   Sharing data between not related components
https://fireship.io/lessons/sharing-data-between-angular-components-four-methods/
### On what protocol is based HTTP ? (TCP vs UDP)
TCP is a connection-oriented protocol, whereas UDP is a connectionless protocol. A key difference between TCP and UDP is speed, as TCP is comparatively slower than UDP. Overall, UDP is a much faster, simpler, and efficient protocol, however, retransmission of lost data packets is only possible with TCP.
![enter image description here](https://www.netburner.com/wp-content/uploads/2020/06/TCP-vs-UDP-1024x687.png)
https://www.geeksforgeeks.org/differences-between-tcp-and-udp/

### Difference between HTTP 1.0 and HTTP 2.0
HTTP2 is much faster and more reliable than HTTP1. HTTP1 loads a single request for every TCP connection, while HTTP2 avoids network delay by using multiplexing.

https://cheapsslsecurity.com/p/http2-vs-http1/#:~:text=HTTP2%20is%20much%20faster%20and,then%20the%20page%20loads%20faster.

### How can data be compromised in a website ? (XSS and SQL Injection)
XSS and SQL injection are two types of attacks that can occur on websites. The main difference between XSS and SQL injection is that XSS injects malicious code to the website, therefore, those code executes in the users of the website while SQL injection inserts the SQL code to a web form input field to obtain access and modify data.
https://pediaa.com/what-is-the-difference-between-xss-and-sql-injection/#:~:text=The%20main%20difference%20between%20XSS,obtain%20access%20and%20modify%20data.

### How to process user's input data ? (Processing user's input best practices)
-   Data type validators available natively in web application frameworks (such as  [Django Validators](https://docs.djangoproject.com/en/1.11/ref/validators/),  [Apache Commons Validators](https://commons.apache.org/proper/commons-validator/apidocs/org/apache/commons/validator/package-summary.html#doc.Usage.validator)  etc).
-   Validation against  [JSON Schema](https://json-schema.org/)  and  [XML Schema (XSD)](https://www.w3schools.com/xml/schema_intro.asp)  for input in these formats.
-   Type conversion (e.g.  `Integer.parseInt()`  in Java,  `int()`  in Python) with strict exception handling
-   Minimum and maximum value range check for numerical parameters and dates, minimum and maximum length check for strings.
-   Array of allowed values for small sets of string parameters (e.g. days of week).
-   Regular expressions for any other structured data covering the whole input string  `(^...$)`  and  **not**  using "any character" wildcard (such as  `.`  or  `\S`)
https://cheatsheetseries.owasp.org/cheatsheets/Input_Validation_Cheat_Sheet.html

### What is a cookie and how it works ? 
**Cookies**  are text files with small pieces of data — like a username and password — that are used to identify your computer as you use a computer network. 
Data stored in a cookie is created by the server upon your connection. This data is labeled with an ID unique to you and your computer.

When the cookie is exchanged between your computer and the network server, the server reads the ID and knows what information to specifically serve to you.

1.  **Session management.** 
2.  **Personalization.** 
3.  **Tracking.**

**Session cookies** are used only while navigating a website
**Persistent cookies** remain on a computer indefinitely,

Why Cookies Can Be Dangerous ? 
**First-party cookies** are directly created by the website you are using.
**Third-party cookies** are more troubling. They are generated by websites that are different from the web pages users are currently surfing, usually because they're linked to ads on that page.

https://www.kaspersky.com/resource-center/definitions/cookies

### Can a website have access to another website's cookies ?
Cookies cannot be used to obtain personal information from your computer. The only data in a cookie is the data put into by a website's server. **The only site that has access to it is the site that put it there**

### How to share data across several servers ? ( What is sharding ? )

Sharding is a method of splitting and storing a single logical dataset in multiple databases
Implemented at the **application level**

**horizontal ** vs **vertical ** partitionning 
![enter image description here](https://miro.medium.com/max/1400/1*yyHih3GveWruzwYgLxTu3w.png)

https://medium.com/@jeeyoungk/how-sharding-works-b4dec46b3f6

### How to improve SQL queries performance 
-   [Tip 1: Add missing indexes](https://blog.devart.com/how-to-optimize-sql-query.html#missing-indexes)
-   [Tip 2: Check for unused indexes](https://blog.devart.com/how-to-optimize-sql-query.html#Non-used-indexes)
-   [Tip 3: Avoid using multiple OR in the FILTER predicate](https://blog.devart.com/how-to-optimize-sql-query.html#or-in-join-predicate)

-   [Tip 4: Use wildcards at the end of a phrase only](https://blog.devart.com/how-to-optimize-sql-query.html#use-wildcards)
-   [Tip 5: Avoid too many JOINs](https://blog.devart.com/how-to-optimize-sql-query.html#high-table-count)
-   [Tip 6: Avoid using SELECT DISTINCT](https://blog.devart.com/how-to-optimize-sql-query.html#avoid-using-select-distinct)
-   [Tip 7: Use SELECT fields instead of SELECT *](https://blog.devart.com/how-to-optimize-sql-query.html#use-select-fields-instead-of-select-all)
-   [Tip 8: Use TOP to sample query results](https://blog.devart.com/how-to-optimize-sql-query.html#use-top-to-sample-query-results)
-   [Tip 9: Run the query during off-peak hours](https://blog.devart.com/how-to-optimize-sql-query.html#run-query-during-offpeak-hours)
-   [Tip 10: Minimize the usage of any query hint](https://blog.devart.com/how-to-optimize-sql-query.html#minimize-usage-of-query-hint)
-   [Tip 11: Minimize large write operations](https://blog.devart.com/how-to-optimize-sql-query.html#minimize-large-write-operations)
-   [Tip 12: Create joins with INNER JOIN (not WHERE)](https://blog.devart.com/how-to-optimize-sql-query.html#create-joins-with-inner-join)
https://blog.devart.com/how-to-optimize-sql-query.html

### How to implement authentification in a website ? (hashing...)

-   Cookie-Based authentication
-   Token-Based authentication
-   Third party access(OAuth, API-token)
-   OpenId
-   SAML
https://medium.com/@vivekmadurai/different-ways-to-authenticate-a-web-application-e8f3875c254a

### Difference between push and pull notifications 
-   **[Pull notification](https://en.wikipedia.org/wiki/Pull_technology)**  means  **a client requesting a server**  to check if there are any updates.
the initial  request for data originates from the client, and then is responded to by the server.
-   **[Push notification](https://en.wikipedia.org/wiki/Push_technology)**  means  **a server notifying a client**  about the updates.
	 A client "subscribes" to various information "channels" provided by a server; whenever new content is available on one of those channels, the server pushes that information out to the client.
