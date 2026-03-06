<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2025 Datacenter Azure Edition
- Windows (24H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Install Active Directory Domain Services
- Step 2
- Step 3
- Step 4

<h2>Deployment and Configuration Steps</h2>

<p>
<img width="830" height="434" alt="Screenshot 2026-03-05 171721" src="https://github.com/user-attachments/assets/445519e9-39f9-4396-ab5b-824baae59362" />
</p>
<p>
To install Active Directory Domain Services (AD DS) on the Windows Server 2025  VM, first sign in to the server with a local administrator account and make sure the VM has a static private IP in Azure (so the domain controller’s address doesn’t change). Open Server Manager, click Manage, then select Add Roles and Features. Choose Role-based or feature-based installation, select your server, and on the Server Roles page, check Active Directory Domain Services. When prompted, click Add Features, then click Next to continue through the wizard, and click Install.
</p>
<br />
<p>
<img width="830" height="437" alt="Screenshot 2026-03-05 171200" src="https://github.com/user-attachments/assets/73734080-fab3-43d4-b6e0-df476dc5554f" />
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
