<h1>Wireless Penetration Testing Project</h1>



<h2>Description</h2>
The objective of this penetration test was to simulate an attacker attempting to gain unauthorized access to a WPA2-protected Wi-Fi network using publicly available tools and techniques. The test was conducted for educational purposes and as a portfolio project to showcase wireless security skills. The detailed project walkthrough can be found <a href="https://github.com/VemTech6/Wi-Fi-Pentesting-Project/blob/main/Project%20Walkthrough.md">HERE</a>.
<br />


<h2>Methodology</h2>



The penetration test followed a structured process:

| **Phase**            | **Description**                                                                 |
|----------------------|---------------------------------------------------------------------------------|
| Reconnaissance       | Identified broadcasted SSIDs and their configurations using `airodump-ng`.     |
| Target Enumeration   | Collected BSSID, channel, encryption, and client information.                   |
| Attack Simulation    | Performed a deauthentication attack and attempted WPA2 handshake capture.      |
| Password Cracking    | Used `aircrack-ng` with a custom and pre-built wordlist (`rockyou.txt`).        |
| Post-Attack Review   | Analyzed if the attack vector was successful or not and noted possible defenses.|
</b>


<h2>Findings</h2>

<b>

| **Category**        | **Finding**                             | **Severity** | **Notes**                                                                 |
|---------------------|------------------------------------------|--------------|---------------------------------------------------------------------------|
| SSID Broadcast      | SSID is visible                          | Low          | While not inherently dangerous, broadcasting the SSID makes discovery easier. |
| Encryption          | WPA2-PSK identified                      | Medium       | Strong encryption but subject to dictionary or brute-force if password is weak. |
| Handshake Capture   | Successful                               | High         | Indicates the network is vulnerable to offline password cracking attempts. |
| Wordlist Attack     | Unsuccessful (Password Not in Wordlist)  | Low          | Demonstrates password strength against common wordlists.                  |
| Device Isolation    | Not enabled                              | Medium       | Clients could potentially communicate with one another.                   |
</b> 

<h2>Recommendations</h2>

<b> 

| **Recommendation**                                  | **Purpose / Benefit**                                                                      |
|-----------------------------------------------------|---------------------------------------------------------------------------------------------|
| **Use a strong, unique passphrase**                | Prevents successful dictionary and brute-force attacks.                                     |
| **Enable client isolation on router**              | Blocks devices from communicating with each other, reducing lateral movement opportunities. |
| **Disable SSID broadcast (optional)**              | Adds minor obscurity by hiding the network from casual scanning.                           |
| **Implement MAC address filtering**                | Limits device access to approved hardware, though can be bypassed by skilled attackers.     |
| **Monitor for deauthentication attempts**          | Helps detect active attacks like handshake capturing or forced disconnection attempts.      |
| **Update router firmware regularly**               | Ensures the latest security patches are applied to prevent known exploits.                  |
| **Restrict physical access to the network area**   | Reduces risk of local attacks from within Wi-Fi signal range.                              |

</b>

<h2>Conclusion</h2>

<b>The penetration test successfully captured the WPA2 handshake but was unable to crack the passphrase using standard and custom wordlists. This outcome suggests the Wi-Fi password has a sufficient level of complexity. However, the ability to capture a handshake and attempt cracking demonstrates that physical proximity still poses a viable attack surface. Further hardening is advised to improve overall security.</b>



<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
