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
Launch the utility: <br/>
<img src="https://i.imgur.com/62TgaWL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the disk:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
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
