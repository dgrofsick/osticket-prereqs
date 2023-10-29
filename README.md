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

- Windows 11</b>

<h2>List of Prerequisites</h2>

- PHP Manager for IIS
- Rewrite Module
- PHP 7.3.8
- VC_redist.x86
- MY SQL 5.5.62
- osTicket v1.15.8
- HeidiSQL 

<h2>Setting Up Your Virtual Machine in Azure</h2>


-  From the Home screen, select the <b>Virtual Machine</b> icon and click the <b>Create</b> option.  From the drop down menu, select <b>Azure virtual machine</b>.


![Step 1](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/631567e6-717d-4a67-8e0d-2bfcd205a978)

<br />


-  In the VM menu, begin to fill the required information in the <b>Basics</b> tab (feel free to use the above image as a guide to get started.)  Be sure to select a suitable sized vcpu set that best fits your financial needs and subscription plan.  In this case, Windows 10, 4CPUs is recommended.
	-	Username: <b>osTuser (or whatever you choose)</b>
	
	-	Password: <b>Password12345 (or whatever you choose)</b>
	
	-	Virtual Machine Name: <b>vm1 (or whatever you choose)</b>


![Step 2](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/197196bb-abce-4c48-ae7a-6751366508df)


<br />

<b>Note:</b> Keep the Virtual network in mind the <b>Networking</b> tab for future use anytime multiple VMs are created to ensure they are all on same vnet.

![Step 3](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/3673536e-c43c-4831-aa16-fb3f0c19094b)

<br />

-	Once both the Basics and Networking tabs are complete, feel free to review any other tabs and select 'Review + create'.  Upon validation being completed, select <b>Create</b>.

![Step 4](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/f5a12499-b396-4c47-a406-659408b4a963)

-	After deployment is complete, select <b>Go to resource</b> to review your vm's information

![Step 5](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/c9b89330-32d6-4b1a-ad70-458783a503e9)

![Step 6](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/56624a5b-85a0-4022-9f2e-e848eba77d3e)
 
 <br />

-	Begin to type <b>Remote Desktop Connection</b> in your Window's search bar and select the app.  Once it is open, copy vm1's public ip address into the <b>Computer</b> drop down menu and click <b>Connect</b>.

![Step 7](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/eb246d7c-b3f7-4d00-886f-f5b4111276ec)

-	The credentials entered will match the ones you created within vm1: 

	-	Username: <b>osTuser</b>
	-	Password: <b>Password12345</b> 

-	Click <b>OK</b> when complete and select <b>Yes</b> if a verification warning appears

![Step 8](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/ec060228-e700-4d35-8128-006f77ff7844)
 
 <br />

<h2>Installing Files and Downloading osTicket</h2>

<b>The Following steps will all take place within vm1.</b>

-	Provided below is the link containing all prerequisite files and programs needed to properly install osTicket:

https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6

![Step 10](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/b605c2f8-6525-47e3-8931-5913fa261cea)
 
 <br />


<b>Install / Enable IIS in Windows WITH CGI and Common HTTP Features AND IIS Management Console.</b>

- In order to do this, open the control panel within vm1, select 'Programs', and click 'Turn Windows features on or off'.  From there select the following:

	-	Click Internet Information Services -> Web Management Tools -> Check [X] IIS Management Console

	-	Click World Wide Web Services -> Application Development Features -> Check [X] CGI and [X] Common HTTP Features


![Step 11](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/1eaad5c5-d182-4551-9ca0-210449a54428)

<br />

<h3>PHP Manager for ISS</h3>

-	From the Installation Files, download and install <b>PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)</b>.

<h3>Rewrite Module</h3>

-	From the Installation Files, download and install the <b>Rewrite Module (rewrite_amd64_en-US.msi)</b>.

<h3>PHP 7.3.8</h3>

-	Create the directory <b>C:\PHP</b>

-	From the Installation Files, download <b>PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip)</b> and unzip the contents into <b>C:\PHP</b>.

![Step 13](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/f1a5c54e-b383-4a11-8086-966de62f64f0)

![Step 14](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/17d260e5-843f-40a6-8009-380f6254b5e3)

![Step 15](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/1e68b62c-874b-4921-b26c-1a9586f45bc8)

<br />

<h3>VC_redist.86.exe</h3>

-	From the Installation Files, download and install <b>VC_redist.x86.exe.</b>.

<h3>MySQL 5.5.62</h3>

-	From the Installation Files, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)

	-	Select Typical Setup
	-	Launch Configuration Wizard (after install)
	-	Standard Configuration

![Step 16](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/9438cfcc-c648-4b58-a1a8-63e2207d0e2a)


![Step 17](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/f02d25b3-1c31-4ccc-8898-75ef6567a7c4)


![Step 18](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/0e8b246d-3f59-4bea-8be6-7e8b04ee79a5)


-	For exercise purposes, use <b>Password 1</b> for the root password.

![Step 19](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/22c8be13-edc8-41ea-9565-a5c66e9a8e4c)

![Step 20](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/9f19b02c-e947-4e15-96d5-9cc2e2347e3e)

<br />

-	Open IIS as an Admin by entering <b>iss</b> into the Windows search bar, right-click the <b>Internet Information Services (IIS) Manager</b> app, and select <b>Run as administrator</b>.

![Step 21](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/22bd3b9e-9efe-48ad-9a68-acd7dcca1e8f)

<br />

-	Register PHP from within IIS

	-	Select <b>PHP Manager</b> from the IIS Manager

![Step 22](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/dbd6ea2d-cfeb-4f7e-9493-af6f60b88c3c)

<br />

-	Click <b>Registger new PHP version'</b>

![Step 23](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/ed3f2243-7251-4d54-b282-b25e8605be2d)

<br />

-	When prompted to find a destination, navigate to the PHP folder within (C:) and select <b>php-cgi</b>

![Step 24](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/a19ec39a-ac9d-489a-8ccc-a8488632fc53)

<br />

-	Reload IIS
	-	Open IIS, Stop and Start the server or select <b>Restart</b>

![Step 25](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/344c773f-bd90-4891-ae9f-95c8acd393d5)

<br />

<h3>osTicket</h3>

-	Install <b>osTicket v1.15.8</b>

 	-	Download osTicket from the Installation Files Folder

 	-	Extract and copy “upload” folder to c:\inetpub\wwwroot

 	-	Within c:\inetpub\wwwroot, rename the folder “upload” to “osTicket”

-	Reload IIS (Open IIS, Stop and Start the server).

![Step 27](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/24c0f125-034e-48fb-beb3-61c326699be5)

<br />

-	From the lefthand side, go to sites -> Default -> osTicket

 	-	On the right, click <b>Browse *:80</b>

 
![Step 29](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/c4ee3994-16c7-4cbd-8099-3b1f51f51668)

<br />

-	Note that some extensions are not enabled

![Step 30](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/5caed72c-558b-4b5c-a636-3b9f97345415)

<br />

-	Go back to IIS, sites -> Default -> osTicket

	-	Double-click <b>PHP Manager</b>

![Step 31](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/23e815d5-b41c-4c1e-932e-be2c7a896280)

<br />

-	Click <b>Enable or disable an extension</b>

![Step 32](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/36241a18-8746-470e-a0d4-95de9d874736)

<br />

-	Enable the following:

	-	php_imap.dll

	-	php_intl.dll

	-	php_opcache.dll

![Step 33](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/3bfec129-1842-4601-aa26-f2fccadcfa15)

<br />

-	Refresh the osTicket site in your browse, observe the changes


![Step 34](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/8878dc98-6dbb-498a-b00f-dad435e13352)

<br />

-	Rename: ost-config.php

 	-	Locate the file within C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php

 	-	Change from ost-<b>sample</b>config.php to <b>ost-config.php</b>

![Step 35](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/b7796642-b6ec-40fe-b78c-ce00e82f773e)

<br />

-	Assign permissions within ost-config.php by right-clicking <b>ost-config.php</b> and selecting <b>Advanced</b>

![Step 36](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/9e2f941f-f794-4c0b-ac9e-0f6453b01d38)

<br />

-	Click <b>Disable inheritance</b> -> <b>Remove All</b>


![Step 37](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/a79af6ec-74db-4224-bad7-ab9722eacca0)

<br />

-	Enable new permissions by selecting <b>Add</b>

![Step 38](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/34f46ce1-a14e-4d50-96e4-e182668e4e06)

<br />

-	Click <b>Select a principal</b>.

![Step 39](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/c4f34930-7d6b-4e5f-86a0-c3e67d3b39b9)

<br />

-	Enter <b>Everyone</b> in the bottom text box -> click <b>Check Names</b> -> Click <b>Ok</b>

![Step 40](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/6b20c411-1bb1-450a-bfd1-01df076803d2)

<br />

-	Enable Full control for <b>Everyone</b> and confirm with <b>OK</b> -> <b>Apply</b> -> 'OK'

![Step 41](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/f81ab1f3-3235-4710-b24f-d8fa9fa2b6fa)

<br />

-	Continue setting up osTicket in the browser (click Continue)

![Step 43](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/4f9ef300-c2d3-4c9a-8361-b3177c4da744)

<br />

<h3>HeidiSQL</h3>

-	From the Installation Files, download and install <b>HeidiSQL</b>

-	Open <b>Heidi SQL</b>

![Step 44](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/ba1fc47e-558a-4232-9c69-029b1f90839a)

<br />

-	Create a new session using the root/Password1 combination made during the intitial MySQL installation

-	Connect to the session by selecting <b>Open</b>

![Step 45](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/7f5e0cf7-c48d-46f6-8e83-b2fad1e5693e)


![Step 46](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/66c2af48-e99e-47a9-9efd-d2730bc03b83)

<br />

-	Create a database called <b>osTicket</b> by right-clicking within the window to the lefthand side

-	Click <b>Create new</b> -> <b>Database</b>

![Step 47](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/a5c402bd-2904-4d53-aa0e-b61f6b71bc4c)

![Step 48](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/056d0701-1f7a-4016-b8c5-a1128fabf062)

<br />

-	Continue Setting up osticket in the browser	

 	-	Name Helpdesk

 	-	Default email (receives email from customers)

	-	MySQL Database: osTicket

	-	MySQL Username: root

	-	MySQL Password: Password1

-	Click “Install Now!”

![Step 49](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/929024a2-08cb-40cb-a483-de83c042c9f8)

<br />

-	Congratulations, hopefully it is installed with no errors!

-	Browse to your help desk login page: http://localhost/osTicket/scp/login.php

-	End Users osTicket URL: http://localhost/osTicket/

![Step 50](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/1f8c8fb9-52f3-4de4-b86d-0db8787eaac3)

<br />

-	Clean up

 	-	Delete: C:\inetpub\wwwroot\osTicket\setup

 	-	Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php

![Step 51](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/f274cffc-55c1-4c37-bfb4-dde1319d4f92)

![Step 52](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/2f58eef1-85bb-4ab0-a952-d544e000f512)

