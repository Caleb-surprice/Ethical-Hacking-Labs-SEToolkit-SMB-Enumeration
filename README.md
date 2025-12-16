# Ethical-Hacking-Labs-SEToolkit-SMB-Enumeration

This repository documents two ethical hacking labs conducted in a controlled lab environment for **educational and security testing purposes only**.

## Labs Covered
1. Website Cloning using SEToolkit (Social Engineering Toolkit)
2. SMB Vulnerability Scanning using Enum4Linux and smbclient

⚠️ **Ethical Disclaimer**
All activities were performed on intentionally vulnerable machines in a lab environment with permission. These techniques must never be used on real systems without authorization.

---

## Lab 1: Website Cloning using SEToolkit

### Objective
To understand how attackers clone websites to harvest credentials and how such attacks can be detected and prevented.

### Tools Used
- Kali Linux
- SEToolkit
- Text Editor
- DVWA (Damn Vulnerable Web Application)

---

## Lab 2: SMB Vulnerability Scanning using Enum4Linux

### Objective
To enumerate SMB services and identify misconfigurations such as anonymous access, shared folders, and exposed user information.

### Tools Used
- Enum4Linux
- Nmap
- smbclient
- Linux Terminal

---

## Skills Gained
- Social engineering awareness
- SMB enumeration and exploitation basics
- Ethical hacking documentation
- Command-line proficiency
- Security risk analysis

---

📌 **Author:** Caleb Kutani  
📌 **Field:** Cybersecurity / Ethical Hacking  


🧪 Lab 1: Website Cloning (SEToolkit)

### Website Cloning using SEToolkit
📌 Explanation (explanation)
In this lab, I used SEToolkit to clone a vulnerable web application to demonstrate how phishing attacks work.

SEToolkit copies the structure of a target website and hosts it locally. Any credentials entered on the cloned site are captured and stored in SEToolkit logs.

This lab helps defenders understand how attackers steal login details and how users can protect themselves.


Commands Used

sudo su

setoolkit

<img width="629" height="548" alt="1  lauch setoolkit" src="https://github.com/user-attachments/assets/22235b68-779f-4d56-9f77-c7b2acdb9699" />


# Menu selections
1   # Social-Engineering Attacks

<img width="629" height="548" alt="1  lauch setoolkit" src="https://github.com/user-attachments/assets/22235b68-779f-4d56-9f77-c7b2acdb9699" />

2   # Website Attack Vectors

<img width="712" height="565" alt="2  website attack" src="https://github.com/user-attachments/assets/5c0e0c6e-91d4-4b34-8fcd-c72350c6ced8" />


3   # Credential Harvester Attack Method

<img width="797" height="563" alt="3  credential harvest" src="https://github.com/user-attachments/assets/f49f0561-34cd-4ecd-8043-c29de351ef29" />

4   # Site Cloner

<img width="785" height="535" alt="5  site cloner" src="https://github.com/user-attachments/assets/51a0af8d-e56c-48af-8641-9fb84a1a8375" />

5. # Site IP & Url
10.6.6.1
http://dvwa.vm

<img width="749" height="109" alt="6  site ip   url to attack" src="https://github.com/user-attachments/assets/c218a8b3-f5fb-4820-aaaa-ec4e72c57869" />


📄 HTML Redirect File (hack1.html)

<html>
<head>
<meta http-equiv="refresh" content="0; url=http://10.6.6.1/" />
</head>
</html>


🧪 Test Credentials Used

Email: ladies@gmail.com

Password: 1234

<img width="1099" height="591" alt="7  cloned site" src="https://github.com/user-attachments/assets/64436023-79de-4984-8fe2-a308530ee4ac" />

📝 Viewing Captured Credentials

<img width="574" height="364" alt="9  saved credentials" src="https://github.com/user-attachments/assets/0761a8ac-d025-4f93-83d2-839fdf9311df" />


🔐 Ethical Note

This lab demonstrates how phishing works so that security professionals can:

Train users

Detect fake websites

Improve security awareness



🧪 Lab 2: SMB Vulnerability Scanning (Enum4Linux)
📌 Explanation findings

This lab focused on enumerating SMB services on a target machine to identify security weaknesses such as anonymous access, open shares, and exposed system information.

SMB misconfigurations are common in internal networks and can lead to serious breaches if not properly secured.

Commands Used

sudo su

# Enum4Linux help
enum4linux -help

# Network scan
nmap -sN 172.17.0.0/24

<img width="745" height="576" alt="1  nmap scan_tcp ports" src="https://github.com/user-attachments/assets/81971b6a-c47e-48f8-91e7-3a2df282e882" />

# Enumeration commands
enum4linux -U 172.17.0.2   # Users

<img width="530" height="606" alt="2  sanning for userlist" src="https://github.com/user-attachments/assets/5b98de3d-7aa3-468f-b85a-694adad97730" />

enum4linux -n 172.17.0.2   # NetBIOS

<img width="681" height="595" alt="3  nbstat" src="https://github.com/user-attachments/assets/f8c3bf06-1604-46d8-895f-5c802258de26" />

enum4linux -o 172.17.0.2   # OS info

<img width="771" height="307" alt="4  os info" src="https://github.com/user-attachments/assets/baa66f19-0f8d-48e5-92bf-1f214d408147" />

enum4linux -S 172.17.0.2   # Shares

<img width="764" height="587" alt="5  sharelist" src="https://github.com/user-attachments/assets/ebb1fe77-a0e6-4deb-9e20-610bf0c570de" />

enum4linux -Sv 172.17.0.2
<img width="826" height="557" alt="6  share verbose" src="https://github.com/user-attachments/assets/b3212cab-897c-4d30-86b3-6f5411f1a381" />


enum4linux -P 172.17.0.2

<img width="790" height="600" alt="7  passw policy" src="https://github.com/user-attachments/assets/2d8a0590-e488-4d6f-8bdf-412788bd173a" />



📂 SMB Client Access

smbclient -L //172.17.0.2/
# Press Enter for password

<img width="752" height="407" alt="8  smbclient see the files on the network" src="https://github.com/user-attachments/assets/aff7aefc-b42c-4c21-b638-40c75acaea76" />

smbclient //172.17.0.2/tmp
# Press Enter


📁 File Upload Test

put virus.exe group_work.txt

<img width="400" height="37" alt="10  put a file" src="https://github.com/user-attachments/assets/333dbf7d-fc3f-4158-a533-a690b537d699" />

file put successful

<img width="659" height="102" alt="11  file put success" src="https://github.com/user-attachments/assets/f6e35530-05cf-473e-bcbd-a2f328af8e80" />


🔍 Findings Summary

Anonymous SMB login allowed

Writable shared folder (/tmp)

Poor access control

Risk of malware upload or data exfiltration


🔐 Security Lesson

Disable anonymous SMB access

Apply proper file permissions

Monitor SMB activity

Harden internal networks
