# Social Engineering Using SET (Social-Engineer Toolkit)

The **Social-Engineer Toolkit (SET)** is an open-source framework designed to perform advanced social engineering attacks against various targets. Developed by David Kennedy, SET simplifies the creation and execution of highly effective attacks, making it a popular tool among penetration testers and ethical hackers.

---

## Key Features of SET
- **Phishing Campaigns**: Automates phishing emails and fake websites to steal credentials.
- **Payload Delivery**: Generates malicious payloads to compromise target systems.
- **Customizable Attacks**: Offers pre-built attack vectors with room for customization.
- **User-Friendly Interface**: Intuitive CLI-based menu system for ease of use.

---

## Common Social Engineering Attacks Using SET

### 1. **Phishing Attacks**
SET can clone legitimate websites and host them locally to trick victims into entering sensitive information like usernames, passwords, or credit card details.

#### Example:
- Cloning a bank’s login page and sending a link to the victim via email.

**Steps**:
1. Select `Social-Engineering Attacks` > `Website Attack Vectors`.
2. Choose `Credential Harvester Attack`.
3. Clone the target website or create a custom one.
4. Send the link to the victim.

---

### 2. **Spear Phishing**
SET automates the creation of spear-phishing emails by embedding malicious payloads or links designed to compromise the victim’s system.

#### Example:
- Sending an email that appears to be from HR with a fake PDF attachment containing malware.

**Steps**:
1. Select `Social-Engineering Attacks` > `Email Attack Vector`.
2. Choose `Spear Phishing Attack`.
3. Configure email settings and payload.
4. Launch the attack.

---

### 3. **USB HID Attack**
SET generates malicious payloads to be delivered via USB drives, exploiting human curiosity to run the payload on the target machine.

#### Example:
- Dropping USB drives labeled "Confidential" in public areas to tempt victims into plugging them in.

**Steps**:
1. Select `Infectious Media Generator` from the menu.
2. Choose the payload (e.g., reverse shell).
3. Copy the payload onto a USB drive.

---

### 4. **Java Applet Attack**
SET exploits browser vulnerabilities by hosting a malicious Java applet that executes a payload when the victim visits the attacker’s page.

#### Example:
- Hosting a fake game website that prompts the user to run a Java applet.

**Steps**:
1. Select `Social-Engineering Attacks` > `Website Attack Vectors`.
2. Choose `Java Applet Attack Method`.
3. Configure the payload and launch the attack.

---

### 5. **PowerShell Attack Vectors**
SET uses PowerShell scripts to deliver malicious payloads directly to the victim’s system, bypassing some traditional defenses.

#### Example:
- Executing a PowerShell script on a Windows machine to gain remote access.

**Steps**:
1. Select `PowerShell Attack Vectors` from the menu.
2. Configure the payload and listener.
3. Deliver the script via phishing or another method.

---

## How SET Works
SET operates by:
1. **Creating a Delivery Mechanism**: This can be a phishing email, malicious website, USB drive, etc.
2. **Generating a Payload**: Malicious code designed to exploit vulnerabilities and gain access to systems.
3. **Exploiting Human Vulnerabilities**: Relies on users to execute the payload by clicking links, running programs, or entering sensitive information.

---

## Ethical Use of SET
SET is a powerful tool and should only be used for ethical purposes:
- **Penetration Testing**: Assessing an organization’s vulnerability to social engineering attacks.
- **Awareness Training**: Demonstrating attack scenarios to educate employees and improve security practices.
- **Compliance Testing**: Ensuring adherence to security regulations.

**Note**: Unauthorized use of SET is illegal and unethical. Always obtain explicit permission before using it in any testing environment.

---

## Mitigating SET-Based Attacks
1. **Employee Training**: Educate staff on recognizing phishing and other social engineering tactics.
2. **Multi-Factor Authentication (MFA)**: Adds a layer of protection even if credentials are stolen.
3. **Email Filters**: Block suspicious emails and attachments.
4. **Patch Systems Regularly**: Fix vulnerabilities that could be exploited by payloads.
5. **Limit Privileges**: Restrict user permissions to minimize potential damage.

The **Social-Engineer Toolkit (SET)** is a potent framework for demonstrating and understanding social engineering attacks. Its power highlights the importance of robust security practices and continuous user education.
