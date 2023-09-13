<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Set up Client and Domain Controller Virtual Machines on Azure
- Install Active Directory
- Create administrative and user accounts in Active Directory
  


<h2>Deployment and Configuration Steps</h2>

<p>
<img width="1312" alt="image" src="https://github.com/dblock5/configure-ad/assets/102873312/56b80b99-08d8-4e22-9309-68565cf9cabc">

<img width="901" alt="image" src="https://github.com/dblock5/configure-ad/assets/102873312/3493675b-3caf-4516-99a5-91bc036e3ec3">

</p>
<p>
First, I created a domain controller virtual machine (Windows Server 2022) on Azure and created a client virtual machine (Windows 10) and made sure both VM's were on the same virtual network. I also set the the Domain controllers virtual NIC private IP address to static so it doesn't change and set the DNS for the client VM to use the same IP address that the domain VM has. I also logged in to client virtual machine to ping the domain controllers private IP (10.0.0.5) address with ping-t to check to ensure connectivity between the client and the Domain controller.  
</p>
<br />

<p>
<img width="1050" alt="image" src="https://github.com/dblock5/configure-ad/assets/102873312/6361c75a-1cab-422e-8865-623c55d44173">

<img width="996" alt="image" src="https://github.com/dblock5/configure-ad/assets/102873312/51c0d217-050c-49bc-b0d1-96bd7aa92fb7">

</p>
<p>
Next, I installed active directory on server manager set up domain on the domain controller VM. 
</p>
<br />

<p>
<img width="925" alt="image" src="https://github.com/dblock5/configure-ad/assets/102873312/270f9039-64ce-4fbd-bb08-d8e5f1f02fad">

<img width="851" alt="image" src="https://github.com/dblock5/configure-ad/assets/102873312/caa4a47d-f68e-41e8-8b77-67f94f6d7dc1">


<img width="925" alt="image" src="https://github.com/dblock5/configure-ad/assets/102873312/f5675df3-5d48-4341-906b-50a1ee54825a">


</p>
<p>
Created Organizational Units (_ADMINS and _EMPLOYEES) within active directory. Then I created an employee and an Admin account. I then used Powershell and ran a script that created new accounts on active directory. Then I logged in to the client virtual machine as one of the accounts I created.    
</p>
<br />
