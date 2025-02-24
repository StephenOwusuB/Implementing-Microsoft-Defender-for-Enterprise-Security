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
| Automated Investigation and Response(AIR) |Automated Investigation and Response        | [Automated Investigation and Response](https://github.com/StephenOwusuB/how-to-use-Live-response)|


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



<h2 align="center">Program walk-through</h2>


# Incident Response Steps in Microsoft Defender

When an attack is detected, follow these steps to investigate and mitigate the issue.

## Step 1: Identify the Affected Device

If you don't know the specific device the attack occurred on:

1. Go to the **Microsoft Defender Portal**.
2. Navigate to the **Incident & Alerts** page.
3. Select **Alerts**.
4. Click the three dots next to the device you want to investigate to view actions you can perform on the device.
5. Select the option to **Open the Device**.

If you already know the affected device:

1. Go to **Assets**.
2. Select **Devices**.
3. Choose the affected device.
4. On the top right, select the three dots and choose **Run Antivirus Scan**.

## Step 2: Run Antivirus Scan

### Quick Scan vs Full Scan:

- **Quick Scan**: Scans critical areas where malware might be present, such as registry keys and Windows startup folders. It helps protect against kernel-level malware and uses real-time protection to monitor open and closed files or folder navigation.
- **Full Scan**: After a quick scan, it performs a comprehensive scan of all mounted fixed and removable drives, network drives, and more. This can take hours or even days.

### Process:

1. If you select **Quick Scan**, provide a description (e.g., "Alert Investigation") and click **Confirm**.
2. This action will be logged in the **Action Center**.
3. After a few minutes, go to **Actions & Submissions** > **Action Center** > **History** to view the scan results.

If the **Run Antivirus Scan** option is still greyed out, it means the scan is still in progress. In that case:

1. Select **Collect Investigation Package**. This will help identify the current state of the device and the tools/techniques used by the attacker.
2. Specify the description and click **Confirm**.
3. Select **Action Center** to view the status of the package collection.
4. Download the zip file from **Package Collection**.

## Step 3: Investigate Collected Data

1. Extract the zip file and explore the following folders to gather details about the attack:

- **Autoruns**: Identifies persistence mechanisms through registry keys.
- **Installed Programs**: Lists installed programs on the device.
- **Network Connections**: Shows any suspicious URLs or connections to command-and-control infrastructure.
- **Prefetch**: Contains recently used files or deleted data related to application startup.
- **Processes**: Shows running processes, including any suspicious ones.
- **Scheduled Tasks**: Displays scheduled tasks on the system.
- **Security Event Log**: Contains logon and logoff events.
- **Services**: Displays active services on the device.
- **SMB**: Lists shared access to files, printers, and serial ports.
- **System Information**: Includes OS version and network card details.
- **Temp Directories**: Lists files located in the temp directory.
- **Users and Groups**: Shows the users and groups on the device.
- **WDSupportLogs**: Logs from Western Digital software.
- **Forensic Collection File**: Contains information about commands used to retrieve files.

## Step 4: Take Actions on the Device

### Restrict App Execution:

1. In the Defender portal, on the device page, select the three dots and choose **Restrict App Execution**. This will prevent any non-Microsoft apps from running, allowing only Microsoft apps to execute.

### Initiate Automated Investigation:

1. Initiate an **Automated Investigation** to analyze suspicious behavior. A notification will confirm the investigation has been initiated.

### Initiate Live Response:

1. If needed, initiate a **Live Response Session** for real-time investigation and remediation.

### Isolate the Device:

1. **Isolate the Device** to disconnect it from the network while remaining connected to Microsoft Defender for Endpoint.
2. You can allow users to access Outlook, Teams, and Skype for Business during isolation.
3. If the device becomes unresponsive when releasing isolation, use the **Force Release from Isolation** script.

## Step 5: Actions for Unmanaged Devices

For **Unmanaged Devices** (devices not managed by your IT department):

1. Use the **Device Discovery** feature to identify unmanaged devices.
2. If an unmanaged device is compromised, you can **Contain** the device to stop communication with your network.
3. If necessary, you can **Release** the device from containment.

## Step 6: Additional Actions for Suspicious Files

### Respond to a Suspicious File:

1. Stop, quarantine, or add the file to custom indicators.
2. You can also **Download the File** for further analysis.

### Search for Suspicious File:

1. If you know the name of the file, search for it in the Defender portal.
2. If you don’t find it, type “file” in the search bar and locate the file.
3. On the file's page, you can view metadata, detect incidents, and analyze the file's impact.

### Add File as an Indicator:

1. If you suspect the file is malicious, add it as an indicator by specifying the **File Hash**.
2. Select actions for how to handle the file (e.g., block, warn, audit).
3. Review the statistics and proceed to organizational scope before submitting.

### Download and Analyze the File:

1. If the file has been seen on your devices within the last 30 days, you can **Download** the file for further analysis.
2. The file will be zipped, password-protected, and stored in your downloads folder. You must create a password to access the file.
3. Use a sandbox or other analysis tools to investigate the file's behavior.

### Submit for Deep Analysis:

1. Initiate **Deep Analysis** of the file to review its activity, behaviors, associated artifacts, and communications with suspicious IPs.

## Step 7: Action Center

1. All actions taken during the investigation will be logged in the **Action Center**.
2. You can also use the **Go Hunt** tab for custom queries to gather more information.

### View File Reputation:

1. You can view the file's reputation using **VirusTotal** by selecting **View in VirusTotal** on the file's page overview.

---

These are the actions you can take when responding to a detected attack. Following these steps will help you to investigate, contain, and mitigate the issue effectively.

