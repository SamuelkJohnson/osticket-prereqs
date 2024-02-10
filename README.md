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


![image](https://imgur.com/LOvUpBR.jpg)


Step 8:
osTicket Browser setup
- Go back to the browser and contine through the osTicket setup
- After saving username and password to a note pad
- Download the mysql database exe "HediSQL"
- Run HediSQL and go through the installation
- Launch then click new on the bottom left
- Username as root and password as Password1
- Right click on unnamed at the top and create database
- Name it "osTicket"
- Go back to browser click install now after filling everything in, MySQL Database: osTicket
- Go to c: inetpub wwwroot osTicket then right click on the setup folder and delete it
- Go into the include folder and edit the ost-config php and properties then under security go to advanced and change to read and execute only
- Finally for admins access http://localhost/osTicket/scp/login.php and click sign in
- End Users osTicket URL: http://localhost/osTicket/
