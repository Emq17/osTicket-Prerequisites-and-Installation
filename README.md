<p align="center">
<img src="https://i.imgur.com/C6MnrDC.png" alt="Logo"/>
</p>

<h1 align="center">Prerequisites and Installation</h1>

This step-by-step walkthrough is designed to help provide a detailed framework guiding you through the essential prerequisites & installation process of the open-source help desk ticketing system known as "osTicket."<br />

<h2>Environments and Technologies</h2>

- Microsoft Azure
- Microsoft Remote Desktop (Mac)
- Internet Information Services (IIS) (Web server osTicket runs on)
- osTicket

<h2>Operating Systems Used </h2>

- Windows 10 (22H2)

<h2>List of Prerequisites</h2>

- Installation Files https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6
- MySQL
- PHP Manager
- HeidiSQL
- Rewrite Module (Requirement for osTicket to work)
- Microsoft Visual C++

<h2>Installation Steps</h2>

- Please refer to https://github.com/Emq17/Establishing-Virtual-Machines-With-Remote-Desktop to set up your VM.
  - Apply 2-4 Virtual CPU's & allow it to create a new Virtual Network (Vnet).
  - Use Windows 10 (22H2) for your "image"
- Once we are logged into your Virtual Machine, install and enable IIS with Windows CGI:
  - Open up the Control Panel

![Screen Shot 2023-12-21 at 8 39 42 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/90a9a247-d4a6-4cf6-a975-210d4b9b0c55)

![Screen Shot 2023-12-21 at 8 40 18 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/c18e109c-aa4a-423c-a8c8-e030b5cf1a63)

  - Go to Programs

![Screen Shot 2023-12-21 at 8 40 38 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/e13ea526-0ee1-4cb9-915d-b871c46c02f3)

  - Under "Programs and Features", click "Turn Windows features on or off"

![Screen Shot 2023-12-21 at 8 41 27 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/bb0d2fbd-5828-4ebe-9ac6-c6a2b084d4d9)

  - Check the box & enable "Internet Information Services" then hit expand

![Screen Shot 2023-12-21 at 8 42 16 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/2312365d-882b-4d08-949a-f5fad6e05be2)

  - A dropdown should appear. Expand "World Wide Web Services" then "Application Development Features"
  - Check box to enable CGI then collapse dropdown for "Application Development Features"

![Screen Shot 2023-12-21 at 8 43 04 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/7aeac3cf-0f28-412e-8ddc-b346ec8994f5)

  - Expand "Common HTTP Features" & enable all by making sure every box is checked
  - Hit OK.

![Screen Shot 2023-12-21 at 8 44 59 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/ddfcea22-1170-44ce-a766-f08df22ca6d5)

- Installation of IIS should begin
- Once finished, test this by going to your browswer and typing in 127.0.0.1 (local host)
- You should be able to see the loaded default ISS website below and know that our web server is up and running

![Screen Shot 2023-12-21 at 4 08 44 AM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/265b1b4a-e827-44d8-b003-bb0c57befdc5)

- From the Installation Files, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)

![Screen Shot 2023-12-21 at 4 31 50 AM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/6b62ab94-8f01-4ff8-8381-f330869689ef)

- Then also download and install the Rewrite Module (rewrite_amd64_en-US.msi)

![Screen Shot 2023-12-21 at 4 32 44 AM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/133cd9ae-5ce3-4906-b9a8-8308e7c1b9fa)

- Next we have to create a directory for PHP on the local hard drive (C:\PHP)
- Go into Files Explorer
- This PC
- Windows(C:)
- Right click and create a new folder named "PHP"

![Screen Shot 2023-12-21 at 4 33 38 AM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/e5c550a5-9278-4ad3-8b80-bfa4cc39d9f0)

- Unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) from `Installation Files` (https://drive.google.com/file/d/1snNMtLdCOpMtkCyD4mvl9yOOmvVIp9fP/view) into C:\PHP folder
  - Go to Downloads Tab in File Explorer to find the file after installing
    - Right click and choose `Extract all`
    - Click `Browse` and navigate to the "PHP" folder that you created then click `Extract`
- This basically just dumps all the downloaded files into there

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
  - Create root password (don't have to check box)
  - Leave everything as is
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
  - Open an extra File Explorer window
  - Navigate to c:\inetpub\wwwroot folder
  - Simply drag and drop "upload" folder from the first window into the "wwwroot" folder in the new window
- It should begin extracting

![Screen Shot 2023-12-21 at 5 41 37 AM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/7bcc5396-b992-41e0-9950-574c1828c3ad)

- Once that finishes,
  - within C:\inetpub\wwwroot, rename “upload” to “osTicket”

![Screen Shot 2023-12-21 at 5 42 29 AM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/50f80c8b-dda5-4c51-8e8c-326472d71573)

- Go to IIS Manager
  - Click restart just like in previous step  
- Then expand "Sites" on the left hand side
- Expand Default Web Site
- Click osTicket
  - On the right side click "Browse *:80 (http)"

![Screen Shot 2023-12-21 at 5 46 36 AM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/21c8fd2d-a067-4be5-af20-28511b90a19b)

- Note that some extensions are not enabled

![Screen Shot 2023-12-21 at 7 25 36 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/33af2a40-a3d2-4ded-b211-8c7beed5b979)

- Go back to IIS (Sites/Default Web Site/osTicket)
- Click PHP Manager
- Find "Enable or diable an extension" at the bottom

![Screen Shot 2023-12-21 at 7 27 54 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/3ad03732-106b-4d16-9ad7-ff12882730de)

- Enable
  - "php_imap.dll"
  - "php_intl.dll"
  - "php_opcache.dll"


![Screen Shot 2023-12-21 at 7 29 36 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/76eb7776-10cd-4dc1-a6b8-29a0dcd570f3)

![Screen Shot 2023-12-21 at 7 31 11 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/d3d4b345-78d6-4937-bb6e-c99c118bc6d7)

![Screen Shot 2023-12-21 at 7 32 00 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/4c6005da-0621-4594-962a-22d29db191a3)

- Note that some extensions below are now enabled

![Screen Shot 2023-12-21 at 7 35 30 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/ac3f4a74-72e3-4772-8f2c-fc9e8b6643c0)

- Next thing we're going to do is go to File Explorer
- C:\inetpub\wwwroot\osTicket
- Open "include" folder
- Find "ost-sampleconfig.php"
- Change the file name to "ost-config.php"

![Screen Shot 2023-12-21 at 7 37 20 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/b29f40c6-32be-46ff-92b6-a089ce594bfc)

- Next we will set permissions on this so everyone has the ability to do anything they want to this file
- Right click the file
- Click "Properties"
- "Security" then "Advanced" near the bottom
- Disable Inheritance

![Screen Shot 2023-12-21 at 7 40 02 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/5889320b-4d2e-48f7-a047-65ee0ea7a818)

- Choose "Remove all inherited permissions from this object"

![Screen Shot 2023-12-21 at 7 41 16 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/ad87ad22-ec57-4263-b2b8-18ba6acbc083)

- Click "Add" then "Select a principle"
- Type out "Everyone" then Check Names
- Hit "OK"

![Screen Shot 2023-12-21 at 7 42 21 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/3340df81-2d14-4f7c-8845-73e013f998ea)

- Check all boxes for "Basic permissions:"
- Hit "Ok"
- Then "Apply", "Ok", and "Ok"


![Screen Shot 2023-12-21 at 7 43 03 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/a66b3fda-8a45-4655-a6b5-d5ef00fa52b3)

- Finish completing all Basic Installation Information in osTicket browser up until the Database Settings
- I recommending taking note of everything in case you'll need it for later
  
![Screen Shot 2023-12-21 at 7 47 56 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/a91d00d8-f3ad-48b4-93c3-3e6403d14cd6)

- Before continuing, we must setup our database 
- Install "HeidiSQL" from the installation files (this actually allows us to connect to the SQL server)
- Open Heidi SQL (this is what we call a database client which lets you connect to the database and lets you interact with it)

![Screen Shot 2023-12-21 at 7 58 01 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/4a9e91a3-e0b0-477b-a1f2-78493dc099dc)

- Create a new session

![Screen Shot 2023-12-21 at 7 59 43 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/752eac6d-747e-4765-97a2-e1d67f279044)

- User: root
- Password: Password1
- Click "Open"
- Now we have our connection to mySQL server

![Screen Shot 2023-12-21 at 8 01 51 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/e3447dca-0626-413f-bbd3-f0797e594d7e)

![Screen Shot 2023-12-21 at 8 04 14 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/66174947-bda9-4bc8-9071-2105df86f310)

- Create a database called "osTicket" inside of "HeidiSQL"

![Screen Shot 2023-12-21 at 8 06 26 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/02a45270-b804-4bfc-bb07-7e0ced7ead8b)

![Screen Shot 2023-12-21 at 8 06 51 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/8a6de39c-bb01-4363-b918-07336e03d231)


- Finish setting things up in the last part of the browsers Database Settings
- MySQL Database: osTicket
- MySQL Username: root
- MySQL Password: Password1
- Click "Install Now"

![Screen Shot 2023-12-21 at 9 19 44 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/98eba0ce-ea69-4568-988c-2cbe8578c447)

- You've successfully installed osTicket

![Screen Shot 2023-12-21 at 8 10 28 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/ba946ce7-de30-48ef-a77a-215dd12aa8eb)

- To conclude things, lets clean things up
- Delete the "Setup" folder at C:\inetpub\wwwroot\osTicket\Setup

![Screen Shot 2023-12-21 at 8 14 59 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/8d2236a7-8505-4a32-9b0c-37d4a7c265f5)

- Set Permissions to "Read & execute" and "Read" only at C:\inetpub\wwwroot\osTicket\include\ost-config.php

![Screen Shot 2023-12-21 at 8 17 01 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/9a50c04a-3358-41d1-a2ab-c5a6fedc2ab0)

- Go to "Properties"

![Screen Shot 2023-12-21 at 8 18 05 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/56787138-4fe5-437a-adcd-73c7efd83bd0)

- Go to "Security"

![Screen Shot 2023-12-21 at 8 18 46 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/8f84edbe-43c3-4ce7-a2d1-7fb18640e440)

- Go to "Advanced"
- Click to highlight "Everyone"
- Hit "Edit"
- Uncheck everything except "Read & execute" and "Read"
- Click "Ok", "Apply", then "OK"
  
![Screen Shot 2023-12-21 at 8 19 46 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/33fed67c-4802-4665-9d3f-36401c7935b1)


- Congratulations. Your intitial installation of osTicket is now complete
- Use these URL links to:
  - Log in as an Admin to do Administrative Tasks: http://localhost/osTicket/scp/login.php
  - Or log in as en End User to actually create tickets: http://localhost/osTicket/
  
  ![Screen Shot 2023-12-21 at 8 25 17 PM](https://github.com/Emq17/osTicket-Prerequisites-and-Installation/assets/147126755/c03d015c-9a93-44f7-a824-d936a43b0d5b)














