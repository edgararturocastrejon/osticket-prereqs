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
First go to your VM and copy the Public IP address. When using a Mac you'll have to use Microsoft Remote Desktop to log imto your virtual machine. Using command and space bar search for Microsoft Remote Desktop. Click add PC, then paste the Public IP address. Use the username and password you created to login. 

</p>
<br />

<p>
  
![EnableIIS](https://github.com/user-attachments/assets/671422bd-8c1e-46f8-936c-a377f679ec4d)

</p>
<p>
When logged in you can click no to all the privacy settings an click yes on Network to enable other computers from your network to find you. Then, open and download this: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6. We will use these files to open and install osTicket. Upload the files on your desktop. (for convenience) When finished click the start panel on the bottom left corner and type Control Panel. Under Programs click Uninstall a program. On the left click on Turn Windows features on or off. Check the box that says Internet Information Services. (IIS) Inside World Wide Web Services click -> Application Development Features -> and enable [X] CGI [X] Common HTTP Features. 

  
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
