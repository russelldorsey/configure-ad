<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />

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
- Promote Server as DC/Setup New Forest
- Create New Organizational Unit
- Create Domain Admin User Within Domain
- Join Client-1 to your domain

<h2>Deployment and Configuration Steps</h2>

<p>
<img width="830" height="434" alt="Screenshot 2026-03-05 171721" src="https://github.com/user-attachments/assets/445519e9-39f9-4396-ab5b-824baae59362" />
</p>
<p>
To install Active Directory Domain Services (AD DS) on the Windows Server 2025 VM, first sign in to the server with a local administrator account and make sure the VM has a static private IP in Azure (so the domain controller’s address doesn’t change). Open Server Manager, click Manage, then select Add Roles and Features. Choose Role-based or feature-based installation, select your server, and on the Server Roles page, check Active Directory Domain Services. When prompted, click Add Features, then click Next to continue through the wizard, and click Install.
</p>
<br />
<p>
<img width="830" height="437" alt="Screenshot 2026-03-05 171200" src="https://github.com/user-attachments/assets/73734080-fab3-43d4-b6e0-df476dc5554f" />
</p>
<p>
When the role finishes installing, in Server Manager, click Promote this server to a domain controller to start the configuration wizard. In the promotion wizard, choose Add a new forest if this is your first domain controller, then enter a domain name (for example, company.local or mydomain.com). Leave DNS enabled (most labs install DNS on the domain controller), set a Directory Services Restore Mode (DSRM) password, and click Next to continue through the remaining pages (NetBIOS name, paths, prerequisites). Click Install to begin promotion. After the reboot, sign in using the domain (for example, DOMAIN\Administrator or mydomain.com\labuser) and verify AD DS is working by opening Tools in Server Manager and launching Active Directory Users and Computers.
</p>
<br />

<p>
<img width="479" height="358" alt="Screenshot 2026-03-05 182710" src="https://github.com/user-attachments/assets/1d473d9a-85fd-4316-9de5-92766ff13261" />
</p>
<p>
To create a new Organizational Unit (OU) on a Windows Server 2025 VM controller, sign in with a domain admin account and open Server Manager. Select Tools, then open Active Directory Users and Computers. In the left pane, expand your domain name, then right-click the domain (or right-click an existing OU if you want to create a sub-OU). Choose New > Organizational Unit, type a clear OU name (for example, IT, HR, Workstations, _EMPLOYEES, or _ADMINS), and leave Protect container from accidental deletion enabled unless you have a specific reason to turn it off. Click OK to create the OU. OUs are used to organize users and computers, making it easier to apply Group Policy and delegate administrative control to specific teams.

</p>
<br />

<p>
<img width="477" height="360" alt="Screenshot 2026-03-05 181826" src="https://github.com/user-attachments/assets/3df05c51-ce55-4894-b1c5-34fc8eef5442" />
</p>
<p>
To create a Domain Admin user in Windows Server 2025 VM, remain signed in to the server with an account that already has domain administrative rights (for example, mydomain.com\labuser). Open Server Manager, click Tools, and then select Active Directory Users and Computers if it is not already open. In the console, expand your domain and choose the Users container or the organizational unit (for example, _ADMINS) where you want to create the account. Then select Action, click New, and choose User. Enter the new user’s name (Jane Doe), logon name (for example, jane_admin), and password, then click Next and Finish to complete the wizard and create the account.

After the user account is created, to add the account to Domain Admins, locate the new account, right-click it, and select Properties. Open the Member Of tab, click Add, type Domain Admins, click Check Names, and then click OK. Apply the changes and close the window.

</p>
<br />

<p>
<img width="551" height="281" alt="Screenshot 2026-03-05 194334" src="https://github.com/user-attachments/assets/d0b2d6ea-a6b1-4fee-bca6-f830819884b1" />
</p>
<p>
To join Client-1 to your domain (hosted on a Windows Server 2025 Datacenter: Azure Edition domain controller), first make sure Client-1 can reach the domain controller on the network and is using the domain controller’s IP address for DNS (domain joins commonly fail if DNS isn’t configured to point to the DC). On Client-1, open Control Panel, go to System and Security, then System, and select Change settings (or open System Properties). On the Computer Name tab, click Change, select Domain, and type your domain name (for example, company.local or mydomain.com), then click OK. When prompted, enter the username and password of an account that has permission to join computers to the domain (such as a Domain Admin like mydomain.com\jane_admin), then click OK and accept the confirmation message that you’ve joined the domain. Finally, restart Client-1 to complete the process. After the reboot, you can sign in using a domain account, such as DOMAIN\username or mydomain.com\jane_admin.
</p>
<br />
