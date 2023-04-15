# network-file-share<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Network File Shares and Permissions</h1>
This tutorial extends the on-premises Active Directory tutorial and demonstrates network file sharing and setting permissions on the domain controller.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- Command Line

<h2>Operating Systems Used </h2>

- Windows Server 2022

<h2>Network File Sharing and Permissions</h2>

- Creating Folders in Domain Controller
- Assigning Permissions to Folders
- Access files in Client Computer
- Create Security Group in Active Directory

<h2>Creating Folders in Domain Controller</h2>
<p>
<img src="https://imgur.com/JroTrs4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After logging into the Domain Controller and Client computer, we can go to "File Explorer" and create 4 folders in the C: drive (Read-Access, Write-Access, No-Access, Accounting). Right-click in the C: drive - click New, Folder, and add name.
</p>
<br />
<h2>Assigning Permissions to Folders</h2>
<p>
<img src="https://imgur.com/LjoS2vH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Under Read-Access and Write-Access, we can assign permissions to the "Domain Users". For Read-Access, "Domain users" can only read; for Write-Access, "Domain users" can read and write, and for No-Access, the "Domain Admins" can read and write. To access permission, right-click on the folder --> click on "Properties" --> click on "Share" --> type "Domain Users" in textbox --> Click "Add" -->Select either "Read", "Read or Write" to the Domain Users --> Click "Share", "Apply" and "Ok" to add permissions (Can be followed for both Read-Access and Write Access, respectively). For "No-Access" ensure to add "Domain Admins". For now, do not assign permissions to the accounting folder.
</p>
<br />
<h2>Access files in Client Computer</h2>
<p>
<img src="https://imgur.com/xPYVKJO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next login to Client-1 as a normal user from the list of employees to see which files can be accessed or add files.
</p>
<br />
<h2>Create Security Group in Active Directory</h2>
<p>
<img src="https://imgur.com/FDCLZj4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Inside of Server Manager on the domain controller, we can add a new security group named "Accountants". To add a new security group, we can right-click under domain name --> Select "Group" and name the group. Next, we can toggle to the "accounting folder" to assign permissions and access only to the "Accountants" group. Right-click the "Accounting" folder --> click on "Properties" --> click on "Share" --> type "Accountants" in textbox --> Click "Add" -->Select either "Read or Write" to the Accountants --> Click "Share", "Apply" and "Ok" to add permissions. Next, add a user to the "accountant group" --> Select "Members", --> click "Add" and type in "Created User Name" from previous lab. Next, sign as the designated user and you should receive access as the user inside of the accounting folder.
</p>
<br />
