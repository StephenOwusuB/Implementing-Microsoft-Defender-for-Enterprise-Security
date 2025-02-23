<h1>Implementing-Microsoft-Defender-for-Enterprise-Security</h1>

<h2>Description</h2>
<b>This project focuses on deploying and configuring Microsoft Defender to enhance the security posture of an enterprise environment. The goal is to leverage Microsoft Defender's comprehensive security features to protect against cyber threats, manage vulnerabilities, and ensure compliance with security standards.<b/>
<br />

<h2>Description</h2>
<b>Below are related labs that I will recommend taking a look at before completing this lab.<b/>
<br />
  
| Home Lab                      | Description                                            | Link                                                                  |
|-------------------------------|--------------------------------------------------------|-----------------------------------------------------------------------|
| Defender via GPO              | Deploy Defender via GPO                                | [Defender via GPO](https://github.com/StephenOwusuB/Defender-via-GPO) |
| Defender via Local script     | Deploy Defender via Local script                       | [Defender via Local script](https://github.com/StephenOwusuB/Defender-via-Local-script) |
| Test Antivirus                |How to test antivirus using EICAR file                  | [Test Antivirus](https://github.com/StephenOwusuB/Test-Antivirus-WD-) |
| Submissions(Microsoft Analysis)|How to submit files, emails, teams messages, URLs      | [Submissions](https://github.com/StephenOwusuB/Submissions-Microsoft-Analysis-) |
| Network Protection            |Network Protection in MDE Attack Surface Reduction (ASR)| [Network Protection ASR](https://github.com/StephenOwusuB/Network-Protection-in-MDE-Attack-Surface-Reduction-ASR-) |
| Defender for Cloud Apps       |Lock down Cloud apps & protect data                     | [Defender For Cloud Apps](https://github.com/StephenOwusuB/Defender-for-Cloud-Apps) |
| Live Response                 |How to use Live Responsetest                            | [Live Response](https://github.com/StephenOwusuB/how-to-use-Live-response)|

<h2>This Lab</h2>
<b>Attack Detection and Response using Microsoft Defender. For Microsoft Defender for Endpoints (MDE), you can choose either a P1 or P2 license. The P2 license offers more capabilities and advanced features.<b/>
<br />

<h2>Utilities Used</h2>

- <b>Microsoft Sentinel (SIEM)</b> 
- <b>Log Analytic Workbooks</b>
- <b>Microsoft Defender for Cloud</b>
- <b>Virtual Machines</b>
- <b>Remote Desktop</b>
- <b>PowerShell</b>
- <b>API's</b>
- <b>Event Viewer</b>
- <b>Firewalls</b>

<h2>Environments Used </h2>

- <b>Microsoft Azure</b>
- <b>Windows 10</b> (21H2)

<h2>Links</h2>

- <b>Microsoft Azure Free Trial:</b> https://azure.microsoft.com/en-us/free/
- <b>IPGeolocation:</b> https://ipgeolocation.io/

<h2 align="center">Program walk-through</h2>

<p align="center">
<b>The first step in project is to create a Microsoft Azure account, which will serve as  the cloud environment for provision my resources. I'll take advantage of the $200 credit  that comes with the account to fund this project. Given that the resources I'll be using are not resource-intensive, I'll be able to save some of the credit for future endeavors. Additionally, I'll be utilizing a specific website for my IP geolocation.  </b> <br/>
</p>

![Create_Azure_Subscription](https://user-images.githubusercontent.com/108043108/225348757-c41744df-2be1-4ffc-87a6-aa258a4102ef.JPG)
![Set_Up_Completed](https://user-images.githubusercontent.com/108043108/225348950-5d9c01fa-a707-4813-a6f3-012c703c41df.JPG)
![IPGEO](https://user-images.githubusercontent.com/108043108/225456045-a2a5b61c-b0ba-49a0-9552-92bf0c8d1cf1.JPG)
