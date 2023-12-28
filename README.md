
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
<img src="https://github.com/eavi12/AD_lab/assets/58631054/733ed140-8e53-42ba-be16-224516d81504" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br />
<br />
Now were are going to install the DHCP server.  <br/>
<img src="https://github.com/eavi12/AD_lab/assets/58631054/713991e4-c276-4a06-a255-050be6c3c683" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/eavi12/AD_lab/assets/58631054/612ec6a4-2972-4e8d-bb9c-2bba468e0d76" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br/>

Next we created multiple users with generic password for lab purposes with a Powershell Script.
<img src="https://github.com/eavi12/AD_lab/assets/58631054/075c0f03-fd29-4b3c-b627-378d9d58449a" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/eavi12/AD_lab/assets/58631054/4fd564a8-a24b-4193-b5e0-5fce46550265" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br/>

Next on the client VM we are going to make it a member of mydomain.com 
<img src="https://github.com/eavi12/AD_lab/assets/58631054/053d2045-2bf4-4bd6-b5a4-8feeb0c53b3e" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br/>
<img src="https://github.com/eavi12/AD_lab/assets/58631054/1fb81608-30ce-4f00-a5dc-3a7f9fcd0767" height="80%" width="80%" alt="Disk Sanitization Steps"/>
Now from our Windows 10 VW we can login with one of the created users and login via our Domain Controller we are going to login with the username aabrev
<img src="https://github.com/eavi12/AD_lab/assets/58631054/0030d5a5-b872-437b-a7e5-bf4ffaa55c21" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/eavi12/AD_lab/assets/58631054/ed3bf177-59c2-4868-ad48-95e591b3c910" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/eavi12/AD_lab/assets/58631054/c4600b16-3c2c-4129-89f8-be2efa02770a" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://github.com/eavi12/AD_lab/assets/58631054/b413b75f-d9f7-4a47-9e2b-34e0ec28386b" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br/>

<h2>Conclusion:</h2> <br/>
In conclusion we installed and configured a Windows Server 2019 as our Domain Controller and AD DS with a FQDN of mydomain.com. We set up the Domain Controller to have two NIC's one for public internet access and one for internal network access. Next we configured the RAS/NAT to allow remote access and network address translation on the server. Next we configured the DC server for DHCP with IP range of 172.16.0.100-200 with a NetMask of /24 and loopback DNS for the DC as it is acting as its own DNS server as well. We ran a powershell script to generate random users for the DC. Lastly we install and configured Windows 10 VM as the client for the DC. Now we are able to login to the Windows 10 VM as one of the newly created users and be a part of mydomain.com
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
