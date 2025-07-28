<h1>Keylogger Payload Project</h1>



<h2>Description</h2>
The objective of this project is to simulate a USB-based HID attack using a Rubber Ducky device to demonstrate how physical access can lead to system information disclosure. The payload is designed to raise awareness around endpoint vulnerabilities by automatically collecting system details (e.g., IP addresses, hostname, Wi-Fi SSID) and exfiltrating them to a remote GitHub repository. This proof-of-concept highlights the importance of USB security, physical device control, and endpoint monitoring in an organization's defense strategy. The detailed project walkthrough can be found <a href="https://github.com/VemTech6/Keylogger-Payload/blob/main/Project%20Walkthrough.md">HERE</a>.
<br />
<br />

<img src="https://i.imgur.com/g91Y3g7.png" height="80%" width="80%" alt=" Payload Walkthrough"/>


<h2>Methodology</h2>



The payload attack followed a structured process:

| **Phase**             | **Description**                                                                 |
|-----------------------|---------------------------------------------------------------------------------|
| Physical Access       | Simulated attacker plugs in a USB Rubber Ducky into the victim’s machine.      |
| Command Execution     | Executes PowerShell commands to gather system details (IP, SSID, hostname).    |
| Data Exfiltration     | Uploads information to a GitHub repository via REST API (using HTTPS).         |
| Visual Distraction    | Optionally opens Notepad to mask payload activity.                             |
| Post-Attack Review    | Analyzes what detection/prevention controls could mitigate this attack vector. |

</b>


<h2>Findings</h2>

Key observations and results during testing:

<b>

| **Observation**                   | **Severity** | **Notes**                                                                 |
|----------------------------------|--------------|---------------------------------------------------------------------------|
| USB payload executed successfully | High         | Payload was able to run without user interaction once plugged in.        |
| PowerShell not blocked           | Medium       | Default security settings allowed PowerShell to run without restriction. |
| Data exfiltrated via GitHub      | High         | GitHub API successfully received system info using HTTPS.                |
| No endpoint alerts triggered     | Medium       | No AV/EDR flagged the activity during testing.                            |

</b> 

<h2>Recommendations</h2>

Defensive strategies to prevent this type of attack.
<b> 

| **Recommendation**                     | **Purpose / Benefit**                                                              |
|----------------------------------------|------------------------------------------------------------------------------------|
| Disable unused USB ports               | Prevents unauthorized devices from being connected to critical systems.           |
| Implement USB device control software  | Allows only authorized USB peripherals; blocks HID devices like Rubber Ducky.     |
| Monitor PowerShell and scripting usage | Helps detect suspicious or automated script execution behavior.                   |
| Enforce endpoint detection (EDR)       | EDR solutions can flag unusual system commands or unauthorized API requests.      |
| Conduct regular user awareness training| Educates employees on the risks of plugging in unknown or suspicious USB devices. |
| Limit physical access to machines      | Reduces risk of attackers gaining physical access to deliver payloads.            |


</b>

<h2>Conclusion</h2>

<b>This Rubber Ducky payload project demonstrates how a simple HID-based attack can be used to exfiltrate sensitive system information within seconds of physical access. While the payload itself is non-malicious and intended for awareness, it highlights how easily a system can be compromised without the need for elevated privileges or complex malware. The experiment underscores the importance of physical security, USB port management, user training, and endpoint monitoring as critical layers of defense. In a real-world environment, even basic scripts like this could serve as the entry point for much larger attacks if proper controls aren’t in place. This project serves as a reminder that cybersecurity isn't just digital — it starts at the physical layer.</b>



<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
