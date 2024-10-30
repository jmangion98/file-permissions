<p align="center">
<img src="https://i.imgur.com/xlYwPUf.png" alt="Permissions Photo"/>
</p>

<h1>Understanding File Permissions</h1>
This lab focuses on file permissions and shares within an Active Directory domain, which are crucial for ensuring users have appropriate access to necessary files. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 Pro (21H2)

<h2>File Permissions Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/bUjobDC.png" height="80%" width="80%" alt="Permissions Steps"/>
<img src="https://i.imgur.com/lz1DMos.png" height="80%" width="80%" alt="Permissions Steps"/>
</p>
<p>
File Permissions Configuration Steps

  1. Create Shared Folders: While logged in to the domain controller VM as an admin, create four folders on the C:\ drive. To share a folder, open its Properties, click on the Sharing tab, and specify network users along with their permissions:

Domain Users:
- Read access to the read-access folder
- Read/Write access to the write-access folder
- Domain Admins: Read/Write access to the no-access folder.
</p>
<br />

<p>
<img src="https://i.imgur.com/kWrpLFE.png" height="80%" width="80%" alt="Permissions Steps"/>
</p>
<p>
2. Navigate to Shared Folders: On the client VM, access the shared folders via \dc-1. Note that some folders allow only viewing, while one is completely inaccessible. This is due to permissions tied to the Security Groups associated with the Domain User.
</p>
<br />

<p>
<img src="https://i.imgur.com/NgM0CcI.png" height="80%" width="80%" alt="Permissions Steps"/>
<img src="https://i.imgur.com/I4k9T2J.png" height="80%" width="80%" alt="Permissions Steps"/>
</p>
<p>
3. Create a Security Group: In the Active Directory Users and Computers panel on the domain controller, create a new group called ACCOUNTANTS. Then, assign Read/Write permissions for the accounting folder to this group.
</p>
<br />

<p>
<img src="https://i.imgur.com/xev1Svv.png" height="80%" width="80%" alt="Permissions Steps"/>
<img src="https://i.imgur.com/SHotVB2.png" height="80%" width="80%" alt="Permissions Steps"/>
</p>
<p>
4. Assign Users to the Group: A user not in the ACCOUNTANTS group cannot access the accounting folder. Log off the client VM, and in the ACCOUNTANTS Properties, add the user bon.rovej. Upon logging back in, bon.rovej can now access the accounting folder.

<br />

<h2>Lessons Learned </h2>

This lab enhanced my understanding of file permissions in Windows/Active Directory. It emphasized the importance of restricting access so users can only reach what they need for their work, avoiding unnecessary permissions.
