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

<p>

-  From the Home screen, select the <b>Virtual Machine</b> icon and click the <b>Create</b> option.  From the drop down menu, select <b>Azure virtual machine</b>.

</p>
<p>

![Step 1](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/631567e6-717d-4a67-8e0d-2bfcd205a978)

</p>

<br />


<p>

-  In the VM menu, begin to fill the required information in the <b>Basics</b> tab (feel free to use the above image as a guide to get started.)  Be sure to select a suitable sized vcpu set that best fits your financial needs and subscription plan.  In this case, Windows 10, 4CPUs is recommended.
	-	Username: osTuser (or whatever you choose)
	
	-	Password: Password12345 (or whatever you choose)
	
	-	Virtual Machine Name: vm1 (or whatever you choose

</p>
<p>

  ![Step 2](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/197196bb-abce-4c48-ae7a-6751366508df)


</p>

<br />
<p>

<b>Note:</b> Keep the Virtual network in mind the <b>Networking</b> tab for future use anytime multiple VMs are created to ensure they are all on same vnet.

</p>
<p>

  ![Step 3](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/3673536e-c43c-4831-aa16-fb3f0c19094b)

</p>

<br />

![Step 4](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/f5a12499-b396-4c47-a406-659408b4a963)

-  Once both the Basics and Networking tabs are complete, feel free to review any other tabs and select 'Review + create'.  Upon validation being completed, select 'Create'.

![Step 5](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/c9b89330-32d6-4b1a-ad70-458783a503e9)

![Step 6](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/56624a5b-85a0-4022-9f2e-e848eba77d3e)

-	After deployment is complete, select 'Go to resource' to review your vm's information.

![Step 7](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/eb246d7c-b3f7-4d00-886f-f5b4111276ec)

-	Begin to type 'Remote Desktop Connection' in your Window's search bar and select the app.  Once it is open, copy vm1's public ip address into the 'Computer' drop down menu and click 'Connect'.

![Step 8](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/ec060228-e700-4d35-8128-006f77ff7844)

-	The credentials entered will match the ones you created within vm1: 

Username: osTuser Password: 
Password12345.  

-	Click 'OK' when complete and select 'Yes' if a verification warning appears.

<h2>Installing Files and Downloading osTicket</h2>

![Step 10](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/b605c2f8-6525-47e3-8931-5913fa261cea)


The Following steps will all take place within vm1.
-	Provided below is the link containing all prerequisite files and programs needed to properly install osTicket:

https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6


![Step 11](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/1eaad5c5-d182-4551-9ca0-210449a54428)

-	Install / Enable IIS in Windows WITH CGI and Common HTTP Features AND IIS Management Console.

In order to do this, open the control panel within vm1, select 'Programs', and click 'Turn Windows features on or off'.  From there select the following:

⦁	World Wide Web Services -> Application Development Features ->

[X] CGI

[X] Common HTTP Features

⦁	Internet Information Services -> Web Management Tools -> 

[X] IIS Management Console

-	From the Installation Files, download and install <b>PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)</b>.
-	From the Installation Files, download and install the <b>Rewrite Module (rewrite_amd64_en-US.msi)</b>.

![Step 13](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/f1a5c54e-b383-4a11-8086-966de62f64f0)

![Step 14](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/17d260e5-843f-40a6-8009-380f6254b5e3)

![Step 15](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/1e68b62c-874b-4921-b26c-1a9586f45bc8)

-	From the Installation Files, download <b>PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip)</b> and unzip the contents into <b>C:\PHP</b>.

-	From the Installation Files, download and install <b>VC_redist.x86.exe.</b>.

![Step 16](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/9438cfcc-c648-4b58-a1a8-63e2207d0e2a)

-	From the Installation Files, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)

	-	Typical Setup

![Step 17](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/f02d25b3-1c31-4ccc-8898-75ef6567a7c4)

-	Launch Configuration Wizard (after install)

![Step 18](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/0e8b246d-3f59-4bea-8be6-7e8b04ee79a5)

-	Standard Configuration

![Step 19](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/22c8be13-edc8-41ea-9565-a5c66e9a8e4c)

![Step 20](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/9f19b02c-e947-4e15-96d5-9cc2e2347e3e)


-	For exercise purposes, use 'Password 1' for the root password.


![Step 21](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/22bd3b9e-9efe-48ad-9a68-acd7dcca1e8f)

-	Open IIS as an Admin by entering 'iss' into the Windows search bar, right-click the 'Internet Information Services (IIS) Manager' app, and select 'Run as administrator'.

![Step 22](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/dbd6ea2d-cfeb-4f7e-9493-af6f60b88c3c)

-	Register PHP from within IIS

	-	Select 'PHP Manager' from the IIS Manager

![Step 23](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/ed3f2243-7251-4d54-b282-b25e8605be2d)

 -	Click 'Registger new PHP version' ->

![Step 24](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/a19ec39a-ac9d-489a-8ccc-a8488632fc53)

-	When prompted to find a destination, navigate to the PHP folder within (C:) and select 'php-cgi'

  ![Step 25](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/344c773f-bd90-4891-ae9f-95c8acd393d5)

-	Reload IIS (Open IIS, Stop and Start the server or select Restart).

![Step 27](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/24c0f125-034e-48fb-beb3-61c326699be5)

-	Install <b>osTicket v1.15.8</b>

 	-	Download osTicket from the Installation Files Folder

 	-	Extract and copy “upload” folder to c:\inetpub\wwwroot

 	-	Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”

-	Reload IIS (Open IIS, Stop and Start the server).
 
![Step 29](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/c4ee3994-16c7-4cbd-8099-3b1f51f51668)

-	From the lefthand side, go to sites -> Default -> osTicket

 	-	On the right, click “Browse *:80”

![Step 30](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/5caed72c-558b-4b5c-a636-3b9f97345415)

-	Note that some extensions are not enabled.

![Step 31](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/23e815d5-b41c-4c1e-932e-be2c7a896280)

-	Go back to IIS, sites -> Default -> osTicket

	-	Double-click PHP Manager

![Step 32](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/36241a18-8746-470e-a0d4-95de9d874736)

-	Click “Enable or disable an extension”.

![Step 33](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/3bfec129-1842-4601-aa26-f2fccadcfa15)

-	Enable the following:

	-	php_imap.dll

	-	php_intl.dll

	-	php_opcache.dll

![Step 34](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/8878dc98-6dbb-498a-b00f-dad435e13352)

-	Refresh the osTicket site in your browse, observe the changes.

![Step 35](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/b7796642-b6ec-40fe-b78c-ce00e82f773e)

-	Rename: ost-config.php

 	-	From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php

 	-	To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

![Step 36](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/9e2f941f-f794-4c0b-ac9e-0f6453b01d38)

-	Assign permissions within ost-config.php by right-clicking said file and selecting 'Advanced'.

![Step 37](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/a79af6ec-74db-4224-bad7-ab9722eacca0)

-	Disable inheritance -> Remove All

![Step 38](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/34f46ce1-a14e-4d50-96e4-e182668e4e06)

-	Enable new permissions by selecting 'Add'.

![Step 39](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/c4f34930-7d6b-4e5f-86a0-c3e67d3b39b9)

-	Click 'Select a principal'.

![Step 40](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/6b20c411-1bb1-450a-bfd1-01df076803d2)

-	Enter 'Everyone' in the bottom text box -> click 'Check Names' -> Click 'Ok'.

![Step 41](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/f81ab1f3-3235-4710-b24f-d8fa9fa2b6fa)

-	Enable Full control for 'Everyone' and confirm with 'OK' -> 'Apply' -> 'OK'.

![Step 43](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/4f9ef300-c2d3-4c9a-8361-b3177c4da744)

-	Continue Setting up osTicket in the browser (click Continue)


![Step 44](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/ba1fc47e-558a-4232-9c69-029b1f90839a)

-	From the Installation Files, download and install HeidiSQL.

-	Open Heidi SQL

![Step 45](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/7f5e0cf7-c48d-46f6-8e83-b2fad1e5693e)


![Step 46](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/66c2af48-e99e-47a9-9efd-d2730bc03b83)

-	Create a new session using the root/Password1 combination made during the intitial MySQL installation.

-	Connect to the session

![Step 47](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/a5c402bd-2904-4d53-aa0e-b61f6b71bc4c)

![Step 48](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/056d0701-1f7a-4016-b8c5-a1128fabf062)


-	Create a database called “osTicket” by right-clicking within the window to the lefthand side.

	-	Click 'Create new' -> 'Database'

![Step 49](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/929024a2-08cb-40cb-a483-de83c042c9f8)

-	Continue Setting up osticket in the browser	

 	-	Name Helpdesk

 	-	Default email (receives email from customers)

	-	MySQL Database: osTicket

	-	MySQL Username: root

	-	MySQL Password: Password1

-	Click “Install Now!”

![Step 50](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/1f8c8fb9-52f3-4de4-b86d-0db8787eaac3)

-	Congratulations, hopefully it is installed with no errors!

-	Browse to your help desk login page: http://localhost/osTicket/scp/login.php

-	End Users osTicket URL: http://localhost/osTicket/

![Step 51](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/f274cffc-55c1-4c37-bfb4-dde1319d4f92)

![Step 52](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/2f58eef1-85bb-4ab0-a952-d544e000f512)

-	Clean up

 	-	Delete: C:\inetpub\wwwroot\osTicket\setup

 	-	Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php
