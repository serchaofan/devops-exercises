# Security

<details>
<summary>Can you describe the DevSecOps core principals?</summary><br><b>
</b></details>

<details>
<summary>What DevOps security best practices are you familiar with?</summary><br><b>
</b></details>

<details>
<summary>What security techniques are you familiar with?</summary><br><b>
</b></details>

<details>
<summary>Explain Authentication and Authorization</summary><br><b>

Authentication is the process of identifying whether a service or a person is who they claim to be.
Authorization is the process of identifying what level of access the service or the person have (after authentication was done)
</b></details>

<details>
<summary>How do you manage passwords in different tools and platforms?</summary><br><b>
</b></details>

<details>
<summary>Explain what is Single Sign-On</summary><br><b>

SSO (Single Sign-on), is a method of access control that enables a user to log in once and gain access to the resources of multiple software systems without being prompted to log in again.

</b></details>

<details>
<summary>Explain MFA (Multi-Factor Authentication)</summary><br><b>

Multi-Factor Authentication (Also known as 2FA). Allows the user to present two pieces of evidence, credentials, when logging into an account.

- The credentials fall into any of these three categories: something you know (like a password or PIN), something you have (like a smart card), or something you are (like your fingerprint). Credentials must come from two different categories to enhance security.

</b></details>

<details>
<summary>Explain RBAC (Role-based Access Control)</summary><br><b>

Access control based on user roles (i.e., a collection of access authorizations a user receives based on an explicit or implicit assumption of a given role). Role permissions may be inherited through a role hierarchy and typically reflect the permissions needed to perform defined functions within an organization. A given role may apply to a single individual or to several individuals.

- RBAC mapped to job function, assumes that a person will take on different roles, overtime, within an organization and different responsibilities in relation to IT systems.

</b></details>

<details>
<summary>Explain Symmetric encryption</summary><br><b>

A symmetric encryption is any technique where the same key is used to both encrypt and decrypt the data.

</b></details>

<details>
<summary>Explain Asymmetric encryption</summary><br><b>

A asymmetric encryption is any technique where the there is two different keys that are used for encryption and decryption, these keys are known as public key and private key.

</b></details>

<details>
<summary>Explain the following:

- Vulnerability
- Exploits
- Risk
- Threat</summary><br><b>
  </b></details>

<details>
<summary>What is XSS?</summary><br><b>

Cross Site Scripting (XSS) is an type of a attack when the attacker inserts browser executable code within a HTTP response. Now the injected attack is not stored in the web application, it will only affact the users who open the maliciously crafted link or third-party web page. A successful attack allows the attacker to access any cookies, session tokens, or other sensitive information retained by the browser and used with that site

You can test by detecting user-defined variables and how to input them. This includes hidden or non-obvious inputs such as HTTP parameters, POST data, hidden form field values, and predefined radio or selection values. You then analyze each found vector to see if their are potential vulnerabilities, then when found you craft input data with each input vector. Then you test the crafted input and see if it works.
</b></details>

<details>
<summary>What is an SQL injection? How to manage it?</summary><br><b>

SQL injection is an attack consists of inserts either a partial or full SQL query through data input from the browser to the web application. When a successful SQL injection happens it will allow the attacker to read sensitive information stored on the database for the web application.

You can test by using a stored procedure, so the application must be sanitize the user input to get rid of the tisk of code injection. If not then the user could enter bad SQL, that will then be executed within the procedure

</b></details>

<details>
<summary>What is Certification Authority?</summary><br><b>
</b></details>

<details>
<summary>How do you identify and manage vulnerabilities?</summary><br><b>
</b></details>

<details>
<summary>Explain "Privilege Restriction"</summary><br><b>
</b></details>

<details>
<summary>How HTTPS is different from HTTP?</summary><br><b>
</b></details>

<details>
<summary>What types of firewalls are there?</summary><br><b>
</b></details>

<details>
<summary>What is DDoS attack? How do you deal with it?</summary><br><b>
</b></details>

<details>
<summary>What is the difference between asynchronous and synchronous encryption?</summary><br><b>
</b></details>

<details>
<summary>Explain Man-in-the-middle attack</summary><br><b>
</b></details>

<details>
<summary>Explain CVE and CVSS</summary><br><b>
</b></details>

<details>
<summary>What is ARP Poisoning?</summary><br><b>
</b></details>

<details>
<summary>Describe how do you secure public repositories</summary>
</b></details>

<details>
<summary>How do cookies work?</summary><br><b>
</b></details>

<details>
<summary>What is DNS Spoofing? How to prevent it?</summary><br><b>

DNS spoofing occurs when a particular DNS server’s records of “spoofed” or altered maliciously to redirect traffic to the attacker. This redirection of traffic allows the attacker to spread malware, steal data, etc.

**Prevention**

- Use encrypted data transfer protocols - Using end-to-end encryption vian SSL/TLS will help decrease the chance that a website / its visitors are compromised by DNS spoofing.
- Use DNSSEC - DNSSEC, or Domain Name System Security Extensions, uses digitally signed DNS records to help determine data authenticity.
- Implement DNS spoofing detection mechanisms - it’s important to implement DNS spoofing detection software. Products such as XArp help product against ARP cache poisoning by inspecting the data that comes through before transmitting it.

</b></details>

<details>
<summary>What can you tell me about Stuxnet?</summary><br><b>

Stuxnet is a computer worm that was originally aimed at Iran’s nuclear facilities and has since mutated and spread to other industrial and energy-producing facilities. The original Stuxnet malware attack targeted the programmable logic controllers (PLCs) used to automate machine processes. It generated a flurry of media attention after it was discovered in 2010 because it was the first known virus to be capable of crippling hardware and because it appeared to have been created by the U.S. National Security Agency, the CIA, and Israeli intelligence.

</b></details>

<details>
<summary>What can you tell me about Spectre?</summary><br><b>

Spectre is an attack method which allows a hacker to “read over the shoulder” of a program it does not have access to. Using code, the hacker forces the program to pull up its encryption key allowing full access to the program

</b></details>

<details>
<summary>Explain OAuth</summary><br><b>
</b></details>

<details>
<summary>Explain "Format String Vulnerability"</summary><br><b>
</b></details>

<details>
<summary>Explain DMZ</summary><br><b>
</b></details>

<details>
<summary>Explain TLS</summary><br><b>
</b></details>

<details>
<summary>What is CSRF? How to handle CSRF?</summary><br><b>

Cross-Site Request Forgery (CSRF) is an attack that makes the end user to initate a unwanted action on the web application in which the user has a authenticated session, the attacker may user an email and force the end user to click on the link and that then execute malicious actions. When an CSRF attack is successful it will compromise the end user data

You can use OWASP ZAP to analyze a "request", and if it appears that there no protection against cross-site request forgery when the Security Level is set to 0 (the value of csrf-token is SecurityIsDisabled.) One can use data from this request to prepare a CSRF attack by using OWASP ZAP
</b></details>

<details>
<summary>Explain HTTP Header Injection vulnerability</summary><br><b>

HTTP Header Injection vulnerabilities occur when user input is insecurely included within server responses headers. If an attacker can inject newline characters into the header, then they can inject new HTTP headers and also, by injecting an empty line, break out of the headers into the message body and write arbitrary content into the application's response.

</b></details>

<details>
<summary>What security sources are you using to keep updated on latest news?</summary><br><b>
</b></details>

<details>
<summary>What TCP and UDP vulnerabilities are you familiar with?</summary><br><b>
</b></details>

<details>
<summary>Do using VLANs contribute to network security?</summary><br><b>
</b></details>

<details>
<summary>What are some examples of security architecture requirements?</summary><br><b>
</b></details>

<details>
<summary>What is air-gapped network (or air-gapped environment)? What its advantages and disadvantages?</summary><br><b>
</b></details>

<details>
<summary>Explain what is Buffer Overflow</summary><br><b>

A buffer overflow (or buffer overrun) occurs when the volume of data exceeds the storage capacity of the memory buffer. As a result, the program attempting to write the data to the buffer overwrites adjacent memory locations.
</b></details>

##### Containers

<details>
<summary>What security measures are you taking when dealing with containers?</summary><br><b>
</b></details>

<details>
<summary>Explain what is Docker Bench</summary><br><b>
</b></details>

<a name="security-advanced"></a>

#### :baby: Advanced

<details>
<summary>Explain MAC flooding attack</summary><br><b>

MAC address flooding attack (CAM table flooding attack) is a type of network attack where an attacker connected to a switch port floods the switch interface with very large number of Ethernet frames with different fake source MAC address.

</b></details>

<details>
<summary>What is "Diffie-Hellman key exchange" and how does it work?</summary><br><b>
</b></details>

<details>
<summary>Explain "Forward Secrecy"</summary><br><b>
</b></details>

<details>
<summary>What is Cache Poisoned Denial of Service?</summary><br><b>

CPDoS or Cache Poisoned Denial of Service. It poisons the CDN cache. By manipulating certain header requests, the attacker forces the origin server to return a Bad Request error which is stored in the CDN’s cache. Thus, every request that comes after the attack will get an error page.

</b></details>
