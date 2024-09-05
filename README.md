<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- MacBook Pro
- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Have Azure tenant created 
- Have an active subscription with Azure
- Create a Resource Group for Vitual Machine (VM)
- Create a Windows 10 VM with 2-4 Virtual CPUs. When creating the VM, allow it to create a new Virtual Network (Vnet)
- Name: Vm-osticket, Username: labuser (for example/whatever you chose), Password: osTicketPassword1! (for example/whatever you chose)


<h2>Installation Steps</h2>


<p>
  
![image](https://github.com/user-attachments/assets/5c78c0a3-7d1f-4282-b783-161d0dd24a71) 
  
 </p>
<p>
First, go to your VM and copy the Public IP address. When using a Mac you'll have to use Microsoft Remote Desktop to log imto your virtual machine. Using command and space bar search for Microsoft Remote Desktop. Click add PC, then paste the Public IP address. Use the username and password you created to login. 
</p>
<br />

<p>
  
![EnableIIS](https://github.com/user-attachments/assets/671422bd-8c1e-46f8-936c-a377f679ec4d)

</p>
<p>
When logged in you can click no to all the privacy settings an click yes on Network to enable other computers from your network to find you. Then, open and download this: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6. We will use these files to open and install osTicket. Upload the files on your desktop. (for convenience) When finished click the start panel on the bottom left corner and type Control Panel. Under Programs click Uninstall a program. On the left click on Turn Windows features on or off. Check the box that says Internet Information Services. (IIS) Inside World Wide Web Services click -> Application Development Features -> and enable [X] CGI [X] Common HTTP Features. Go to internt explorer and type on the address bar 127.0.0.1 to check if installation was successful.
</p>
<br />

<p>
  
![InstallPHP](https://github.com/user-attachments/assets/4b788123-b35c-4079-8b6f-49ac2994276f)
  
</p>
<p>
After that go to your desktop to the Installation Files, download and install PHP Manager for IIS. (PHPManagerForIIS_V1.5.0.msi) Say yes to eveything to finish installing. 
</p>
<br />

<p>
  
![InstallRewriteModule](https://github.com/user-attachments/assets/dcf7cd30-0377-4871-9443-ed9c5236ff26)

</p>
<p>
From the Installation Files, download and install the Rewrite Module. (rewrite_amd64_en-US.msi)
</p>
<br />

<p>
<p>
  
![CtreatePHPfolder](https://github.com/user-attachments/assets/7a55c885-a82d-4f5f-aa51-860fd5e350e6)

</p>
<p>
Go to File Explorer to create the directory C:\PHP
</p>
<br />

</p>

![TypePHP](https://github.com/user-attachments/assets/2bea6ef4-2009-4c4d-943e-5282a07001e2)

<p>
From the Installation Files, download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP. If you are having trouble downloading PHP 7.3.8, please try downloading and installing Google Chrome and doing it from within there. 
</p>
<br />

<p>
  
![DownloadC++Redistributable](https://github.com/user-attachments/assets/5c285d57-6f0d-4cba-8be8-1a6df2603202)

</p>
<p>
From the Installation Files, download and install VC_redist.x86.exe.
</p>
<br />

<p>
  
![DownloadMySQL](https://github.com/user-attachments/assets/d1d7da57-053e-4ea6-ad2e-4bd4b2c6cdb5)

</p>
<p>
From the Installation Files, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
Typical Setup ->
Launch Configuration Wizard (after install) ->
Standard Configuration ->
Password1
</p>
<br />

<p>
  
![OpenIISasAministrator](https://github.com/user-attachments/assets/c7dcb5b6-cb47-4754-b01b-a3cbfcd02def)

</p>
<p>
Open IIS as an Admin
</p>
<br />

<p>
  
![EnablePHPcgi](https://github.com/user-attachments/assets/9ca7f27d-1def-4beb-8532-fd08201a7bc4)

</p>
<p>
Register PHP from within IIS. Click on PHP Manager -> Register new PHP version -> Windows(C): -> C:\PHP -> php-cgi then click Open and then OK. Then reload IIS (Open IIS, Stop and Start the server)
</p>
<br />

<p>
  
![DragDropUploadToWwwroot](https://github.com/user-attachments/assets/2761f70a-fd73-44ec-990b-b29424da5e90)

</p>
<p>
Install osTicket v1.15.8. Download osTicket from the Installation Files Folder. Extract and copy “upload” folder to c:\inetpub\wwwroot.

<br />

<p>
  
![RenameUploadTOosTicket](https://github.com/user-attachments/assets/692d7216-0d6f-4a23-a52f-f46d4f23b47f)

</p>
<p>
Within c:\inetpub\wwwroot, Rename “upload” to “osTicket” Reload IIS again (Open IIS, Stop and Start the server)
</p>
<br />

<p>
  
![IIStoSitesToDefaultWebToOsticket](https://github.com/user-attachments/assets/685c8bb5-b353-47e9-9b34-2b3c425a77ef)

</p>
<p>
Go to sites -> Default -> osTicket. On the right, click “Browse *:80” 
</p>
<br />

<p>
  
![EnablePHPimap,intl,opcache](https://github.com/user-attachments/assets/07b60b32-0c36-449d-aa30-27856e07ccfd)

</p>
<p>Note that some extensions are not enabled
Go back to IIS, sites -> Default -> osTicket
Double-click PHP Manager
Click “Enable or disable an extension”
Enable: php_imap.dll
Enable: php_intl.dll
Enable: php_opcache.dll
</p>
<br />

<p>
  
![RefreshOsTicketSite](https://github.com/user-attachments/assets/180080c5-5d0a-41b9-b792-84c087d79ebd)

</p>
<p>
Refresh the osTicket site in your browse, observe the changes

</p>
<br />

<p>
  
![RenameOst-sampleconfig](https://github.com/user-attachments/assets/e44ba0e8-9265-4e09-94d5-6a04ca7d2f6b)

</p>
<p>
From the File Explorer Rename: ost-config.php
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php <p>ost-sampleconfig.php new file name should be ost-config.php</p>
</p>
<br />

<p>
  
![DisableInheritedPermission](https://github.com/user-attachments/assets/25c9f489-dc60-4238-81b1-72fca2b80b0f)

</p>
<p>
Assign Permissions: ost-config.php
Disable inheritance -> Remove All
New Permissions -> Everyone -> All

</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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


