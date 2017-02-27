# web-security
A readme on web security issues

### What's built into the browser: same-origin policy
- Explain what it is and what it can do
- Also a bit about CORS

### System architecture level


### Code level
Top 10 security issues
- SQL injection: validate all inputs (ie form fields)
- XSS: cross-site scripting is about inputs too, so there's a need to validate inputs (but need to understand this better)
- Email form header injection: forces your system to send spam. Can be prevented by managing inputs properly
- Malicious file upload/execution: aim is to get control of database and website. Prevention is by evaluating file type and contents before interacting with it
- User authorisation: users should only be able to see the data that is within the scope of their authorisation, so scope must be properly managed
- All actions by any employee or other user must be logged
- Handle errors: visible errors could provide a malicious user information about the configuration of the system

From https://www.wubbleyou.co.uk/blog/articles/most-common-website-security-issues-and-prevention

### Public and private keys
- Public key, prime numbers, Diffie & Hellman key exchange, how does this actually work with numbers? I get it with paint colours but I don't understand how the number aspect works

### Understanding of SSL and HTTPS


## GDS-specific security research

### What you should do
- make the team that’s building the software responsible for security
- make sure your team includes certified ethical hackers, security engineers or penetration testers
- have your team test for security issues throughout the development phases and after the service goes live
- use commercial and open source tools (system configuration should not be open source)
- conduct 3rd party penetration testing

### System attributes
- confidentiality - information should only be seen by people who are authorised to access it
- integrity – information should only be modified by people who are authorised to do so
- availability - information should be available when needed (problems or attacks shouldn’t stop you getting information from the system)
- non-repudiation - nothing should happen in a system that can’t be traced back to a responsible person

### Blogs on security
Check GDS blog for posts about security
[**Striking a balance between security and usability**](https://gds.blog.gov.uk/2014/02/10/striking-a-balance-between-security-and-usability/)
- Security and usability are often in tension, but they’re not necessarily opposed
- Verification of identity: use different channels for checking that information. Send a message to user's mobile
- GDS design principle: “Do less”, don't embellis with a ton of other things that aren't crucial
- All user data on one page on the web - a lot of risk (identity theft)
- Phishing: link in forged email looks like it’s to your service (offer them part of the information that they need, so they can see that it’s genuine?
- Design for security but do it proportionately - don’t get paralysed
- "Misuse cases": when you’re writing user stories also think about the misuse cases; think about how somebody might play with what you’ve built, or abuse it.

**Open source**
GDS aims to open source all code - up to a point
https://gds.blog.gov.uk/2014/10/08/when-is-it-ok-not-to-open-all-source-code/

