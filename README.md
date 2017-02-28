# Web security
A readme on web security issues

## Security design
### System architecture level
- Read more about system architecture [here](https://msdn.microsoft.com/en-gb/library/ee658124.aspx)  
- Whitelisting apis at point of exit

### Code level
Manage user interactions carefully
- SQL injection: validate all inputs (ie form fields)
- XSS: cross-site scripting is about inputs too, so there's a need to validate inputs and use escaping or output encoding to indicate that the code is not meant to be executed
- Email form header injection: forces your system to send spam. Can be prevented by managing inputs properly
- Malicious file upload/execution: aim is to get control of database and website. Prevention is by evaluating file type and contents before interacting with it  

Minimise scope  
- User authorisation: users should only be able to see the data that is within the scope of their authorisation, so scope must be properly managed  

Log all user actions  
- All actions by any employee or other user must be logged  

Handle errors   
- Handle errors: visible errors could provide a malicious user information about the configuration of the system

[source](https://www.wubbleyou.co.uk/blog/articles/most-common-website-security-issues-and-prevention)  

## Same-origin policy
- is built into modern browsers
- provides a barrier between pages and scripts hosted on different domains
- permits unrestricted interactions between pages served as part of the same site

### Allowed under same-origin policy (using CORS)
- links
- redirects
- form submissions
- embedding scripts, images, CSS etc from other sites

### What is CORS?
- a standard for accessing web resources on different domains
- browsers restrict cross-origin scripting to secure the code on any given domain
- XMLHttpRequests initially followed same-origin policy: could only make HTTP requests to its own domain
- to enrich the content of web applications, browser vendors made it possible to make some cross-domain requests

### Public and private keys
- Diffie-Hellman key exchange is a way of securely exchanging cryptographic keys over a public channel
- Uses a public key, which is numerically 'mixed' on each side with a private key. The two mixed numbers are exchanged and combined with the local private number to get the same shared 'key'

[More on Diffie-Hellman](https://en.wikipedia.org/wiki/Diffie–Hellman_key_exchange)  

### SSL and HTTPS
HTTPS is HTTP with a secure sockets layer that encrypts all the data that is transferred.  
