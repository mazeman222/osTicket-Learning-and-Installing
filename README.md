<p align="center">
<img src="images/Screenshot%202024-12-25%20042807.png">
</p>

<h1>osTicket - Prerequisites and Installation</h1>
Here I will outline the prerequisites and installation of the open-source help desk ticketing system osTicket.
This is the link for the documentation. https://docs.osticket.com/en/latest/Getting%20Started/Installation.html<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop Connection
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Desktop/Laptop
- Azure/AWS/Google Account (When you signup with Microsoft Azure free tier, you get a $200 credit.)
- Internet Information Services (IIS) Manager
- Remote Desktop Connection

******** MOST WINDOWS OSs ALREADY COME WITH REMOTE DESKTOP AND INTERNET INFORMATION SERVICES (DISABLED) ******************

<hr>
<h2>It does not matter wether you use Azure/AWS/Google or Virtualbox/VMware. It is better to use install this on a virtual machine than your main system. Then when you are confident, then you can install it on your main system if you like. This was deployed on a virtual machine created within Microsoft Azure</h2>
<hr>

<h2>Installation Steps</h2>

- When you signup with Microsoft Azure free tier, you get a $200 credit.
- Login to Azure and create a Windows virtual machine (Windows 10/11)
- After Azure finishes creating the VM, type in the search bar "virtual machine" to go to the VM page.
- Locate the "Public IP address" for the virtual machine and then use that to log into "Remote Desktop Connection" (You will be prompted to enter the user name and password for the virtual machine.)
- After loging into the windows virtual machine type in the search bar "Remote Desktop Connection". When the app appears you want to pin it to the taskbar for ease of access. Search for "Internet Information Sevices Manager" and pin that to the taskbar as well.

These will need to be downloaded and installed on your virtual machine.
<img src="images/Screenshot%202024-12-25%20113611.png" alt=""/>

- After installing the packages you want to make sure that "IIS" is running with "CGI" enabled. Type "control panel" in the search bar and then click on "programs". Then click on "turn windows features on or off".
<img src="images/Screenshot%202024-12-25%20115041.png" alt=""/>

This brings up the "windows features" windows. Here you can add and remove the features that you do not want. This is where you are going to add the "IIS" feature if it is not enabled on your system. Enable the box next to "Internet Information Services" and ensure that all of your settings match the images below.

<img src="images/Screenshot%202024-12-25%20115449.png" alt=""/>
<img src="images/Screenshot%202024-12-25%20115530.png" alt=""/>

Restart your virtual machine to make sure that the settings have been changed. When you log back into the virtual machine, open up the "edge browser" and type "127.0.0.1" into the search bar. This is how you know that IIS is running correctly.
<img src="images/Screenshot%202024-12-25%20120916.png" alt=""/>

- Go to the "C:" drive of your virtual machine and create a folder called "PHP" then extract the binaries from the "PHP 8.2/8.1" into the "PHP" folder on the "C:" drive.
<img src="images/Screenshot%202024-12-25%20122116.png" alt=""/>

- Now click on the windows logo and type in the search bar "IIS" and open it as "administrator". This is what you will see once the app has opened.
<img src="images/Screenshot%202024-12-25%20144521.png" alt="">

- Now this is where we will register PHP in IIS. Go to PHP Manager and click on the icon. Once in the icon in the "PHP Manager page click on "register new PHP version. When the window pops up, navigate to the PHP folder located in the "C:" drive. When in the folder you will see "php-cgi" application at the bottom and double click on that. The path will show up in the "register PHP version" window and click "ok". After this you will have to stop and restart the server with the controls in the upper right corner.
<img src="images/Screenshot%202024-12-25%20145750A.png" alt="">

- If you haven't downloaded the latest version of osTicket, you can do it now. When you have the file downloaded there will be two folders named:<br>
  <b>scripts</b><br>
  <b>upload</b> <br>
  You are going to copy the "upload" folder into the "C:\inetpub\wwwroot" folder. Then in the "c:\inetpub\wwwwroot" folder you are going to change the name of the "<b>upload</b>" folder to "<b>osTicket</b>".<br>
  ******* THERE SHOULD BE NO SPACES IN OSTICKET AND SHOULD BE SPELLED: osTicket******** <br>
  Restart the server again.

- If you are not logged in to "IIS" log back in and then:<br>
  (1) Click on your computer network in the left panel.<br>
  (2) Click on the "sites folder and it will expand downward and you will see "Default websites".<br>
  (3) On the bottom you will see the "osTicket" folder and then you can click on it.<br>
  (4) On the right side click "Browse:*80:(http)".<br>
  <img src="images/Screenshot%202024-12-25%20152635.png" alt="">

- If everything was done correctly, you will see this screen:<br>
<img src="images/Screenshot%202024-12-25%20042937.png" alt=""/>

-<h2>****** BY DEFAULT THESE 3 EXTENSIONS WILL BE DISABLED. YOU HAVE TO ENABLE THEM*****</h2><br>
You will have to go back into "IIS" > "sites" > "Default" > osTicket
Go back into PHP Manager and click "Enable or disable an extension":<br>
  Enable: php_imap.dll<br>
  Enable: php_intl.dll<br>
  Enable: php_opcache.dll<br>

- Now go into to "C:\inetpub\wwwroot\osTicket\include" and look for a file named "ost-sampleconfig.php". We are going to change this file name to "ost-config" and leave the .php on the end of the file. If you are prompted with a window about permissions, go ahead and grant the permission to change the name of the file. Now we have to make more changes to the files so that osTicket can have permission to make changes on the backend.<br>
(1) Right click on the "os-config.php" and go to "properties".<br>
(2) Go to "security" and click on the "advanced" button.<br>
(3) Click on the "disable all inheritance" button on the bottom left of the window and click on "remove all inherited permissions from this object."<br>
(4) Click on "add" to add new permissions. On the next screen click "select a new principle" at the top of the window.<br>
(5) (FOR THE SAKE OF THIS TUTORIAL WE WILL ADD "EVERYONE", BUT DO NOT DO THIS IN A PRODUCTION ENVIRONMENT) Type "everyone" in the "user/group box" and hit the "check names" button. This will give "everyone" full access and you can click ok.<br>
(6) Give "everyone" "full control" in the "basic permissions window" and press "ok". Then hit apply and then ok, again.

- Now everything is ready to go and you can hit the "continue" button at the bottom of the screen. On the next screen you will need to fill out the "osTicket Basic Installion" form. At the bottom you will need to configure and connect a database so that osTicket to use. After that is done:<br>
<img src="images/Screenshot%202024-12-25%20043001.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

- SUCCESS! osTicket was successfully installed.

- When you go to localhost/osTicket/scp/login.php you should see this window to login as the admin:
<img src="images/Screenshot%202024-12-25%20043033.png" alt=""/>

- When you enter your credentials you will end up in the main dashboard:
<img src="images/Screenshot%202024-12-25%20043053.png" alt=""/>

- This is the end of the tutorial and you have installed the osTicket Help Desk Ticketing System.

