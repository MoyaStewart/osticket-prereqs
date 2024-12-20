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
<img src="https://i.imgur.com/vEn63zp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After creating your Windows VM in Azure, remote desktop into your virtual machine using the Public IP address given to your VM after creation, and the credentials you assigned during setup. (ProTip: Open Notepad to keep track of the different login credentials you create.) Once inside your VM, from Microsoft Edge web browser download <a href= https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD>osTicket-Installation-Files.zip</a>. After installation extract the file to your desktop.
</p>
<br />

<p>
<img src="https://i.imgur.com/QgMz62E.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From Windows START menu enable IIS with CGI by opening Control Panel> Programs> Turn features On/Off>IIS> WWWS> Application Development Feature> CGI. Once IIS is installed, from within the osTicket Installation folder install PHP Manager.    
</p>
<br />

<p>
<img src="https://i.imgur.com/dfgA9FS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once PHP manager has been successfully installed, open up Windows (C:) and create a folder named PHP. From within the osTicket folder extract file php-7.3.8-nts-Win32-VC15-x86 into the new PHP folder you just created. From within the osTicket folder install VC_redist.x86 and mysql-5.5.62. Be sure to follow prompts and record created username and password on notepad.After installation is complete open IIS as admin and register PHP. Open PHP Manger > Register New PHP Version > C:\PHP\php-cgi.exe. Reload/Refresh IIS form within IIS.  
</p>
<br />

<p>
<img src="https://i.imgur.com/FzFycIK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next install the redistributable and accept all defaults. Then install MySQL, select Standard Configuration and then enter root and root as the username and password. This is just for simplicity and you'd likely use a stronger password in real life.
</p>
<br />

<p>
<img src="https://i.imgur.com/k509qyf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From within the osTicket Installation folder extract osTicket-v1.15.8 and copy it into C:\inetpub\wwwroot. From within the "wwwroot" folder rename "upload" folder to "osTicket". Be sure to avoid spelling or spacing mistakes when renaming. Restart IIS server.
</p>
<br />

<p>
<img src="https://i.imgur.com/3JkZRf0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After IIS servers have been restarted, reopen IIS manager under admin if you closed it out previously. From the homepage click Sites->Default Website->osTicket. To the right of the screen you'll load the site by clicking Browse *:80(http). Once loaded notice that some extensions are not enabled. Back in PHP Manager within the IIS Admin enable the following extensions; php_imap.dll, php_intl.dll, and php_opache.dll. Once enabled refresh your browser and you should see all but the last two extensions enabled.
</p>
<br />

<p>
<img src="https://i.imgur.com/4KeG5Jz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now, from (C:) we have to rename C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php to C:\inetpub\wwwroot\osTicket\include\ost-config.php.(Make sure its entered correctly!) Next, we'll need to assign permissions for this file. Right click ost-config.php -> Properties -> Security tab -> Advanced -> Disable inheritance (remove all option) -> Add -> Select a principal -> Type everyone in the box -> Check names -> OK. Make sure you click on Full control as well.
</p>
<br />

<p>
<img src="https://i.imgur.com/Rj7Eb7y.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Finally, from the osTicket Install Folder follow prompts to install HeidiSQL. Fom within HeidiSQL session manager select New -> Username -> Password ( root/root - created during mySQL section) -> Open. From here you'll right click Unnamed -> Create New -> Database -> name it osTicket (exactly).
</p>
<br />

<p>
<img src="https://i.imgur.com/Vhykyh6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once you have completed the steps above you can finish the install in your browser using the username and passwords previously setup. Congratulations! You did it! osTicket should be installed and ready to use.
</p>
<br />
