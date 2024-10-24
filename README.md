<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- <b>PHP manager for IIS</b> - ensures PHP is correctly configured to run IIS
- <b>Rewrite module </b> - facilitates URL rewriting and redirect users to URLs
- <b>VC_redist.x86</b> (redistributable) - osTicket relies on libraries that are part of Microsoft Visual C++ and ensures the program runs smoothly
- <b>MySQL</b> - for storing data into databases
- <b>HeidiSQL</b> - interface for accessing MySQL 

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/fRx4VaXl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After creating your Windows VM in Azure, remote desktop into your virtual machine using the Public IP address given to your VM after creation, and the credentials you assigned during setup. (ProTip: Open Notepad to keep track of the different login credentials you create.) Once inside your VM, from Microsoft Edge web browser download <a href= https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD>osTicket-Installation-Files.zip</a>. After installation extract the file to your desktop.
</p>
<br />

<p>
<img src="https://i.imgur.com/71ti5Dg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From Windows START menu enable IIS with CGI by opening Control Panel> Programs> Turn features On/Off>IIS> WWWS> Application Development Feature> CGI. Once IIS is installed, from within the osTicket Installation folder install PHP Manager.    
</p>
<br />

<p>
<img src="https://i.imgur.com/C9B6Bfp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once PHP manager has been successfully installed, open up Windows (C:) and create a folder named PHP. From within the osTicket folder extract file php-7.3.8-nts-Win32-VC15-x86 into the new PHP folder you just created. From within the osTicket folder install VC_redist.x86 and mysql-5.5.62. Be sure to follow prompts and record created username and password on notepad. 
</p>
<br />
