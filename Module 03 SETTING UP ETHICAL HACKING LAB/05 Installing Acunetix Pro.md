# Installing Acunetix Pro

## 1. Download Acunetix Pro
1. Visit the [Acunetix website](https://www.acunetix.com/) and log in with your account credentials.
2. Navigate to the "Download" section and select the installer for your operating system (Windows or Linux).

## 2. Installation on Different Operating Systems

### Windows
1. Run the `.exe` installer you downloaded.
2. Follow the installation wizard's prompts:
   - Accept the License Agreement.
   - Choose the installation directory.
   - Select whether to install Acunetix as a standalone or with other components like the database.
3. Complete the installation by clicking `Finish`.
4. After installation, you can launch Acunetix Pro from the Start menu or desktop shortcut.

### Linux
1. Connect to your server via SSH.
2. Make the downloaded file executable using the following command:

   ```bash
   chmod +x acunetix_trial.sh
   ```
Run the installer:

```bash
sudo ./acunetix_trial.sh
```
Follow the on-screen prompts to complete the installation.

Access the Acunetix web interface via https://<your-server-ip>:3443/ in your browser.

3. Activating Acunetix Pro
Launch Acunetix Pro.
In the web interface, go to Settings > License.
Enter your license key, which was provided when you purchased Acunetix Pro.
Click Activate to complete the activation.
4. Configuring Acunetix Pro
After installation, you should configure a few settings:

Targets: Add the websites or IP addresses you want to scan.
Scan Settings: Configure scan profiles and schedules according to your needs.
Notifications: Set up email or webhook notifications for scan results.
5. Post-Installation
Integrations: Integrate Acunetix with other tools like Jenkins, Jira, or GitLab if needed.
User Management: Add users and assign roles to manage access to Acunetix Pro.
Custom Configuration: Adjust any custom settings to fit your security testing workflows.
Once installed and configured, Acunetix Pro will be ready to perform web vulnerability scans on your targets.

