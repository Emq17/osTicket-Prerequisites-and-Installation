<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This step-by-step walkthrough is designed to help provide a detailed framework guiding you through the essential prerequisites & installation process of the open-source help desk ticketing system known as "osTicket."<br />



<h2>Environments and Technologies</h2>

- Microsoft Azure
- Microsoft Remote Desktop (Mac)
- Internet Information Services (IIS) (Web server osTicket runs on)
- osTicket

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)

<h2>List of Prerequisites</h2>

- Installation Files https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6
- MySQL
- PHP Manager
- HeidiSQL
- Rewrite Module (Requirement for osTicket to work)
- Microsoft Visual C++

<h2>Installation Steps</h2>

- Please refer to https://github.com/Emq17/Establishing-Virtual-Machines-With-Remote-Desktop to set up VM.
  - Apply 2-4 Virtual CPU's & allow it to create a new Virtual Network (Vnet).
- Once we are logged into your Virtual Machine, install and enable IIS with Windows CGI:
  - Open up the Control Panel
  - Go to Programs
  - Under "Programs and Features", click "Turn Windows features on or off"
  - Check box & enable "Internet Information Services" then hit expand
  - A dropdown should appear. Expand "World Wide Web Services" then "Application Development Features"
  - Check box to enable CGI then collapse dropdown for "Application Development Features"
  - Expand "HTTP Features" & enable all by making sure every box is checked
  - Hit OK.

![Screen Shot 2023-12-21 at 4 30 42 AM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/c9baf7b1-c2cd-4b93-ae15-cb90dbd22b75)

- Installation of IIS should begin
- Once finished, test this by going to your browswer and typing in 127.0.0.1 (local host)
- You should be able to see the loaded default ISS website below and know that our web server is up and running

![Screen Shot 2023-12-21 at 4 08 44 AM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/265b1b4a-e827-44d8-b003-bb0c57befdc5)

- Install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)

![Screen Shot 2023-12-21 at 4 31 50 AM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/6b62ab94-8f01-4ff8-8381-f330869689ef)

- Download and install the Rewrite Module (rewrite_amd64_en-US.msi)

![Screen Shot 2023-12-21 at 4 32 44 AM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/133cd9ae-5ce3-4906-b9a8-8308e7c1b9fa)

- Next we have to create a directory for PHP on the local hard drive (C:\PHP)
- Now go into Files Explorer
- This PC
- Windows(C:)
- Right click and create a new folder named "PHP"

![Screen Shot 2023-12-21 at 4 33 38 AM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/e5c550a5-9278-4ad3-8b80-bfa4cc39d9f0)

- Right click and choose "Extract all"
- Unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into C:\PHP folder

![Screen Shot 2023-12-21 at 4 35 43 AM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/daefb105-c3c5-4769-b3dc-ca6ecbd28ba5)

- Download and install VC_redist.x86.exe from the installation files

![Screen Shot 2023-12-21 at 4 39 23 AM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/e562b55b-9f7e-47bc-9c72-7fea9aa614dc)

 - Next, just like the last step, install MySQL 5.5.62 (mysql-5.5.62-win32.msi) from the installation files

![Screen Shot 2023-12-21 at 4 44 15 AM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/966844c6-a3fa-42c7-9d37-21eb5a0d38bc)
  
  - While installing, choose "Typical" as the Setup Type
  - Launch Configuration Wizard (after installation)
  - Standard Configuration

![Screen Shot 2023-12-21 at 4 45 33 AM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/a4a6f15d-4f84-4f85-be6c-151616714f79)

  - Install as Windows Service
  - Create root password
  - Execute then click Finish

**Currently installing database on actual computer to store application data (ex. tickets)**

![Screen Shot 2023-12-21 at 4 51 04 AM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/f14c32db-119b-4980-8f48-581859d08286)

 - Open IIS as an Administrator using the right click

![Screen Shot 2023-12-21 at 4 53 56 AM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/446f5805-2194-409a-b0f4-a2ad47999bfb)

 - Double click PHP Manager
 - Then choose "Register new PHP version"
 - Browse and choose the file PHP-CGI in C:\PHP folder

![Screen Shot 2023-12-21 at 4 56 52 AM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/e66685d9-3feb-4b51-805b-10d85ccebf21)

 - Click Open
 - Hit OK
 - On the left hand side inside IIS Manager, click on the name of the server then restart

![Screen Shot 2023-12-21 at 4 58 54 AM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/e7413f8a-ee87-4a57-bf85-bc94c57b0b9c)

 - Install osTicket v1.15.8 from installation files
 - Extract and copy the Upload folder into c:\inetpub\wwwroot (web servers main folder)

![Screen Shot 2023-12-21 at 5 41 37 AM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/7bcc5396-b992-41e0-9950-574c1828c3ad)

 - Within C:\inetpub\wwwroot, rename “upload” to “osTicket”

![Screen Shot 2023-12-21 at 5 42 29 AM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/50f80c8b-dda5-4c51-8e8c-326472d71573)

- Go to IIS Manager
- Click restart just like in previous step  
- Then expand "Sites" on the left hand side
- Expand Default Web Site
- Open osTicket
- On the right click "Browse *:80 (http)"

![Screen Shot 2023-12-21 at 5 46 36 AM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/21c8fd2d-a067-4be5-af20-28511b90a19b)

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
