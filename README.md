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

- Windows 10 Pro

<h2>Installation Steps</h2>

Step 1:


![image](https://i.imgur.com/wAPhqS1.jpg)


Create Virtual Machine in Azure
- Create a new resource group 
- Create a Windows 10 Pro virtual machine (VM) with 4 virtual CPUs as the size
- Remember and take note of the username and password created
- Under the network tab, allow it to create a new virtual network (vnet)
- Then hit review and create!

Step 2:


![image](https://i.imgur.com/czGO2h6.jpg)


Installation
- Connect to the VM via remote desktop connection application
- Login with saved username and password
- While in the VM, open microsoft edge and open this link that includes the installation files for osTicket: https://drive.google.com/drive/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6
- Now open control panel > programs > programs and features > turn windows features on or off > then check internet information services then expand to world wide web services then application development features then check "CGI" then under "common http features" under world wide web services make sure everything is checked
- To make sure it works, go to the edge browser to 127.0.0.1 in the url then it will load the windows Internet Information Services (IIS) page

Step 3:


![image](https://i.imgur.com/LhCoLYc.jpg)


osTicket Installation Files
- Go to installation files for osTicket: https://drive.google.com/drive/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6
- Download "PHPManagerforIIS" then install to VM
- Download "rewrite" then install to VM
- Then go to files under the C: folder create a new folder called PHP
- Download PHP.zip and unzip in the created folder called PHP
- Download VC_redist and install
- Download MySQL and install


Step 4:


![image](https://i.imgur.com/CAmCq5p.jpg)


MySQL and PHP Manager
- Launch SQL and choice standard config
- Write down username: root and password: Password1
- Hit execute then finish
- Launch IIS as admin then open PHP Manager
- Register new PHP version and find the C: in the PHP folder in the new window
- Click php-cgi
- Reminder to hit restart on the top right to refresh server


Step 5:


![image](https://i.imgur.com/Z5HEmCr.jpg)


osTicket Zip
- Download osTicket zip
- Open two file explores one of osTicket folder and one of C: inetpub then open wwwroot folder
- Drag the upload folder from the osTIcket zip in there
- Rename the upload folder to "osTicket"
- Restart IIS on the top right


![image](https://i.imgur.com/nlhq9sl.jpg)


Step 6: 
Extensions
- Expand the sites folder on the top left then expand until you see osTicket folder then hit browse link on the right
- Go back to IIS then PHP manager then click on enable or disable extensions
- Enable php_imap.dll
- Enable php_intl.dll
- Enable php_opcache.dll
- Go back to browser and refresh until some appear green


![image](https://i.imgur.com/J25UzmW.jpg)


Step 7:
Security
- In file explorer go into c: inetpub > wwwroot > osTicket then rename file from ost-sampleconfig to ost-config
- Right click on the ost-config file and properties
- Security then advanced
- Permissions then disable inheritance
- Add and select a principal then type "Everyone"
- Check the name and add then apply and close
- Basic permissions as full control

 <p align="center">
 <img src="https://i.imgur.com/Ds8JUvt.png" height="50%" width="50%" alt="properties selection"/>
 </p>
 <p align="center">
 <img src="https://i.imgur.com/rKhcHkW.png" height="50%" width="50%" alt="change permissions"/>
</p>
<br/>
<p align="center">
<img src="https://i.imgur.com/IxpkEaE.png" height="50%" width="50%" alt="disable inheritance"/>
 </p>
<p align="center">
<img src="https://i.imgur.com/xajjPGK.png" height="50%" width="50%" alt="remove all inherited"/>
 </p>
 
Then add new permissions for everyone and give Full Control.

<p align="center">
 <img src="https://i.imgur.com/Q9XQLXm.png" height="50%" width="50%" alt="add permssions for everyone"/>
 </p>
 
 After returning to the browser windows with osTicket installer and press '`Continue`', you will now see the below form to complete before continuing.  
 
 <p align="center">
 <img src="https://i.imgur.com/fjKAgGk.png" height="50%" width="50%" alt="osticket form"/>
</p>


Step 8:Download and install HeidiSQL from <a href="https://drive.google.com/drive/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">Google Drive</a> using the provided defaults that are available in the install wizard.
 <hr>
<p align="center">
 <img src="https://i.imgur.com/oImw5w0.png" height="50%" width="50%" alt="completion of heidisql install"/>

Next we will do the following in HeidiSql:
<ol>
 <li>Create a new session, username:root/password:Password1</li>
 <li>Connect to the session</li>
<li>Create a database called “osTicket”</li>
 </ol>
 <p align="center">
 <img src="https://i.imgur.com/D2QfMEb.png"  height="50%" width="50%" alt="create HeidiSql session"/> 
 </p>
 <p align="center">
 <img src="https://i.imgur.com/3bMHP2K.png" height="50%" width="50%" alt="create database HeidiSql"/> 
 </p>
 
 Created database for "osTicket":
 
 <p align="center">
 <img src="https://i.imgur.com/mLg4tOl.png" height="50%" width="50%" alt="create data base osTicket"/> 
</p>
<p> After the database is created, we can now enter those details into osTicket Installer 
<li>MySQL Username: root</li>
 <li>MySQL Password: Password1</li>
<li>Click <b><i>“Install Now!”</i></b></li>
</p>
<p> Congratulations, hopefully it is installed with no errors!
</p>
<p align="center">
 <img src="https://i.imgur.com/V3GSvvT.png" height="50%" width="50%" alt="congratulations of completion for osTicket"/>
</p>

Results below are from of choosing for "`Your Staff Control Panel`" or "`Your osTicket URL:`"
 
 <p align="center"><img src="https://i.imgur.com/LhTgI92.png" height="50%" width="50%" alt="available links to choose help desk or admin"/>
 </p>
 <p align="center">
 <img src="https://i.imgur.com/jNkPZNC.jpg" height="65%" width="65%" alt="Admin login for osTicket"/>
</p>

"`Your osTicket URL`" will direct us to the "`End User`" Portal where Users can submit tickets for assistance from the help desk.

 <p align="center">
  <img src="https://i.imgur.com/ErvbCg6.png" height="65%" width="65%" alt="End user login page to open/check ticket status"/>
  </p>
  <p> - <i>Clean up</i>
    <ol>
    <li> Delete: C:\inetpub\wwwroot\osTicket\setup</li>
    <li> Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php</li> 
    <li><i>Login to the osTicket Admin Panel</i> ([http://localhost/osTicket/scp/login.php](http://localhost/osTicket/scp/login.php))
  </p>
  <p align="center">
 <img src="https://i.imgur.com/XGHz3lx.png" height="65%" width="65%" alt="delete setup folder"/>
 </p>
 
Set Permission to "`Read`" only can be acheived by choosing to right-click on '`ost-config.php`' --> select `properties` --> select the '`Security`' tab near the top --> then click the '`Advanced`' button (not pictured below) --> once `advanced settings` is selected, you can now select the '`Everyone`' principle and now we can select to choose '`Read`' only as the preferred permission(s)

 <p align="center">
 <img src="https://i.imgur.com/AXCIeQN.png"  height="65%" width="65%" alt="read-only permissions"/>
 </p>
 <p align="center">
 <img src="https://i.imgur.com/R11rIMd.png"  height="65%" width="65%" alt="read-only allow is shown for osticketcong file"/>
 </p>
 <br/>
 
- Finally for admins access http://localhost/osTicket/scp/login.php and click sign in
- End Users osTicket URL: http://localhost/osTicket/
