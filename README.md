<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> 

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- osTicket Installation files
- Heidi SQL

<h2>Installation Steps</h2>

<p>
In this tutorial, I will walk you through the steps to create a virtual machine, install a ticketing system, and set up SQL.
<br>
<br>
To get started, we need to create a virtual machine in the Microsoft Azure portal (portal.azure.com). A virtual machine (VM) acts as a remote computer, allowing us to protect our physical machine in case something goes wrong and providing a clean, reusable environment for our lab setup. Begin by creating a resource group and naming it "osTicket".</p>
<br />
<img width="1255" alt="image" src="https://github.com/user-attachments/assets/bb5a6ad0-fb93-49db-bbdd-33e1dd2d561e">

<p>
</p>
<br />
<p>
</p>
<p>
Next, connect to your new VM using Remote Desktop Protocol (RDP) with the public IPv4 address. If you're using a Mac, you'll need to download the Microsoft Remote Desktop app first.
</p>
<img src="https://i.imgur.com/uLVKzxS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
Once connected to your VM, you'll need to enable IIS. Go to the Control Panel, select "Uninstall a program," and then click "Turn Windows features on or off" on the left. From the list that appears, enable Internet Information Services (IIS).

</p>  
<img src="https://i.imgur.com/qtEnuWu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
</p>
<p>

Great! Now that IIS is enabled, the next step is to install the Web Platform Installer. Use the link provided here: 
<a href="https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">Web Platform Installer Resources</a> this link will provide the Web Platform Installer Resources to access all necessary materials for setting up osTicket. Simply click the link and download the Web Platform Installer to proceed.
  
</p>
<img src="https://i.imgur.com/AxHCfQ6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>  
</p>
<p>
After installing the Web Platform Installer, open the application. Within it, install MySQL 5.5, followed by the x86 versions of PHP up to version 7.3.
</p>
<img src="https://i.imgur.com/JJ8bZeJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
</p>
<p>
Next, download osTicket and extract the files. Copy the "upload" folder to C:\inetpub\wwwroot, then rename the folder to "osTicket."</P>
<img width="364" alt="image" src="https://github.com/user-attachments/assets/7a5dc3aa-367d-4577-9753-5c2b905c4cad">

</p>
<br />
<p>
</p>
<p>
Open IIS Manager and restart the server. In IIS Manager, navigate to Sites > Default > osTicket. On the right, click Browse *.80 to open the osTicket web server in your default browser.

</p>
<img src="https://i.imgur.com/4AkTkV0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p>
</p>
<p>
Return to IIS Manager and enable the necessary extensions. Go to Sites > Default > osTicket, then double-click on PHP Manager. Select Disable or enable an extension, enable php_intl.dll and php_opcache.dll, and refresh the osTicket web server. The "Intl Extension" should now be enabled.

</p>
<img src="https://i.imgur.com/APZgUTT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p>
</p>
<p>
Navigate to c:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php and rename the file to ost-config.php. Next, assign appropriate permissions to the newly renamed file. Disable inheritance, remove all inherited permissions, and then set the new permissions to grant full access to "Everyone."
</p>
<img src="https://i.imgur.com/1nYaYGe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p>
</p>
<p>
Next, proceed with the osTicket setup in your browser by clicking "Continue." You will then be prompted to name your helpdesk according to your preference. Additionally, select a default email address that will receive notifications from customers who submit tickets.

</p>
<img src="https://i.imgur.com/RmVk3q5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p>
<p>
  Continue the osTicket setup in the browser by entering the following details:

MySQL Database: osTicket
MySQL Username: root
MySQL Password: Password1
Click "Install Now!" to complete the installation. Congratulations, if there are no errors, the installation should be successful.
</P>
