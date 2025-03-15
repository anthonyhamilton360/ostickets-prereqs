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

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine Windows 10, 4 vCPUs
- osTicket Installation Files
- Admin User Credentials (for database and osTicket setup)
- PHP 7.4 - 8.0 (Latest stable version recommended)
- MySQL 5.5+ or MariaDB 10.0+

<h2>Installation Steps</h2>

![Screenshot 2025-03-08 225954](https://github.com/user-attachments/assets/5b2b873b-9bca-4209-b8c2-8f50a1dc5a7d)

<p>
</p>
<p>
I start by creating a virtual machine using Microsoft Azure. 
</p>
<br />

<p>
  
![Screenshot 2025-03-08 230116](https://github.com/user-attachments/assets/5d6e123b-2048-4fcb-9bad-8601435d9432)

</p>
<p>
Renaming the resource group to osTicket.
</p>
<br />

<p>
  
![Screenshot 2025-03-08 230408](https://github.com/user-attachments/assets/6f8e97f0-aeca-452a-b58f-5d8b3daf3e2f)

</p>
<p>
Renaming the virtual machine to osticket-vm, choose a region and selecting Windows 10 Pro version 22H2 x64 Gen2. Click Next for until you get to review and create.
</p>
<br />


<p>
  
![Screenshot 2025-03-08 231450](https://github.com/user-attachments/assets/01031bf1-f428-489e-b803-4595a6244b9b)

</p>
<p>
After reviewing inputs and selections click create.
</p>
<br />


<p>
  
![Screenshot 2025-03-08 231508](https://github.com/user-attachments/assets/0403b595-5126-40f2-b0b6-b055ad202e9d)

</p>
<p>
Wait until the vm finish deploying.
</p>
<br />

<p>
  
![Screenshot 2025-03-08 231731](https://github.com/user-attachments/assets/f2bdd3a9-1f86-4c9a-8b04-e164045c5bbe)

</p>
<p>
  Deployment is complete!
</p>
<br />


<p>
  
![Screenshot 2025-03-08 231925](https://github.com/user-attachments/assets/0acc7c9e-e6a9-4743-a4e0-db46e7c30975)

</p>
<p>
Navigate to Virtual Machines copy public IP address and launch Remote Desktop Connection.
</p>
<br />


<p>
  
![Screenshot 2025-03-08 232049](https://github.com/user-attachments/assets/76df2719-49f3-4d7c-a06e-2cfc9386c732)

</p>
<p>
After successfully signing into remote desktop click yes.
</p>
<br />

<p>
  
![Screenshot 2025-03-08 232512](https://github.com/user-attachments/assets/186611c4-e3a8-42c5-baf5-75a63a2de2d7)

</p>
<p>
  Downloaing files for osTickket installation.
</p>
<br />

<p>
  
![Screenshot 2025-03-08 232716](https://github.com/user-attachments/assets/9088703a-3ba7-40cb-9fdd-25af4ea0cf14)

</p>
<p>
Extractnig folder to desktop.
</p>
<br />

<p>
  
![Screenshot 2025-03-08 233021](https://github.com/user-attachments/assets/3211ebcb-f8e2-40eb-a24f-7fd20a211a6c)

</p>
<p>
Confirming that the loopback address isn't responding before installing IIS with CGI enabled.
<br />

<p>
  
![Screenshot 2025-03-08 233106](https://github.com/user-attachments/assets/7b51bc8b-ff9c-4e48-9541-fc87708419b5)

</p>
<p>
Launch Control Panel.
</p>
<br />

<p>
  
![Screenshot 2025-03-08 233236](https://github.com/user-attachments/assets/f4e51870-879f-4158-8a0b-b1db9f99aa66)


</p>
<p>
Navigate to Programs and click on "Turn Windows features on or off".
</p>
<br />

<p>
  
![Screenshot 2025-03-08 233329](https://github.com/user-attachments/assets/04115218-0233-4fd1-8989-21c21477c174)


</p>
<p>
Check the "Internet Information Services" box.
</p>
<br />

<p>
  
![Screenshot 2025-03-08 233417](https://github.com/user-attachments/assets/b5d56d51-4123-414d-9c69-673bdb10eab5)


</p>
<p>
Drop down to World Wide Services within the IIS folder.
</p>
<br />

<p>
  
![Screenshot 2025-03-08 233440](https://github.com/user-attachments/assets/bb2afe1a-55eb-4e5e-8546-09a925335a01)


</p>
<p>
Expand Application Development Features
</p>
<br />

<p>
  
![Screenshot 2025-03-08 233455](https://github.com/user-attachments/assets/f7ba6da6-9961-4340-b222-fc29d6b38f5a)


</p>
<p>
Check CGI box and click OK
</p>
<br />

<p>
  
![Screenshot 2025-03-08 233542](https://github.com/user-attachments/assets/947d3da7-e13d-4f29-964c-fa6e66d2968e)


</p>
<p>
After enabling IIS and CGI close the window.
</p>
<br />

<p>
  
![Screenshot 2025-03-08 233641](https://github.com/user-attachments/assets/ca4b2f3b-8b19-497a-8a72-fbf55cac7ad6)


</p>
<p>
Reftresh the loopback address of 127.0.0.1 and we can see that IIS has been installed successfully.
</p>
<br />

<p>
  
![Screenshot 2025-03-08 233945](https://github.com/user-attachments/assets/4e5dac60-2df9-43cf-a11b-d0b248fb5b50)



</p>
<p>
Go tothe osTicket installation files that was extracted to the desktop andlaunch the PHP Manager installation.
</p>
<br />

<p>
  
![Screenshot 2025-03-08 234007](https://github.com/user-attachments/assets/1e3fe0df-1721-4b8e-91c9-fa15e53d3ec9)


</p>
<p>
Launch the installer
</p>
<br />

<p>
  
![Screenshot 2025-03-08 234145](https://github.com/user-attachments/assets/934ece59-87c5-4620-a27a-fb917a5a66e2)


</p>
<p>
Launch and install the rewrite module 2 setup.
</p>
<br />

<p>
  
![Screenshot 2025-03-08 234529](https://github.com/user-attachments/assets/2638d3b0-2e43-4c03-b91d-eeaa80a74f86)


</p>
<p>
Navigate to the C drive and within Windows folder create a new folder.
</p>
<br />

<p>
  
![Screenshot 2025-03-08 234555](https://github.com/user-attachments/assets/4f639df5-f9c0-47ea-bd9e-3bac3c388734)


</p>
<p>
Rename the folder to PHP
</p>
<br />

<p>
  
![Screenshot 2025-03-08 234653](https://github.com/user-attachments/assets/edcc795f-5932-4c91-98f5-75b6d2fdcae4)


</p>
<p>
Within the osTicket Installation files on the desktop, click Extract All.
</p>
<br />

<p>
  
![Screenshot 2025-03-08 234721](https://github.com/user-attachments/assets/d49c0dde-124e-4202-9fdd-e814a21e18f0)


</p>
<p>
Browse to the PHP folder within the Windows folder on the C drive and extract the files to the PHP folder.
</p>
<br />

<p>
  
![Screenshot 2025-03-08 234817](https://github.com/user-attachments/assets/b7febe84-04ef-4420-96e0-117c36181001)



</p>
<p>
Back to the osticket installation launch VC_redistx86.
</p>
<br />

<p>
  
![Screenshot 2025-03-08 234836](https://github.com/user-attachments/assets/ef87ef38-875e-4fc2-9ae4-90f6de1a7712)



</p>
<p>
Install the VC Redistributable.
</p>
<br />

<p>
  
![Screenshot 2025-03-08 234918](https://github.com/user-attachments/assets/24b258e0-b473-45c9-bfa5-fb96eb04412c)



</p>
<p>
Go to the osticket installtion folder and launch the mysql installer.
</p>
<br />

<p>
  
![Screenshot 2025-03-08 234934](https://github.com/user-attachments/assets/b767ee90-1244-4046-baa6-c900686852ef)



</p>
<p>
Click Next
</p>
<br />

<p>
  
![Screenshot 2025-03-08 235010](https://github.com/user-attachments/assets/e6ce6c15-e5ed-4bd4-8c4a-b1aa55210ae6)



</p>
<p>
After reviewing and accepting the terms click Next.
</p>
<br />

<p>
  
![Screenshot 2025-03-08 235018](https://github.com/user-attachments/assets/73d93742-0894-4ea9-83ca-168c196e1d7a)




</p>
<p>
Choose Typical installation.
</p>

<p>
  
![Screenshot 2025-03-08 235028](https://github.com/user-attachments/assets/7ebcbbb4-da1e-44de-9fb1-84375fbf62eb)



</p>
<p>
Click Install.
</p>
<br />


<p>
  
![Screenshot 2025-03-08 235220](https://github.com/user-attachments/assets/6dbe3baa-afd9-4504-a335-252154624f5f)



</p>
<p>
Afterthe installation is complete check the Launch the MySQL Instance Configuration Wizard and click Finish.
</p>
<br />

<p>
  
![Screenshot 2025-03-08 235229](https://github.com/user-attachments/assets/c26487bc-963d-4c29-9188-3e42b7d37b11)



</p>
<p>
Click Next.
</p>
<br />

<p>
  
![Screenshot 2025-03-08 235351](https://github.com/user-attachments/assets/af715d78-e513-41c0-8e95-1ed2eef4bd2f)



</p>
<p>
Select Standard Configuration.
</p>
<br />

<p>

<p>
  
![Screenshot 2025-03-08 235427](https://github.com/user-attachments/assets/d8df8d9a-60bf-4779-b202-3dad38627bda)



</p>
<p>
Leave this page as is and click Next.
</p>
<br />

<p>
  
![Screenshot 2025-03-08 235602](https://github.com/user-attachments/assets/6e8e4ccc-0668-415e-8adf-7acf494be8cf)



</p>
<p>
For the sake of this lab,  I created my password as root all lowercase but I wouldn't recommend this in a live workplace enviornment.
</p>
<br />

<p>
  
![Screenshot 2025-03-08 235648](https://github.com/user-attachments/assets/c31e3357-4792-41bd-b237-f54171d7496a)



</p>
<p>
After all the configuratons are done processing click Finish.
</p>
<br />

<p>
  
![Screenshot 2025-03-08 235859](https://github.com/user-attachments/assets/4a1d4394-68e1-4d9b-992b-d42c8b62e030)



</p>
<p>
Type IIS in the search bar and launch IIS
</p>
<br />

<p>
  
![Screenshot 2025-03-09 000010](https://github.com/user-attachments/assets/2c4d1f51-44be-4fc6-aa01-4ca7f580d11c)


</p>
<p>
Navigate to the PHP Manager and launch the application
</p>
<br />

<p>
  
![Screenshot 2025-03-09 000033](https://github.com/user-attachments/assets/550c3fd3-8436-40ea-b5cb-def30920eab2)



</p>
<p>
  Here, we have to provide a path for the php executable.
</p>
<br />

<p>
  
![Screenshot 2025-03-09 000053](https://github.com/user-attachments/assets/6601f349-420e-43b7-ba75-5d41095d0bd5)

</p>
<p>
Browse to the Windows C drive and open the PHP folder.
</p>
<br />

<p>
  
![Screenshot 2025-03-09 000103](https://github.com/user-attachments/assets/2d425fb1-6cec-4da2-8419-a2fd7308c19c)

</p>
<p>
Open the php-cgi application
</p>
<br />

<p>
  
![Screenshot 2025-03-09 000113](https://github.com/user-attachments/assets/e84b378b-a087-4a4e-93ac-8be2b5fd5ec0)

</p>
<p>
Click OK 
</p>
<br />

<p>
  
![Screenshot 2025-03-09 000252](https://github.com/user-attachments/assets/d3fe40e8-993e-4bc8-bd5b-04c63220fb17)


</p>
<p>
Within IIS, right click and stop the connection.
</p>
<br />

<p>
  
![Screenshot 2025-03-09 000319](https://github.com/user-attachments/assets/fe9f74c5-b042-41e2-b158-1ef30b12b9ac)



</p>
<p>
Right click again and start the connectionton.
</p>
<br />

<p>
  
![Screenshot 2025-03-09 000519](https://github.com/user-attachments/assets/944b50f1-6173-4535-b238-e6f6275010ce)




</p>
<p>
Go yo the osTicket installtion files, right click on the osTicket-v1.15.8 file and click Extract All
</p>
<br />

<p>
  
![Screenshot 2025-03-09 000533](https://github.com/user-attachments/assets/2353aec1-ec94-4ef8-ad6d-7432d2190151)





</p>
<p>
Extract files within the osTicket Installtion folder and copy the “upload” folder into “c:\inetpub\wwwroot”
Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”

</p>
<br />

<p>
  
![Screenshot 2025-03-09 001000](https://github.com/user-attachments/assets/16442e75-4fa1-4373-b312-458e8274711c)


</p>
<p>
Reload IIS by right clicking and stopping the service.
</p>
<br />

<p>
  
![Screenshot 2025-03-09 001019](https://github.com/user-attachments/assets/50c17aa1-13f6-4b9a-9054-14dbe9052cf1)

</p>
<p>
Start the service.
</p>
<br />

<p>
  
![Screenshot 2025-03-09 001147](https://github.com/user-attachments/assets/b0f79e5b-74ba-4cbf-874b-34d1a50070c8)

</p>
<p>
Within IIS, click the drop arrow on Application Pools, Sites, Default Web Site and click on osTicket. On the right hand side click on “Browse *:80”
</p>
<br />

<p>
  
![Screenshot 2025-03-09 001231](https://github.com/user-attachments/assets/df268760-1711-40c3-90a5-bd84130b1659)

</p>
<p>
osTicket installer has been launched. Now to enable some features!
<br />

<p>
  
![Screenshot 2025-03-09 001611](https://github.com/user-attachments/assets/4e472cfe-c34e-4837-9b9a-9a3c7edc5a6d)

</p>
<p>
Open IIS and double-click on PHP Manager.
</p>
<br />

<p>
  
![Screenshot 2025-03-09 001639](https://github.com/user-attachments/assets/23616dd0-d8e3-41dc-ba8c-233865b6e307)

<p>
Click on "Enable or disable an extension".
<br />

<p>
  
![Screenshot 2025-03-09 001726](https://github.com/user-attachments/assets/1bb14788-82c8-4cad-961e-44f2ab3345e6)


<p>
Right click and Enable php_imap.dll
<br />

<p>
  
![Screenshot 2025-03-09 001824](https://github.com/user-attachments/assets/7f5f3512-f441-45a8-b147-aea0abf96ffb)



<p>
Right click and Enable php_intl.dll
</p>
<br />

<p>
  
![Screenshot 2025-03-09 001903](https://github.com/user-attachments/assets/1134c443-b27a-42b6-91a3-0470d456b426)



<p>
Right click and Enable php_apache.dll
</p>
<br />

<p>
  
![Screenshot 2025-03-09 002109](https://github.com/user-attachments/assets/6a03cd5d-13a6-4973-92d4-7f115832c818)



<p>
Reload the browser and features have been enabled!
<br />

<p>
  
![Screenshot 2025-03-09 002515](https://github.com/user-attachments/assets/80994039-9579-42eb-9899-a1ed12a5dfd5)



<p>
Navigate to C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php, rename it to ost-config.php, right click and go to Properties.
   
</p>
<br />

<p>
  
![Screenshot 2025-03-09 002540](https://github.com/user-attachments/assets/8a9f9a31-be8a-41ca-8232-ba11efc4c8be)



<p>
Go to the Security tab and click on Advanced.
</p>
<br />

<p>
  
![Screenshot 2025-03-09 002623](https://github.com/user-attachments/assets/216f5a91-8e16-4b16-99c0-bcbc9b6d468c)



<p>
Click on Disable inheritence and Remove all inherited permissions from this object.
</p>
<br />

<p>
  
![Screenshot 2025-03-09 002712](https://github.com/user-attachments/assets/c84cd607-4148-4d1f-bb04-99ee3014c881)



<p>
Click Add.
</p>
<br />

<p>
  
![Screenshot 2025-03-09 002746](https://github.com/user-attachments/assets/1b223f52-b8a1-40bd-a787-23f5d4d310a1)



<p>
Type Everyne and click OK
</p>
<br />

<p>
  
![Screenshot 2025-03-09 002819](https://github.com/user-attachments/assets/fee53a29-149f-45c5-90c7-45e8d47edb79)



<p>
Allow all permissions and click OK. 
</p>
<br />

<p>
  
![Screenshot 2025-03-09 002852](https://github.com/user-attachments/assets/27b9d307-be7a-4c72-b164-b8c849a439ba)




<p>
Click OK.
</p>
<br />

<p>
  
![Screenshot 2025-03-09 003243](https://github.com/user-attachments/assets/655194d7-6eb2-4142-b9d8-9ecb7f477dbc)

<p>
Fill out basic information for the installer.
</p>
<br />

<p>
  
![Screenshot 2025-03-09 003331](https://github.com/user-attachments/assets/9c440b6a-b7f7-402e-8fda-9e8cf99a6a1a)

<p>
Navigate to osTicket installation folder launch HeidiSQL
</p>
<br />

<p>
  
![Screenshot 2025-03-09 003354](https://github.com/user-attachments/assets/3e013e59-50fd-4d31-9c5a-0cc5e9399154)

<p>
After reviewing the terms, accept the terms and click Next.
</p>
<br />

<p>
  
![Screenshot 2025-03-09 003409](https://github.com/user-attachments/assets/8be3b152-7909-48f5-83d4-955809c746c1)

<p>
Check all boxes and click Next.
</p>
<br />

<p>
  
![Screenshot 2025-03-09 003425](https://github.com/user-attachments/assets/b417e66b-b5f3-4195-b995-bffb1395c932)

<p>
Make sure "Launch HeidiSQL" is checked and click Finish
</p>
<br />

<p>
  
![Screenshot 2025-03-09 003618](https://github.com/user-attachments/assets/71fd6840-223f-43ea-82d1-0b85700caa16)


<p>
Once Heidi is launched, click New. The user name and password will be root and click Open.
</p>
<br />

<p>
  
![Screenshot 2025-03-09 003804](https://github.com/user-attachments/assets/3dc0ff40-d1dc-48c4-942f-deea815f0853)


<p>
Right click and create a new Database
</p>
<br />

<p>
  
![Screenshot 2025-03-09 003841](https://github.com/user-attachments/assets/de4a0842-52bf-4507-b116-114dcb981067)


<p>
Name the database "osTicket"
</p>
<br />

<p>
  
![Screenshot 2025-03-09 004024](https://github.com/user-attachments/assets/ea9d63ac-f5e0-473e-9bc2-227908abbc71)


<p>
The information we used to create our database will be used for the configuration settings for the osTicket installer.
</p>
<br />

<p>
  
![Screenshot 2025-03-09 004102](https://github.com/user-attachments/assets/3615fa41-81e4-4c0f-97a2-8a882ffc889a)


<p>
osTicket has been successfully installed!
</p>
<br />

<p>
  
![Screenshot 2025-03-09 004141](https://github.com/user-attachments/assets/878a1e98-f6a4-4f9d-a431-1e18e7461ba4)


<p>
Refresh the osTicket database
</p>
<br />

<p>
  
![Screenshot 2025-03-09 004426](https://github.com/user-attachments/assets/1bef7401-10c6-4c93-8fcf-cd13be98300e)


<p>
On the internet browser, navigate to http://localhost/osTicket/scp/login.php and use login credentials to log into osTicket.

</p>
<br />

<p>
  
![Screenshot 2025-03-09 004454](https://github.com/user-attachments/assets/469b1f2f-ad38-4f27-a57e-2fb9d7b00921)


<p>
Congradtulations! osTicket login has been successful!
</p>
<br />
