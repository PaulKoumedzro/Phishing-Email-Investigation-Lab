# Phishing Email Investigation Lab

# Objective
The objective of this lab is to simulate a real-world phishing email investigation, focusing on identifying potential threats and assessing their impact. This exercise involves a comprehensive analysis of the email header and body to determine the sender's identity, trace associated IP addresses, and examine mail server pathways. Encoded URLs and suspicious content will be decoded and scrutinized for indicators of compromise. The findings will be documented in a structured investigation report, followed by actionable security recommendations to mitigate future phishing risks.

# Skills Learned
- Extracting and interpreting metadata to identify spoofed sender addresses, return paths, and relay servers.
- Mapping IP addresses to geographic locations and identifying suspicious routing patterns.
- Revealing obfuscated or encoded URLs to detect malicious payloads or phishing sites.
- Identifying embedded threats in attachments or links using sandboxing or static analysis.
-  Using OSINT and pattern recognition to hypothesize attacker profiles or campaigns.
-  Connecting disparate indicators (headers, URLs, IPs) to build a coherent threat narrative.



# Tool Used
- Notepad++ text editor
- AbuseIPdb
- CyberChef
- EML-Analyzer
- Vmware
- Windows 10


  # Steps
  Fig1: The email is opened in Notepad++, and the Email Properties are highlighted.
  <img width="1888" height="840" alt="image" src="https://github.com/user-attachments/assets/57d27cfc-e9dc-49db-b355-7b92a532ffff" />

  Fig2: The email’s sent date can be identified in the screenshot below, showing it was sent on December 6, 2023, at 20:59:57 (CST, +0800).
  ![2](https://github.com/user-attachments/assets/059dda57-3298-4973-bb80-2a0f7c61ae75)


  Fig3: Examining the email security configuration, the Authentication-Results show that DKIM is set to NONE, DMARC is set to NONE, and SPF is set to Softfail. Additionally, the message is not signed, indicating a failure in the email security configuration. The sender’s IP address is 183.56.179.169, and the header indicates that the email was sent from the domain name sasktel.com.
 ![3](https://github.com/user-attachments/assets/6f51adbc-4213-40bb-9cff-58adbb974d9e)

  Fig4: The screenshot below reveals that the nearest email server to the sender is mail.yobow.cn, which will be the subject of further OSINT investigation.
  <img width="1919" height="960" alt="image" src="https://github.com/user-attachments/assets/0be7c587-b649-46dd-9633-fea3edd5859c" />

  Fig5: As shown in the screenshot below, the Reply-To email agentcynthiajamescontact01[@]gmail.com and the "From" email p.chambers[@]sasktel.com addresses differ; an unusual discrepancy that raises significant security concerns.
![4](https://github.com/user-attachments/assets/16a52899-57dd-4b72-8ad6-0d4d4dcdc5bc)


# In the following steps, we'll perform OSINT on our findings as proof of concept , investigate further determine the nature  and content of the email.

  Fig6: We will conduct OSINT (Open Source Intelligence) on the IP address 183.56.179.169, which was identified in the email. Refer to Figure 3 for visual context. As shown in the screenshot, the IP originates from China, specifically the Guangdong Province Network, and is associated with the ISP China Telecom (domain: chinatelcom.cn). This IP address has been reported 10 times, primarily flagged for email spam and is linked to malicious activity.
  ![5](https://github.com/user-attachments/assets/0e1f076b-70fb-47db-984a-5baa860a4db0)

Fig7-a: The screenshot below reveal that the Content-type of this email will be render as a webpage or html. follow by the body of the email.
![6](https://github.com/user-attachments/assets/33d66d88-5628-458e-bd3a-1cc7ece9ba91)

Fig7-b![7](https://github.com/user-attachments/assets/a882368c-f19e-491c-859f-0e4a2a4ff10e)

Fig8: The HTML version of the email body (see Figure 7-b) was converted into plain text for further analysis.
![8](https://github.com/user-attachments/assets/25d6a564-7b4a-4d8b-bd38-8894e0944c67)

Fig9: Complete email analysis with Sublime-Security flag the email as Malicious Business Email Compromise.
![9](https://github.com/user-attachments/assets/1b0db9dc-7f1a-4b1c-9bbf-12d54c6e5042)


# Phishing Email Investigation Report

Date of Incident: December 6, 2023<br>
Time of Receipt: 20:59:57 CST (+0800)<br>
Sender Email Address: <br>
Subject Line: Attention Dear Beneficiary<br>
Phishing Type: Business Email Compromise (BEC)

# Summary of Findings
A suspicious email was received on December 6, 2023, appearing to originate from . The subject line, Attention Dear Beneficiary, and the body content suggest a Business Email Compromise (BEC) attempt targeting corporate users.
The email impersonates Lynn Malerba, Treasurer of the United States, and falsely claims the recipient is entitled to $16,000,000 in COVID-19 relief funds. The message urges the recipient to download an attached ID card, which is likely a malicious file intended to gain unauthorized access to the recipient’s system or network.

# Thechnical Analysis
The authentication failures such as SPF, DKIM, DMARC vailidation all failed. these failures indicate the email was not sent froma trusted or authorized  source and is likely spoofed.  There is a mismatch between the "From" and "Reply-To" fields this inconsistency is a common tactic used in phishing campaigns to redirect replies to an attacker-controlled inbox. The sender IP address has been reported 10 times for malicious activity and is categorized as a known source of email spam.

# Conclusion
Based on the evidence collected—authentication failures, header anomalies, malicious intent, and sender reputation—the email is conclusively flagged as malicious. The attachment and social engineering tactics used are consistent with initial access techniques employed in phishing and BEC attacks.

# Recommendations
- User Awareness Training: Educate users on identifying and reporting phishing attempts.
- Attachment & Link Caution: Instruct users not to click on links or open attachments from unknown senders.
- Simulated Phishing Exercises: Conduct regular phishing simulations to reinforce detection and response skills.


