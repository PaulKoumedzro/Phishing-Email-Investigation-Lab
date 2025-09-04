# Phishing Email Investigation Lab

# Objective
The objective of this lab is to simulate real-world cyber threats by evaluating the security posture of an Active Directory a network environment. The lab aims to identify vulnerabilities in systems, applications, and configurations in the AD, assess their potential exploitability, and mitigating security flaws . The purpose of the testing is to identify and document weaknesses in Active Directory that could be exploited by malicious actors; improve defensive strategies by recommending mitigation techniques and security ehancements.

# Skills Learned
- Enumerate and map the AD environment, including domains, forests, and trust relationships.
- Identify key components such as Domain Controllers, organizational units (OUs), and group policies.
- Analyze password policies, Kerberos configurations, and credential storage.
- Simulate attacks like Pass-the-Hash, Kerberoasting, and credential spraying.
- Discover and exploit misconfigured permissions, service accounts, and group memberships to escalate privileges.
- Identify misconfigurations in Group Policy Objects (GPOs) that may allow privilege escalation or data leaka


# Tool Used
- Nmap an ONSIT tool used for reconnaissance and enumeration
- https://www.exploit-db.com/ a vulnerability database
- Metasploitable
- Windows 10
- Active Directory 2022
- Vmware

I have found and exploited vulnerability in the Active Directory used in the network. Below are steps I took from discovery to exploitaion.

  # Steps
  Fig1: The email is opened in Notepad++, and the Email Properties are highlighted.
  <img width="1888" height="840" alt="image" src="https://github.com/user-attachments/assets/57d27cfc-e9dc-49db-b355-7b92a532ffff" />

  Fig2: The email’s sent date can be identified in the screenshot below, showing it was sent on December 6, 2023, at 20:59:57 (CST, +0800).
  ![2](https://github.com/user-attachments/assets/059dda57-3298-4973-bb80-2a0f7c61ae75)


  Fig3: Examining the email security configuration, the Authentication-Results show that DKIM is set to NONE, DMARC is set to NONE, and SPF is set to Softfail. Additionally, the message is not signed, indicating a failure in the email security configuration. The sender’s IP address is 183.56.179.169, and the header indicates that the email was sent from the domain name sasktel.com.
 ![3](https://github.com/user-attachments/assets/6f51adbc-4213-40bb-9cff-58adbb974d9e)


  Fig4: Using mimikatz, we were able perform Active Directory persistence through credential.
  ![2](https://github.com/user-attachments/assets/2dbdb630-2039-4050-b9fc-500616a68ac8)

  Fig5: As poof of concept, we able to get user account hash and crack it.
  ![3](https://github.com/user-attachments/assets/e895a387-0b1d-4e6a-99cd-f5360331e7c9)

  

# Network scan result
  <a href="https://tinyurl.com/Network-Scan-result">Download the scan result</a>

# Recommandation.
Implement  Multifactor Authentication mechanism </br>
Disabled Powershell and cmd on systems </br>
Setup real-time alert </br>
Enforce strong password policies  </br>
Use separate administrative accounts for domain admins and standard user accounts.</br>
Restrict GPO delegation to prevent unauthorized changes.
