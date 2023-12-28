
<h1>Active Directory Lab</h1>


<h2>Description</h2> Setting up a home lab running Active Directory and add multiple users with Powershell script. <br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Oracle VirtualBox</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)

- <b>Server 2019</b> 

<h2>Program walk-through:</h2>

<p align="center">
Lab Overview: <br/>
<img src="https://github.com/eavi12/AD_lab/assets/58631054/736aff57-3ce3-47f3-b42a-0b9ff985f429" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
First, we need to download and install VirtualBox and an ISO image for Windows 10 and Windows Server 2019  <br/>
<img src="https://github.com/eavi12/AD_lab/assets/58631054/1dfb56d3-b174-42f1-a906-368be104018b" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
After downloading and installing VirtualBox, both virtual machines a Windows 10 and a Windows Server 2019 as our Domain Controller are booted and running. Then the IPV4 is configured and an IP address is assigned to our domain controller, a default gateway was not assigned in this example because the domain controller will serve as our default gateway. For our DNS we use the Domain Controller itself in our case we used the loopback address 127.0.0.1
<img src="https://github.com/eavi12/AD_lab/assets/58631054/e90ebc04-94a8-48f9-a4e0-e879a288889f" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Next we are going to install Active Directory Domain Services (AD DS) with the FQDN: mydomain.com <br/>
<img src="https://github.com/eavi12/AD_lab/assets/58631054/71be5cb4-47c1-43bf-bb70-fca39ff93000" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/eavi12/AD_lab/assets/58631054/5e0ac15c-2152-4b3e-a7ff-d0b901024398" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/eavi12/AD_lab/assets/58631054/9f6420e4-bc44-4310-a905-a2794e913fbe" height="80%" width="80%" alt="Disk Sanitization Steps"/>

 <br />
<br />
Now we are going to build our own dedicated domain account instead of using the built in administrator account.  <br/>
<img src="https://github.com/eavi12/AD_lab/assets/58631054/6689346e-a5e7-467d-a688-1fcfc9fb16de" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br/>
Next we created an admin user for the domain
<img src="https://github.com/eavi12/AD_lab/assets/58631054/e65fe661-7aec-4c6b-b020-acfceac12006" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br/>
The test user is then added to Domain Admins group
<img src="https://github.com/eavi12/AD_lab/assets/58631054/89d9a8b5-fdd9-4992-b470-dcd6b273f412" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Next we are going to install RAS/NAT which will allow the  Windows 10 client to be on a private virtual network but still access the Internet through the domain controller.   <br/>
<img src="https://github.com/eavi12/AD_lab/assets/58631054/5e94463a-81e4-4c6e-bbbb-ae3cbb9994f5" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/eavi12/AD_lab/assets/58631054/d3beaf38-6f41-4bda-a6dc-61bb3feaf6bd" height="80%" width="80%" alt="Disk Sanitization Steps"/>

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
