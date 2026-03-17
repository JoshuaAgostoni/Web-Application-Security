<h1>Web Application Security & PenTesting Lab</h1>



<h2>Description:</h2>
This project demonstrates a comprehensive web application penetration test within a containerized environment. Utilizing <b>OWASP Juice Shop</b> as the target, the lab showcases the ability to identify, exploit, and provide remediation for critical web vulnerabilities, including <b>SQL Injection (SQLi), Cross-Site Scripting (XSS)</b>, and <b>Insecure Direct Object References (IDOR)</b>.


<h2>Architecture Components</h2>

* <b>Target Application:</b> OWASP Juice Shop running in a Docker container on port 3000.
* <b>Attacker Node:</b> Kali Linux instance utilizing Burp Suite Professional/Community.
* <b>Proxy Tools:</b> Burp Suite Intercept and Repeater for manual request manipulation.
* <b>Network:</b> Shared NAT/Host-Only network for secure local traffic analysis.

 


<h2>Environments Used: </h2>

<b>OWASP Juice Shop - Kali linux -Burp Suite</b>

<h2>Program walk-through:</h2>

<p align="center">
Displays the successful deployment of the target application via Docker and an Nmap scan verifying service availability on port 3000.
<br/>
<a href="https://imgur.com/diuOprg"><img src="https://i.imgur.com/diuOprg.png" title="source: imgur.com" /></a>
<br />
<br />
Shows Burp Suite capturing raw HTTP GET requests from the browser, demonstrating the ability to analyze headers and cookies before they reach the server.  <br/>
<a href="https://imgur.com/hO04th0"><img src="https://i.imgur.com/hO04th0.png" title="source: imgur.com" /></a>
<br />
<br />
Displays the injection of an ' or 1=1-- payload into the email field of the login form to bypass authentication mechanisms. <br/>
<a href="https://imgur.com/pDc7mLV"><img src="https://i.imgur.com/pDc7mLV.png" title="source: imgur.com" /></a>
<br />
<br />
Shows the application dashboard confirming an active session as the "Administrator" user, verifying a successful SQL Injection attack.  <br/>
<a href="https://imgur.com/JZhxN0A"><img src="https://i.imgur.com/JZhxN0A.png" title="source: imgur.com" /></a>
<br />
<br />
Displays the identification of a Reflected Cross-Site Scripting (XSS) vulnerability within the OWASP Juice Shop search field. <br/>
<a href="https://imgur.com/hDChn5w"><img src="https://i.imgur.com/hDChn5w.png" title="source: imgur.com" /></a>
<br />
<br />
Displays a browser alert box triggered by a malicious <script> payload injected into the search bar, confirming a Cross-Site Scripting vulnerability.  <br/>
<a href="https://imgur.com/b7PPDl7"><img src="https://i.imgur.com/b7PPDl7.png" title="source: imgur.com" /></a>
<br />
<br />
Confirms a sensitive directory exposure within the OWASP Juice Shop application.
<a href="https://imgur.com/eaRttNs"><img src="https://i.imgur.com/eaRttNs.png" title="source: imgur.com" /></a>
<br />
<br />
Displays a successful data exfiltration, bypassing directory restrictions to access and display the contents of a sensitive legal.md.
<a href="https://imgur.com/WXEnvse"><img src="https://i.imgur.com/WXEnvse.png" title="source: imgur.com" /></a>
<br />
<br />
An Insecure Direct Object Reference (IDOR) vulnerability where modifying the basket ID in a Burp Suite Repeater request allows unauthorized access to another user's shopping basket data.
<a href="https://imgur.com/Ha7dtHd"><img src="https://i.imgur.com/Ha7dtHd.png" title="source: imgur.com" /></a>
<br />
<br />
A professional table documenting each vulnerability found, its severity rating, and the specific technical fix (e.g., Parameterized Queries for SQLi).
<a href="https://imgur.com/Ui2IklG"><img src="https://i.imgur.com/Ui2IklG.png" title="source: imgur.com" /></a>

</p>

<h2>7.	Security Principles Demonstrated</h2>

* <b>Input Validation:</b> Identifying the lack of sanitization in user-input fields.
* <b>Secure Coding:</b> Applying principles of "Least Privilege" to database queries and session management.
* <b>Defense in Depth:</b> Recommending a combination of WAF rules and backend code fixes to mitigate OWASP Top 10 risks.

