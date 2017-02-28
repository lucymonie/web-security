# Web security
A readme on web security issues

## What's built into the browser: same-origin policy
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

### System architecture level
Read more about this [here](https://msdn.microsoft.com/en-gb/library/ee658124.aspx)

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

### Public and private keys
- Diffie-Hellman key exchange is a way of securely exchanging cryptographic keys over a public channel
- Uses a public key, which is numerically 'mixed' on each side with a private key. The two mixed numbers are exchanged and combined with the local private number to get the same shared 'key'

[More on Diffie-Hellman](https://en.wikipedia.org/wiki/Diffie–Hellman_key_exchange)  

### Understanding of SSL and HTTPS
HTTPS is HTTP with a secure sockets layer that encrypts all the data that is transferred.  

## GDS-specific security research
### What teams should do
- make everyone is responsible for security
- include certified ethical hackers, security engineers or penetration testers
- test for security issues throughout development and after the service is live
- use commercial and open source tools (system configuration should not be open source)
- engage external testers to ensure the system isn't vulnerable to attack
- write 'misuse cases' when writing user stories

### System attributes
- confidential: only those authorised should have access to data
- integral: only authorised users should be able to modify information
- available: problems and attacks shouldn't prevent access to the system
- accountable: all user actions should be logged

### Blogs on security
Check GDS blog for posts about security  
[**Striking a balance between security and usability**](https://gds.blog.gov.uk/2014/02/10/striking-a-balance-between-security-and-usability/)  
Key points from article:  
- Security and usability are often in tension, but they’re not necessarily opposed
- "Misuse cases": when you’re writing user stories also think about the misuse cases; think about how somebody might play with what you’ve built, or abuse it  

Other notes  
- Verification of identity: don't make access an epic. Use different channels for checking that information. Eg Send a message to user's mobile
- GDS design principle: “Do less”, don't embellish with a ton of other things that aren't crucial that might add risk or increase barriers to access
- All user data on one page on the web - a lot of risk (identity theft)
- Phishing: link in forged email looks like it’s to your service. Mitigate by personalising the message or providing other data so they can see that it’s genuine
- Design for security but do it proportionately - don’t get paralysed


**Whitelisting cloud APIs**
- Traditional approach to system security is to control which networks and computers it can talk to (by ip address)
- Not great for cloud computing which uses Content Delivery Networks (CDNs) which use changing or shared ip addresses
- Instead use an HTTPS egress proxy, which is located at server exit and examines the destination of the traffic to see if it's trusted
- In addition, it can request the TLS certificate of the destination to ensure that the server is connecting with a trusted api via a secure connection
- Can also be configured to inspect the contents of the data leaving the network to ensure that it's not sensitive, but this can make the system more vulnerable to attack as personal details an auth tokens are available at the proxy

[source]((https://gdstechnology.blog.gov.uk/2017/01/03/a-whitelisting-approach-for-cloud-apis/))

**Open source**
- GDS aims to open source all code - up to a point
- System configuration should not be publicly availble as this could compromise security

[source](https://gds.blog.gov.uk/2014/10/08/when-is-it-ok-not-to-open-all-source-code/)

