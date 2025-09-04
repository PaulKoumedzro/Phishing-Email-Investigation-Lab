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
  Fig1:The screenshot below demonstrates the enumeration and scanning phase using Nmap to scan the entire network, identifying devices, systems, and other connected components.
  ![Capture](https://github.com/user-attachments/assets/bb0b819e-fba2-4864-a9f7-7b441d6ee33a)

  Fig2: The scan is complete and the result is listed.
  ![Capture](https://github.com/user-attachments/assets/f6b740bf-eb7a-4bfd-835d-68c22d51f79f)

  Fig3:The following screenshot shows the exploitation phase of vulnerability discovered In the Active Directory.
  ![Capture](https://github.com/user-attachments/assets/0e87b044-552b-4c98-a1f7-ce755587cd9c)

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
