<h1>Active Directory VirtualBox Setup - Oravle VirtualBox</h1>

<h2>Description</h2>
This project sets up a basic Active Directory environment for learning, testing, and future cybersecurity lab work. Using Oracle VirtualBox, I deployed a Windows Server 2019 VM configured as a Domain Controller and a Windows 10 VM as a domain-joined client. 

<br />


<h2>Languages and Utilities Used</h2>

- <b>Powershell</b> 
- <b>Virtual Box</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> 
- <b>Windows Server 2019</b> 

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
<img src="https://i.imgur.com/MTN4Sxh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for the scan to complete and check findings (Basic scan looks ok):  <br/>
<img src="https://i.imgur.com/FU4cniO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
In the Server Manager, click "Add roles and features" and go through it and Install:  <br/>
<img src="https://i.imgur.com/TT8W1dA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
After setting up the server "Promote this server to a domain controller" and restart the Server VM:  <br/>
<img src="https://i.imgur.com/duuJpVp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Open "Active Directory Users and Computers" and in mydomain.com create a new Organizational unit and call it "ADMINS":  <br/>
<img src="https://i.imgur.com/lytEhoe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
In the ADMINS folder you just made create a new user and fill it out accordingly:  <br/>
<img src="https://i.imgur.com/MxmdSHh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Now, with the new user you just created, go to "properties" and make them a member of "Domains Admins":  <br/>
<img src="https://i.imgur.com/rmQfpT2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sign out and sign in as the User you just created  <br/>
Click "Add roles and features" and select "Remote Access" for the role and enable "Routing" and Install:  <br/>
<img src="https://i.imgur.com/Qa49Bso.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
In the Server Manager, click on "Tools" and select "Routing and Remote Access" for the role and enable "Routing" and install  <br/>
Select the NAT and for the public interface select the adaptor that is connected to the internet:  <br/>
<img src="https://i.imgur.com/fnxyBc1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Now to set the DHCP server to the domain controller....  <br/>
<br />
<br />
"Add roles and features" and for server roles select "DHCP server" and install:  <br/>
<img src="https://i.imgur.com/5y19Rhi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
In the Server Manager, click on "Tools" and select "DHCP" for the role and enable "Routing", and install  <br/>
Right-click "IPv4" and "Configure the IP address accordingly, please make sure to add the DC IP to the router:  <br/>
<img src="https://i.imgur.com/bdpmykQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
In the Server Manager "configure this server" turn off Enhanced security Configuration (Optional if you're doing this in a home lab):  <br/>
<img src="https://i.imgur.com/1mLO1o6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
I used a txt file with thousands of names for Users and I used this PowerShell script that automatically made 1000+ user accounts:  <br/>
<img src="https://i.imgur.com/dg8VbHs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Double-check that the script ran successfully and then you are all done setting up the server!<br />
Now moving on to set up the Client Windows...<br />
Here is the setup for the new VM with the Windows using ISO file: <br />
<img src="https://i.imgur.com/QX6wzuS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Here is the setup for the new VM with the Windows using ISO file: <br />
<img src="https://i.imgur.com/QX6wzuS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
