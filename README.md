<h1>Active Directory VirtualBox Setup - Oravle VirtualBox</h1>

<h2>Description</h2>
This project sets up a basic Active Directory environment for learning, testing, and future cybersecurity lab work. Using Oracle VirtualBox, I deployed a Windows Server 2019 VM configured as a Domain Controller and a Windows 10 VM as a domain-joined client. 

<br />


<h2>Languages and Utilities Used</h2>

- <b>Powershell</b> 
- <b>Virtual Box</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)
- <b>Windows Server 2019</b> (21H2)

<h2>Program walk-through:</h2>

<p align="center">
Set up a Virtual Machine on VirtualBox. Set up second network adaptor for "Internal Network": <br/>
<img src="https://i.imgur.com/NK6IrvI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
For better function, go to "Devices" --> "insert Guest Additions CD image" and then in the File Explorer "This PC" --> "VirtualBox Guest Additions" then power the VM and power it back on (optional):  <br/>
<img src="https://i.imgur.com/VabyP4w.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Start a new Scan on Nessus Essentials & set your target IP: <br/>
<img src="https://i.imgur.com/Wqb6cVd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for the scan to complete and check findings (Basic scan looks ok):  <br/>
<img src="https://i.imgur.com/1iw7IIT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Inspect the Scan:  <br/>
<img src="https://i.imgur.com/tuYUDIy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Change Remote Registry properties to "Automatic":  <br/>
<img src="https://i.imgur.com/UwoDocX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Turn on File and Print sharing:  <br/>
<img src="https://i.imgur.com/2h3Ngbs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Turn off notifications when changes made to the computer (optional):  <br/>
<img src="https://i.imgur.com/hpKXoc3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Add a new registry and call it "LocalAccountTokenFilterPolicy" and change value data to "1":  <br/>
<img src="https://i.imgur.com/H5VfelN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Going to Nessus Essentials on my Host I did another scan and added my VM credentials to do a more thorough scan:  <br/>
Inspect the results (We now see more vulnerabilities than the basic scan):  <br/>
<img src="https://i.imgur.com/CPmBX0a.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
I installed an old version of Mozilla FireFox (2005):  <br/>
<img src="https://i.imgur.com/gRsjIHc.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
<br />
<br />
Going back to Nessus Essentials I did another scan with even more critical vulnerabilities:  <br/>
<img src="https://i.imgur.com/aQe0qJR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Inspect the results (We now see more vulnerabilities than the basic scan):  <br/>
<img src="https://i.imgur.com/2vff7dy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Uninstalled Mozilla FireFox and remediated as many vulnerabilities as we could:  <br/>
<img src="https://i.imgur.com/fOnupzf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Finally did one last scan on Nessus (look at how many vulnerabilities we remediated!):  <br/>
<img src="https://i.imgur.com/ggdT0LV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
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
