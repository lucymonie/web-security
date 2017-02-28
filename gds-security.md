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
**Striking a balance between security and usability**  
Key points from article:  
- Security and usability are often in tension, but they’re not necessarily opposed
- "Misuse cases": when you’re writing user stories also think about the misuse cases; think about how somebody might play with what you’ve built, or abuse it  

Other notes  
- Verification of identity: don't make access an epic. Use different channels for checking that information. Eg Send a message to user's mobile
- GDS design principle: “Do less”, don't embellish with a ton of other things that aren't crucial that might add risk or increase barriers to access
- All user data on one page on the web - a lot of risk (identity theft)
- Phishing: link in forged email looks like it’s to your service. Mitigate by personalising the message or providing other data so they can see that it’s genuine
- Design for security but do it proportionately - don’t get paralysed  

[source](https://gds.blog.gov.uk/2014/02/10/striking-a-balance-between-security-and-usability/)

**Whitelisting cloud APIs**
- Traditional approach to system security is to control which networks and computers it can talk to (by ip address)
- Not great for cloud computing which uses Content Delivery Networks (CDNs) which use changing or shared ip addresses
- Instead use an HTTPS egress proxy, which is located at server exit and examines the destination of the traffic to see if it's trusted
- In addition, it can request the TLS certificate of the destination to ensure that the server is connecting with a trusted api via a secure connection
- Can also be configured to inspect the contents of the data leaving the network to ensure that it's not sensitive, but this can make the system more vulnerable to attack as personal details an auth tokens are available at the proxy

[source](https://gdstechnology.blog.gov.uk/2017/01/03/a-whitelisting-approach-for-cloud-apis/)

**Open source**
- GDS aims to open source all code - up to a point
- System configuration should not be publicly availble as this could compromise security

[source](https://gds.blog.gov.uk/2014/10/08/when-is-it-ok-not-to-open-all-source-code/)
