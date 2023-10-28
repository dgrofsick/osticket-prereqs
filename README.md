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

![Step 1](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/631567e6-717d-4a67-8e0d-2bfcd205a978)

</p>
<p>

-  From the Home screen, select the 'Virtual Machine' icon and click the 'Create' option.  From the drop down menu, select 'Azure virtual machine'.

</p>
<br />


<p>

  ![Step 2](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/197196bb-abce-4c48-ae7a-6751366508df)


</p>

<p>

-  In the VM menu, begin to fill the required information in the Basics tab (feel free to use the above image as a guide to get started.)  Be sure to select a suitable sized vcpu set that best fits your financial needs and subscription plan.  In this case, Windows 10, 4CPUs is recommended.

Username: osTuser (or whatever you choose)
	
 Password: Password12345 (or whatever you choose)
	
 Virtual Machine Name: vm1 (or whatever you choose

</p>
<br />

<p>

  ![Step 3](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/3673536e-c43c-4831-aa16-fb3f0c19094b)

</p>
<p>
*Note the Virtual network for future use anytime multiple VMs are created to ensure they are all on same vnet.

</p>
<br />

![Step 4](https://github.com/dgrofsick/osticket-prereqs/assets/148154704/f5a12499-b396-4c47-a406-659408b4a963)

-  Once both the Basics and Networking tabs are complete, feel free to review any other tabs and select 'Review + create'.  Upon validation being completed, select 'Create'.

