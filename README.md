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

<img src="images/Screenshot%202024-12-25%20042937.png" alt=""/>
</p>
<p>
You want to make sure that you Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="images/Screenshot%202024-12-25%20043001.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="images/Screenshot%202024-12-25%20043033.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="images/Screenshot%202024-12-25%20043053.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="images/Screenshot%202024-12-25%20043115.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="images/Screenshot%202024-12-25%20043137.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

