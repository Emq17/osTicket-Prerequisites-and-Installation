<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This step-by-step walkthrough is designed to help provide a detailed framework guiding you through the essential prerequisites & installation process of the open-source help desk ticketing system known as "osTicket."<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop Connection
- Internet Information Services (IIS)
- osTicket (Help Desk Ticketing System)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- MySQl
- PHP Manager
- HeidiSQl
- Rewrite Module
- Microsoft Visual C++

<h2>Installation Steps</h2>

- Once we are logged into our Virtual Machine
- Open up the Control Panel
- Go to Programs and Features
- Turn Windows Features on or off
- Enable IIS(Internet Information Services)
- Expand World Wide Web Services
- Enable CGI
- Enable all of the Common HTTP Features
- Hit OK.

![image](https://github.com/CarlosAlvarado0718/osticket-prereqs/assets/140138198/530a2d16-dd64-49a0-862a-8a33dac7d00a)

- Now that we've installed IIS
- Go into the installation files and install PHP Manager for IIS, (PHPManagerForIIS_V1.5.0.msi)
- Double click to Install from Files Explorer
- Complete the Installation process for PHP Manager.

![image](https://github.com/CarlosAlvarado0718/osticket-prereqs/assets/140138198/99bf3a59-8d45-44a8-b43e-e818a7dc32bb)

- From here, Install the Rewrite Module(rewrite_amd64_en-US.msi)
- In the same pattern from before, until completion.

  
![image](https://github.com/CarlosAlvarado0718/osticket-prereqs/assets/140138198/0e4b3d58-4f5e-452f-8ddb-c21d7b48d235)

- Now go into Files Explorer
- This PC
- Windows(C:)
- Create a folder named "PHP"

  
  ![image](https://github.com/CarlosAlvarado0718/osticket-prereqs/assets/140138198/9c73e0c4-bfef-4443-a932-1862ac7607a6)

- From the installation files
- unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into C:\PHP

  
  ![image](https://github.com/CarlosAlvarado0718/osticket-prereqs/assets/140138198/32360f37-fde1-48b3-963c-9abf0fe84e0a)


- From the installation files install VC_redist.x86.exe.


  ![image](https://github.com/CarlosAlvarado0718/osticket-prereqs/assets/140138198/6882d61c-ae1d-4287-8ea7-6904bf458dbc)

 - From the installation files install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
  
  - Typical Setup
  - Launch Configuration Wizard (after installation)
  - Standard Configuration
  - Password1 

  ![image](https://github.com/CarlosAlvarado0718/osticket-prereqs/assets/140138198/de834eb0-5630-4d66-919c-eee98b03e8fa)

 - Open IIS as an Administrator
 - Go to PHP Manager
 - Register new PHP version
 - Browse and choose the file PHP-CGI
 - Click Open
 - Restart the Server

  
  ![image](https://github.com/CarlosAlvarado0718/osticket-prereqs/assets/140138198/e8f58a87-b7d9-4c76-b052-da293ab79ac1)



  ![image](https://github.com/CarlosAlvarado0718/osticket-prereqs/assets/140138198/68b6a8f9-687f-4d36-b243-b7c0b0692aa5)


 - Install osTicket v1.15.8 
 - Locate the Upload folder within
 - Drag the Upload Folder to c:\inetpub\wwwroot
 - Within C:\inetpub\wwwroot, rename “upload” to “osTicket”


  ![image](https://github.com/CarlosAlvarado0718/osticket-prereqs/assets/140138198/e0df4bc4-6040-47ef-88ba-36691f9a61a9)

![image](https://github.com/CarlosAlvarado0718/osticket-prereqs/assets/140138198/fb259c8b-dd1f-4c8f-9bf7-17c4baa18469)

- Go to IIS Sites
- Default Web Site
- osTicket
- Enable or diable an extension
- Enable php_imap.dll, php_intl.dll, php_opcache.dll 

  ![image](https://github.com/CarlosAlvarado0718/osticket-prereqs/assets/140138198/9d6b2b3e-f78a-48cc-a181-3badebd7c8a6)


- Go to Browse *80 (http) -> Cotinue 


  ![image](https://github.com/CarlosAlvarado0718/osticket-prereqs/assets/140138198/c66ec2f2-c39d-412a-a807-5e5fa4f71331)


- Go to File Explorer
- C:\inetpub
- wwwroot
- osTicket
- include
- ost-sampleconfig.php
- Change the file name to ost-config.php
- Propteries
- Security (advanced)
- Disable Inheritance
- Add Everyone to full control
- Apply and Ok
- Go back to Local Host Website and Continue


  ![image](https://github.com/CarlosAlvarado0718/osticket-prereqs/assets/140138198/26da08c4-18e0-4348-928c-222058ee940b)

  ![image](https://github.com/CarlosAlvarado0718/osticket-prereqs/assets/140138198/2dca7648-7a0a-4916-b050-7b21d278cbdc)



- Fill out all of the osTicket Basic Installation Information and stop at the database settings.


  ![image](https://github.com/CarlosAlvarado0718/osticket-prereqs/assets/140138198/eac087a6-2cde-4c59-9e88-14719fc92ec4)


- From the installation files install HeidiSQL
- Open Heidi SQL
- Create a new session
- root
- Password1
- Connect to the session
- Create a database called “osTicket”
- Click Open
- Place all of the information into Database Settings
- Install now


  ![image](https://github.com/CarlosAlvarado0718/osticket-prereqs/assets/140138198/3fba5b30-f5f1-4697-a625-33adf724831a)

![image](https://github.com/CarlosAlvarado0718/osticket-prereqs/assets/140138198/a46fff1e-b672-4147-96a3-3fcaa3e585e8)


- You've installed osTicket successfully



  ![image](https://github.com/CarlosAlvarado0718/osticket-prereqs/assets/140138198/0986351f-e7ef-48f6-81b7-8b367f6958fe)

 Using this <a href="http://localhost/osTicket/scp/login.php">Link</a>, you'll enter your email or username and password to enter into osTicket, This should be your screen and that will conclude our project! CONGRAT!!!
