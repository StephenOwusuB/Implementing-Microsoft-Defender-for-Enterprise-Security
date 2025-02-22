<h1>Implementing-Microsoft-Defender-for-Enterprise-Security</h1>

<h2>Description</h2>
<b>In this project, I leveraged Microsoft Azure to create and manage a cloud-based virtual machine running Windows 10. By exposing this VM to the internet, I harnessed the power of Azure Log Analytics Workspace, Microsoft Defender for Cloud, and Azure Sentinel to gather and analyze attack data, visualizing it on a map within Microsoft Sentinel. To dive deeper, I utilized PowerShell to monitor the Event Viewer on the exposed VM, specifically targeting EventID 4625 for failed logon attempts. This data was collected in a logfile, and through an API integration with IPgeolocation.io, I mapped the origins of these logon attempts using Microsoft Sentinel.This hands-on experience enriched my understanding of SIEMs, cloud services, APIs, and Microsoft Azure. I mastered the provisioning and configuration of cloud resources, gained proficiency in interpreting SIEM logs, and much more.I thoroughly enjoyed this project and hope it inspires readers to undertake similar projects or leverage the insights gained here to explore even more possibilities with Azure.<b/>
<br />

<h2>Description</h2>
<b>Below are related labs that I will recommend taking a look at before completing this lab.<b/>
<br />
  
| Home Lab                      | Description                                            | Link                                                                  |
|-------------------------------|--------------------------------------------------------|-----------------------------------------------------------------------|
| Defender via GPO              | Deploy Defender via GPO                                | [Defender via GPO](https://github.com/StephenOwusuB/Defender-via-GPO) |
| Defender via Local script     | Deploy Defender via Local script                       | [Defender via Local script](https://github.com/StephenOwusuB/Defender-via-Local-script) |
| Test Antivirus                |How to test antivirus using EICAR file                  | [Test Antivirus](https://github.com/StephenOwusuB/Test-Antivirus-WD-) |
| Submissions(Microsoft Analysis)|How to submit files, emails, teams messages, URLs       | [Submissions](https://github.com/StephenOwusuB/Submissions-Microsoft-Analysis-) |
| Network Protection            |Network Protection in MDE Attack Surface Reduction (ASR)| [Network Protection ASR](https://github.com/StephenOwusuB/Network-Protection-in-MDE-Attack-Surface-Reduction-ASR-) |
| Defender for Cloud Apps       |Lock down Cloud apps & protect data                     | [Defender For Cloud Apps](https://github.com/StephenOwusuB/Defender-for-Cloud-Apps) |
| Live Response                 |How to use Live Responsetest|                           | [GitHub Link](https://github.com/yourusername/projectC) |

<h2>Description</h2>
<b>Attack Detection and Response using Microsoft Defender<b/>
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
