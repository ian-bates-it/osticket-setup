<!--
Duplicate Register New PHP version in IIS Manager
![image](https://github.com/user-attachments/assets/a65a9ecd-81c1-4cdb-8c43-285025bbcf9d)
-->

# osTicket Setup


<p align="center">
<img src="https://github.com/user-attachments/assets/8cf1eaae-fbac-49a4-bbbb-11c28e64aa98" height="30%" width="30%"/>
</p>

This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<!--
https://github.com/user-attachments/assets/046c7817-d6d6-462e-a48e-11ae3efd9ba1
-->

---

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)


<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)


---

## List of Prerequisites


- The installation files at this download link were aggregated from the osTicket Documentation.
    - Download link: [https://tinyurl.com/osticket-files](https://tinyurl.com/osticket-files)

- The installation files are in a folder called `osTicket-Installation-Files`
  - Mcirosoft Visual C++ Redistributable (x86) (`VC_redist.x86.exe`)
  - IIS URL Rewrite Module 2 (`rewrite_amd64_en-US.msi`)
  - PHP Manager For IIS (`PHP ManagerForIIS_V1.5.0.msi`)
  - PHP version 7.3.8 (`php-7.3.8-nts-Win32-VC15-x86.zip`)
  - osTicket Software version 1.15.8 (`osTicket-v1.15.8.zip`)
  - MySQL version 5.5.62 (`mysql-5.5.62-win32.msi`)
  - HeidiSQL (`HeidiSQL_12.3.0.6589_Setup.exe`)

<br />
<br />

  <img src="https://github.com/user-attachments/assets/05f8e974-c85b-4ff3-a621-183de6d796f0" height="50%" width="50%" />

<br />


<h2>Table of Contents</h2>

1. <a href="https://github.com/ian-bates-it/osticket-setup?tab=readme-ov-file#enable-iis">Enable IIS</a>
2. <a href="https://github.com/ian-bates-it/osticket-setup?tab=readme-ov-file#install-php-manager-for-iis">Install PHP Manager for IIS</a>
3. <a href="https://github.com/ian-bates-it/osticket-setup?tab=readme-ov-file#install-the-iis-url-rewrite-module">Install IIS URL Rewrite Module 2</a>
4. <a href="https://github.com/ian-bates-it/osticket-setup?tab=readme-ov-file#install-the-iis-url-rewrite-module">Install IIS URL Rewrite Module 2</a>
5. x
6. x
7. x
8. 





## Enable IIS (Internet Information Services)

- To enable IIS, follow the steps outlined below.

---
<br />

<h3>Control Panel > Programs</h3>

- Navigate to the Control Panel and then click on `Programs`
- THen click on `Turn Windows features on or off` as shown below.

  <img src="https://github.com/user-attachments/assets/ff1c23c2-c0bc-4d58-8c8f-4f1ee657b5f7" height="70%" width="70%" />


---
<br />

<h3>Windows Features</h3>

- In the `Windows Features` view, scroll down and check `Internet Information Services`
      - Then open the view for `World Wide Web Services`
          - Then open up the view for `Application Development Features
              - Then select the check box for `CGI` as shown below.


  <img src="https://github.com/user-attachments/assets/bb451488-3c3e-45d4-aa5f-355355e97633" height="50%" width="50%" />


---

<br />
<br />

- Now Windows has enabled the Internet Information Services (IIS) has been enabled with `CGI`.

  ![image](https://github.com/user-attachments/assets/7fa8e6ba-c8dd-4c6d-b2c2-63c503b2f4ea)

<br />
<br />

- In a browser, we can confirm IIS is running by visiting our loopback address of `127.0.0.1`.
- We can see the default IIS landing page as shown below.

  <img src="https://github.com/user-attachments/assets/8f7278ae-c8e2-40b6-a91f-becfa5681d2e" height="60%" width="60%" />


---
<br />

<h3>View the IIS Configration File</h3>

1. Search for Notepad. Right-click `Notepad`
2. Select `Run as administrator`

  <img src="https://github.com/user-attachments/assets/266352d9-5774-489c-b454-417f10da1385" height="40%" width="40%" />


<br />
<br />

3. In Notepad, select `File` and then `Open`.

  <img src="https://github.com/user-attachments/assets/24df72ab-f330-496c-b76a-430729d3e128" height="40%" width="40%" />


<br />
<br />

4. Navigate to `This PC > Windows (C:) > inetpub > wwwroot` and double-click the `iisstart` file of type `Microsoft Edge HTML Document`.
   - Change the format from the default `.txt` to `All Files`. 
   - This is kind of of like the `index.html` on a typical web server. 

  <img src="https://github.com/user-attachments/assets/5199f557-01df-4513-9f96-83f1aac90ecf" height="60%" width="60%" />

<br />
<br />

This is the actual HTML code for the default IIS homepage which appears when we visit `127.0.0.1`:

  <img src="https://github.com/user-attachments/assets/a20c2237-19a2-46b8-8ada-323f0a99784e" height="80%" width="80%" />


<br />
<br />



---
---
<br />
<br />


<h2>Install PHP Manager for IIS</h2>

- PHP is a backend web server language.
- osTicket runs on PHP, so we have to intsall PHP to use osTicket.


<br />
<br />
<h3>Run `PHPManagerForIIS` In Our osTicket Installation Files</h3>

- In the osTicket-Installation-Files we previously downloaded above, double click the `PHPManagerForIIS_V1.5.0.msi` installer file as shown below.

<br />

  <img src="https://github.com/user-attachments/assets/48b7a267-48ed-4ffc-b0f6-0371c4083459" height="60%" width="60%" />


<br />
<br />
<h3>Run the PHP Manager For IIS Setup Wizard</h3>

- Use the Setup Wizard to install PHP Manager for IIS.
- Click `Next` on the first screen as shown below.


  <img src="https://github.com/user-attachments/assets/f3bee25f-1f6d-4c06-a228-6a9c87a19dfc" height="40%" width="40%" />



<br />
<h4>Accept the MIT License</h4>

  <img src="https://github.com/user-attachments/assets/ac0f1a7d-2c6b-4df7-8ab5-525a1a99482a" height="40%" width="40%" />



<h4>Accept the UAC notice</h4>

  <img src="https://github.com/user-attachments/assets/fa783188-cfa2-43e8-890d-ed36f0f731c2" height="40%" width="40%" />


<br />


<h4>PHP Manager for IIS Installation Completed</h4>

- Click `Close` to complete the process.

  <img src="https://github.com/user-attachments/assets/5e9d98ce-9850-451b-913c-5f075706969a" height="40%" width="40%" />





---
---
<br />
<br />


<h2>Install the IIS URL Rewrite Module</h2>

- From the installation file, double-click the IIS URL Rewrite Module installer, named `rewrite_amd64_en-US.msi`, as shown below.

<br />
  <img src="https://github.com/user-attachments/assets/41793b4b-7792-48bd-9de6-a0247b474ea3" height="60%" width="60%" />


<br />
- Accept the terms of the License Agreement.
- Click the `Install` button as shown below.


<br />
  <img src="https://github.com/user-attachments/assets/9c552bdf-ca9c-4588-9c50-75d7ccbbcece" height="50%" width="50%" />


<h4>IIS URL Rewrite Module Completed</h4>

- After the installation is complete, select the `Done` button to complete the process as shown below.

<br />
  <img src="https://github.com/user-attachments/assets/b0b69e1b-a998-40d7-be19-3cc896b89631" height="50%" width="50%" />




---
---
<br />
<br />


<h2>Install `PHP` Version 7.3.8 on the C Drive (`C:\PHP`)</h2>

- Create a new directory on the C Drive named `PHP`

  <img src="https://github.com/user-attachments/assets/c949e470-bf03-4f25-abd0-5213f13f272c" height="50%" width="50%" />

<br />
<br />

- Extract the zipped PHP file `php-7.3.8-nts-Win32-VC15-x86.zip` to our new `C:\PHP` directory
- This will download the binaries and files required for PHP.

  <img src="https://github.com/user-attachments/assets/65081e12-2ee0-4487-9f7a-7a296bea0b07" height="50%" width="50%" />




---
---
<br />
<br />


<h2>Install C++ Distributable `VC_redis.x86.exe` </h2>

- This is another requirement for osTicket.


- Double-click the `VC_redis.x86.exe` installation file.
- Agree to the license terms and conditions
- Click the `Install` button as shown below.

  <img src="https://github.com/user-attachments/assets/0922d4f5-e0d3-4611-99c7-efc37e185028" height="70%" width="70%" />

<br />
<br />
- Let the installation run and then click `Close` after the installation is successfully completed as shown below.


  <img src="https://github.com/user-attachments/assets/36610a14-11f7-4338-83ff-f88187d231a6" height="50%" width="50%" />




---
---
<br />
<br />


<h2>Install MySQL version 5.5.62 `mysql-5.5.62-win32.msi` </h2>

- This is another requirement for osTicket.
- This will store all the ticketing accounts on the back end.



- Double-click the `mysql-5.5.62-win32.msi` installation file.
- In the `MySQL Server Setup Wizard`, click the `Next` button


  <img src="https://github.com/user-attachments/assets/56a42cf5-57c3-4bf4-a869-1e1f43d9f10c" height="50%" width="50%" />


<br />
<br />

<h4>Accept the GNU Public License</h4>

- Accept the GNU license and click the `Next` button


  <img src="https://github.com/user-attachments/assets/d0f077f9-cc29-4643-aa1d-4359083039ae" height="50%" width="50%" />

<br />
<br />


<h4>Select Typical Setup Type</h4>

- Select the `X` Setup Type button as shown below.


  <img src="https://github.com/user-attachments/assets/f330fe06-4fa0-410e-8d28-b310884bf808" height="50%" width="50%" />


<br />
<br />

<h4>Install</h4>

- Click the `Install` button as shown below.

  <img src="https://github.com/user-attachments/assets/2eb69b21-2d20-4da7-a638-843f88832fa7" height="50%" width="50%" />


<h4>MySQL Server Installation Complete</h4>

-Click the box for `Launch the MySQL Instance Configuration Wizard`, so we can open up the MySQL Instance Configuration Wizard Next.
- Click the `Finish` button to complete the process as shown below.

  <img src="https://github.com/user-attachments/assets/aac12976-1031-48e7-af1a-115fcafa9de5" height="50%" width="50%" />



<br />

- Accept the `MySQLInstanceConfig.exe` UAC

  <img src="https://github.com/user-attachments/assets/d0e4bbb9-844d-4f04-b93b-876c70a6e45c" height="50%" width="50%" />



<br />
<br />

---

<h3>MySQL Server Instance Configuration Wizard </h3>

- Click `Next` on the MySQL Server Instance Configuration Wizard.

  <img src="https://github.com/user-attachments/assets/5c5963c2-05dc-44cc-8c00-26b923fb90db" height="50%" width="50%" />



<br />
<br />

---

<h3>Select `Standard Configuration` </h3>

- Select the `Standard Configuration`. 

  <img src="https://github.com/user-attachments/assets/eda2a0d7-6939-4541-b4ac-dbb435501f07" height="50%" width="50%" />



<br />
<br />

---

<h3>Install As Windows Servce</h3>

- Go with the default options here.
- Click `Next`.


  <img src="https://github.com/user-attachments/assets/94c7d615-1afe-4aa1-bd45-127351956a39" height="50%" width="50%" />



<br />
<br />

---

<h3>Set MySQL Root Password in MySQL</h3>

- Enter in a root password and confirm the password by entering it twice.
- Click `Next`.

  <img src="https://github.com/user-attachments/assets/34522c28-140f-4afe-aa08-e873894206e7" height="50%" width="50%" />

<br />
<br />

---

<h3>Execute</h3>

- Click the `Execute` button.

  <img src="https://github.com/user-attachments/assets/3ebe42e9-215f-437b-bab8-c53334c04cde" height="50%" width="50%" />


<br />
<br />

---

<h3>MySQL Installation Completed</h3>

- Click the `Finish` button.

  <img src="https://github.com/user-attachments/assets/3c89cf17-7ac1-4043-818f-1ed1a8a5773e" height="50%" width="50%" />



---
---
<br />
<br />


<h2>Open IIS Manager As Admin </h2>

- We need to let IIS know the location of PHP on the Windows 10 client VM. (`C:\PHP`)

1. Search for `IIS`
   - This should return `Internet Information Services (IIS) Manager`
2. Select `Run as Administrator` as shown below.

  <img src="https://github.com/user-attachments/assets/8d4739fa-260e-476e-ac37-e68161f9eec0" height="60%" width="60%" />




<br />
<br />

---

<h3>Open PHP Manager</h3>

- Double-click the icon for `PHP Manager` to open it.

  <img src="https://github.com/user-attachments/assets/0fa6d3d8-f989-460c-bd28-d35a4beb056c" height="60%" width="60%" />


<br />
<br />

---

<h3>Register New PHP Version</h3>

- Click the link `Register new PHP version` as shown below.

  <img src="https://github.com/user-attachments/assets/990ef674-3dc7-472f-97c3-207456479b5c" height="60%" width="60%" />


<br />
<br />



1. Select button with three dots
2. Navigate to `C:\PHP` 
3. Select the PHP executable file (`php-cgi.exe`) 
4. Click the `Open` button


  <img src="https://github.com/user-attachments/assets/eff99b58-22aa-4c1f-895d-703aca9114ab" height="60%" width="60%" />

<br />
<br />
<br />


5. Click `OK` to confirm the path to the php executable file (`C:\PHP\php-cgi.exe`) as shown below.

  <img src="https://github.com/user-attachments/assets/d9cf67a7-6c11-4a4a-9905-6537d767183c" height="40%" width="40%" />



---
---
<br />
<br />


<h2>Reload IIS (Open, Stop and Start the IIS Server)</h2>

- In the right-hand column of IIS Manager, follow the steps below to stop and start the ISS Server.

1. Select `Stop`.
2. Select `Start` as shown below.

  <img src="https://github.com/user-attachments/assets/aff2ed86-f117-45ed-97af-ddec90a78de4" height="60%" width="60%" />






---
---
<br />
<br />


<h2>Unzip the osTicket Software To `C:\inpetpub\\wwwroot`</h2>


1. In our osTicket-Installation-Files directory, right-click the `osTicket-v1.15.8.zip` file.
2. Select `Extract All` as shown below.

  <img src="https://github.com/user-attachments/assets/8a7c1a63-6a74-4c91-b7fa-2db868adf46a" height="50%" width="50%" />



<br />
<br />
<br />

3. Select `C:\inpetpub\\wwwroot`as the destination folder for the osTicket extracted files as shown below.
   - Press the `Extract` button to complete this process.


  <img src="https://github.com/user-attachments/assets/fcb85738-3d59-4bbf-9e09-3b53ee00c12e" height="50%" width="50%" />


<br />
<br />
<br />

---

<h3>Rename Upload Folder to `osTicket`</h3>

4. In the `C:\inpetpub\\wwwroot` directory, right-click the `upload` folder.
5. Select `Rename`as shown below. 

  <img src="https://github.com/user-attachments/assets/d94ff271-e1f2-4e54-8dfc-a782dfdc1f61" height="50%" width="50%" />


<br />
<br />
<br />

6. Name the folder `osTicket` as shown below.

  <img src="https://github.com/user-attachments/assets/33cd9d07-a180-445b-9484-284b1fee49a6" height="40%" width="40%" />



<br />
<br />

---

<h2>Reload IIS (Open, Stop and Start the IIS Server)</h2>

- After making a change to the `C:\inpetpub\\wwwroot` directory, we will reload the IIS Server again as shown below.
- In the right-hand column of IIS Manager, follow the steps below to stop and start the ISS Server.

1. Select `Stop`.
2. Select `Start` as shown below.

  <img src="https://github.com/user-attachments/assets/aff2ed86-f117-45ed-97af-ddec90a78de4" height="60%" width="60%" />




<br />
<br />

---

<h2>Browse Port 80 (`http`) in IIS Manager</h2>

**In the left-hand menu in ISS Manager**
- - Go to sites
    - Default
        - osTicket
            - On the right-hand column, click `Browse *:80` as shown below.

<br />
<br />

1. Navigate to `Sites > Default Web Site > osTicket` in the left-hand column of IIS Manager. 
2. Click on the `Browse *:80 (http)` link in the right-hand column of ISS Manager as shown below.

  <img src="https://github.com/user-attachments/assets/07488ce8-10e0-4a21-93a6-11f9c8ad34b5" height="60%" width="60%" />

<br />
<br />
<br />

3. View the default osTicket landing page in the Edge Browser. (`localhost/osTIcket/setup`)

  <img src="https://github.com/user-attachments/assets/d56c343b-d3db-47d2-b722-4c665d8ea251" height="60%" width="60%" />





---
---
<br />
<br />


<h2>Enable Missing Extensions For osTicket</h2>

- osTicket provides a list of extensions which are not yet enabled on the default landing page (`localhost/osTIcket/setup`) and shown below.

  <img src="https://github.com/user-attachments/assets/d87a6bc3-626a-4391-bcf6-062b8be73140" height="50%" width="50%" />

<br />
<br />

**We will enable these three extensions as shown below**
1. Enable IMAP extension (`php_imap.dll`).
2. Enable Internationalization extension (`php_intl.dll`).
3. Enable OP Cache extension (`php_opcache.dll`).



<br />
<br />
<br />

---

<h3>Enable Extensions in osTicket Home View in IIS Manager</h3>

1. Navigate to the osTicket Home view in IIS Manager by going to `Sites > Default Web Site > osTicket`.
2. Double-click the PHP Manager icon as shown below.

  <img src="https://github.com/user-attachments/assets/bdd0ae9b-cfce-4199-acf0-052f3c78a283" height="60%" width="60%" />


<br />
<br />
<br />

3. Click on the `Enable or disable an extension` link in PHP Manager as shown below.

  <img src="https://github.com/user-attachments/assets/2c9fcd13-ad97-4570-9a92-f3aef8493031" height="60%" width="60%" />


<br />
<br />
<br />

<h4>Enable PHP IMAP (`php_imap.dll`)</h4>

4. Enable PHP IMAP by right-clicking on `php_imap.dll` in the disabled list and selecting `Enable` as shown below.


  <img src="https://github.com/user-attachments/assets/c8bc0e9d-645c-44bb-972b-8fde32a3c3d1" height="60%" width="60%" />

<br />
<br />
<br />


<h4>Enable PHP Internationalization extension (`php_intl.dll`)</h4>

5. Enable PHP IMAP by right-clicking on `php_intl.dll` in the disabled list and selecting `Enable` as shown below.

  <img src="https://github.com/user-attachments/assets/bf4d03ab-d23b-4d94-9f33-223bd038a2ba" height="60%" width="60%" />



<br />
<br />
<br />


<h4>Enable PHP OP Cache extension (`php_opcache.dll`)</h4>

6. Enable PHP OP Cache by right-clicking on `php_opcache.dll` in the disabled list and selecting `Enable` as shown below.

  <img src="https://github.com/user-attachments/assets/e0d02d9f-c55d-48a6-9b1b-0c600f58dc4a" height="60%" width="60%" />


<br />
<br />

- In our Edge tab, we can refresh the osTicket setup page (`localhost/osTIcket/setup`) to see that our desired extensions have been enabled.

  <img src="https://github.com/user-attachments/assets/0ea0604c-78ac-4ce9-bde9-3d5a2727c7c5" height="50%" width="50%" />






---
---
<br />
<br />


<h2>Rename `ost-sampleconfig.php` to `ost-config.php`</h2>


1. In File Explorer, navigate to `C:\inetpub\wwwroot\osTicket\include`
2. Right-click on `ost-sampleconfig.php`
3. Select `Rename` as shown below.

  <img src="https://github.com/user-attachments/assets/c671294f-24b8-4311-9f16-c29c06bf4396" height="60%" width="60%" />


<br />
<br />

Now our file has been changed to `ost-config.php`

  <img src="https://github.com/user-attachments/assets/264bc34c-0e11-470e-83c4-eb83606ad469" height="60%" width="60%" />





---
---
<br />
<br />


<h2>Assign Desired Permissions To `ost-config.php`</h2>

- We have to assign permissions to `ost-config.php` to allow osTicket to be able to make changes to this file on the backend.
- To do so, follow these steps.


1. Right-click `ost-config.php`.
2. Select `Properties`.

  <img src="https://github.com/user-attachments/assets/e22d4285-a3f7-4acb-aac5-cc0663e89125" height="40%" width="40%" />



<br />
<br />
<br />


3. In the `ost-config.php Properties` dialog box, select `Security Tab`.
4. Then click the `Advanced` button as shown below.

  <img src="https://github.com/user-attachments/assets/cd482b1b-c2fd-4db7-b052-86633d670d9d" height="40%" width="40%" />


<br />
<br />
<br />


5. We want to disable inheritance to strip all the current permissions away. To do this, click the `Disable inheritance` button

  <img src="https://github.com/user-attachments/assets/a5493f1d-191c-4d33-a710-07145e489995" height="50%" width="50%" />

<br />
<br />
<br />


6. In the pop-up window, select the option to `Remove all inherited permissions from this objet` as shown below.

  <img src="https://github.com/user-attachments/assets/25ed0edc-5ae8-4a20-938b-a33388f83ff6" height="40%" width="40%" />

<br />
<br />
<br />


7. Now we have removed all inherited permissions from `ost-config.php` and we are ready to assign our desired permissions to `ost-config.php` by clicking the `Add` button as shown below.

  <img src="https://github.com/user-attachments/assets/641e8e03-bfa7-49ca-addb-bf5c47aee87b" height="40%" width="40%" />


<br />
<br />
<br />


8. Click the `Select a principal` link as shown below. 

    <img src="https://github.com/user-attachments/assets/bc2c6a2c-3a3f-4e35-b935-98f54b54f444" height="50%" width="50%" />


<br />
<br />
<br />


9. Add `Everyone` to the `Enter the object name to select` field. 
    - ONLY FOR TESTING PURPOSES. 
    - We would not do this in a production environment. 
10. Click the `Check Names` button to confirm. 
11. Click `OK` button

    <img src="https://github.com/user-attachments/assets/4c3024a8-a421-4c67-a2dc-917f73595f64" height="50%" width="50%" />


<br />
<br />
<br />


12. Finally, in the Permission Entry for `ost-config.php` Dialog Box, select `Full Control` as the Basic permissions settings as shown below.
    - This will automatically select all the other permission check boxes since we are granting full control. 
13. Press the `OK` button to save our changes. 


    <img src="https://github.com/user-attachments/assets/117ce8bf-a556-45f3-b457-fb9396efd662" height="50%" width="50%" />


<br />
<br />



<h4>Advanced Security Settings for ost-config.php</h4>

- The final settings for `ost-config.php` for testing purposes only, has granted Everyone full control as shown below.
- osTicket has full control to the configuration file. (32:23)

14. To apply our changes, click the `Apply` button
15. Finally, click the `OK` button to complete this process as shown below. 

    <img src="https://github.com/user-attachments/assets/e54ab8f0-a15c-45b6-84cb-5974b413ab79" height="50%" width="50%" />





---
---

<br />
<br />

---

<h2>HeidiSQL Setup</h2>

- Heidi SQL is an application that allows us to make a connection to our database and configure it. 

- In our `osTicket-Installation-Files` folder, click on the Heidi SQL installer file (`HeidiSQL_12.3.0.6589_Setup.exe`) as shown below. 

    <img src="https://github.com/user-attachments/assets/a53766db-e11a-46de-85da-b8a7065018c2" height="50%" width="50%" />


<br />
<br />

- Click `Yes` to the HeidiSQL Setup UAC notification

    <img src="https://github.com/user-attachments/assets/e7d15551-b373-41ee-a8a7-5feeb3b89503" height="30%" width="30%" />



<br />
<br />


- Accept the License Agreement
- Click `Next`

    <img src="https://github.com/user-attachments/assets/51149da6-3874-4b98-831b-0ce21cb53819" height="40%" width="40%" />



<br />
<br />
<br />


- Accept default installation location (`C:\Program Files\HeidiSQL`). Click `Next`.

    <img src="https://github.com/user-attachments/assets/5f4bb0eb-1bd4-4927-ba75-e8c0e425b9d6" height="40%" width="40%" />



<br />
<br />
<br />


- Accept the rest of the default options.
- Then click `Install` to complete this process.

    <img src="https://github.com/user-attachments/assets/cce3e789-9eff-4711-8b21-14bfbacd3c58" height="40%" width="40%" />


<br />
<br />
<br />

- Click the button to `Launch HeidiSQL`.
- Click the `Finish` button. 

    <img src="https://github.com/user-attachments/assets/79bf8e49-6735-4c94-a54d-2ac1be267cee" height="40%" width="40%" />



<br />
<br />
<br />


---

<h3>HeidiSQL Session Manager</h3>

- With HeidiSQL, we are going to make a connection to our database.
- In the `HeidiSQL Session Manager` select the `New` button as shown below.

    <img src="https://github.com/user-attachments/assets/2fef0469-b012-4533-a8c5-3cc2dc46fd93" height="40%" width="40%" />


<br />
<br />


---

<h3>Enter MySQL credentials</h3>

- In the HeidiSQL Settings, enter the [MySQL root username and password that we set up above at this link.](https://github.com/ian-bates-it/osticket-setup/blob/main/README.md#set-mysql-root-password).
- Then click `Open` as shown below.

    <img src="https://github.com/user-attachments/assets/39210cc9-2451-4d3a-a9c8-14c950e2e507" height="50%" width="50%" />




<br />
<br />


---

<h3>We Opened A Connection Between HeidiSQL and our MySQL Database</h3>

- We created a new session between HeidiSQL and our MySQL database.
- We connected to that session.



<br />
<br />


---

<h3>Create a Database called `osTicket` in HeidiSQL</h3>

1. Right-click the `Unnamed` 
2. Select `Create new`
3. Select `Database` as shown below.

    <img src="https://github.com/user-attachments/assets/08c4faf1-408a-4f82-b468-bfb7ce0e7af7" height="60%" width="60%" />



<br />
<br />

4. Name the new database `osTicket`
5. Click `OK` as shown below.

    <img src="https://github.com/user-attachments/assets/870374be-4add-4fdc-b963-135ed339443c" height="40%" width="40%" />

<br />
<br />

---

<h4>Empty `osticket` database</h4>

- We have an empty database called `osticket` now.

    <img src="https://github.com/user-attachments/assets/6e103456-5d23-4231-8d01-7d42c8373033" height="40%" width="40%" />


The actual installation that is happening in the browser (osTicket edge) is going to make use of this empty database we created in HeidiSQL. (36:15)






<br />
<br />

---







---
---
<br />
<br />


<h2>Setup osTicket Installer via browser at `localhost/osTIcket/setup`</h2>

- In the edge browser at the address `localhost/osTIcket/setup` we can complete the osTicket installation process by clicking the `Continue >` button as shown below.

    <img src="https://github.com/user-attachments/assets/e2186525-b7e6-4102-b377-164bdbd5816a" height="60%" width="60%" />




<br />
<br />

---

<h3>osTicket System Settings</h3>

- Enter a `Helpdesk Name` and `Default Email`

    <img src="https://github.com/user-attachments/assets/5b081b4b-a593-4787-bf64-80aae9d875be" height="50%" width="50%" />



<br />
<br />

---

<h3>osTicket Admin User</h3>

- Enter a `First Name` and `Last Name` for the Admin User
- Enter an Admin User Email
   - Note that the email address must be different than the email used as the system default email.
- Create a `Username` that is at least 3 characters long.
- Create a `Password` and confirm your desired password as shown below.


    <img src="https://github.com/user-attachments/assets/d86685be-4832-4725-9ca8-9693f89bf31c" height="50%" width="50%" />




<br />
<br />

---

<h3>osTicket Database Settings</h3>

- We need to set up the credentials to log into our MySQL database which will handle our osTicket installation.


- Use the default values for **MySQL Table Prefix** (`ost_`).
- Use the default values for **MySQL Hostname** (`localhost`).

- MySQL Database name is the same database name [we created in the HeidiMySQL section above which you can view at this link.](https://github.com/ian-bates-it/osticket-setup/blob/main/README.md#create-a-database-called-osticket)
- In this example, that name was `osTicket` as shown below. 


    <img src="https://github.com/user-attachments/assets/c9a127a4-54df-4ad7-8887-884eac793989" height="70%" width="70%" />


<br />
<br />
<br />

- The **MySQL Username** and  **MySQL Password** is the same that [we set up in the MySQL setup section above which you can view at this link](https://github.com/ian-bates-it/osticket-setup/blob/main/README.md#set-mysql-root-password). 
- In this example, the username was `root`.

    <img src="https://github.com/user-attachments/assets/897ecde6-f1f3-4e6a-867e-5874642c671d" height="60%" width="60%" />

<br />
<br />
<br />


- Finally, click the `Install Now` button to start the `osTicket` installation process as shown below.

    <img src="https://github.com/user-attachments/assets/6672b0d8-b9dd-48e8-b942-b1ec6b808737" height="60%" width="60%" />



<br />
<br />

---

<h3>osTicket Successfully Installed!</h3>

- Confirmation from osTicket Installer should look something like this:

    <img src="https://github.com/user-attachments/assets/21c1beea-7e65-493f-9508-247b3c96982b" height="60%" width="60%" />



<br />
<br />

---

<h3>Check `osTicket` database in HeidiSQL</h3>

- Now when we refresh the `osticket` database in HeidiSQL, we can see the installation added many tables into our database as shown below.

    <img src="https://github.com/user-attachments/assets/b9586a84-b6f1-48a7-b149-200cfd12ad71" height="60%" width="60%" />





<br />
<br />

---

<h3>osTicket Installation is Complete</h3>

- The next step is the [osTicket Post Installation Setup which is oulined at this link](https://github.com/ian-bates-it/osticket-post-installation-setup).


