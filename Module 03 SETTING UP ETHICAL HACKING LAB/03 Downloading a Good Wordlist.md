# Downloading a Good Wordlist

Wordlists are essential for various security testing activities, including password cracking and vulnerability assessments. Here’s how you can download a good wordlist:

## 1. **Common Wordlists**

### **SecLists**

SecLists is one of the most popular collections of wordlists used in security testing. It includes a wide range of wordlists for different purposes.

- **Repository**: [SecLists on GitHub](https://github.com/danielmiessler/SecLists)
- **Download**:
  - Clone the repository using Git:

    ```bash
    git clone https://github.com/danielmiessler/SecLists.git
    ```

  - Navigate to the desired folder inside the SecLists directory to find specific wordlists (e.g., `SecLists/Passwords/`).

### **RockYou**

The RockYou wordlist is widely used for password cracking and contains passwords leaked from the RockYou breach.

- **Download**:
  - You can find the RockYou wordlist as part of many penetration testing distributions, such as Kali Linux. It is located at `/usr/share/wordlists/rockyou.txt.gz`.

  - If you need to download it separately, you can use the following link:

    - [RockYou Wordlist](https://github.com/praetorian-inc/Hob0Rules/blob/master/wordlists/rockyou.txt.gz)

  - To download it using `wget`:

    ```bash
    wget https://github.com/praetorian-inc/Hob0Rules/raw/master/wordlists/rockyou.txt.gz
    ```

  - Extract the file:

    ```bash
    gunzip rockyou.txt.gz
    ```

## 2. **Custom Wordlists**

If you need a wordlist tailored to specific requirements or languages, you might consider creating your own or using a custom wordlist generator.

### **Crunch**

Crunch is a tool used to generate custom wordlists based on specific criteria.

- **Install Crunch**:

  ```bash
  sudo apt-get install crunch
  ```

# Generating a Custom Wordlist

## Using Crunch

Crunch is a versatile tool for generating custom wordlists based on specific criteria.

### Basic Command

To generate a custom wordlist, use the following syntax:

```bash
crunch <min-len> <max-len> <charset> -o <output-file>
```