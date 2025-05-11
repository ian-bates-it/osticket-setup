# osTicket Setup


<p align="center">
<img src="https://github.com/user-attachments/assets/8cf1eaae-fbac-49a4-bbbb-11c28e64aa98" height="30%" width="30%"/>
</p>

<!--
https://github.com/user-attachments/assets/046c7817-d6d6-462e-a48e-11ae3efd9ba1
-->

---

## Install osTicket Software


- The installation files at this download link were aggregated from the osTicket Documentation. (16:38)

<br />
<br />

## Enable IIS

<br />
<br />


---



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


<h2>Create A Directory called `PHP` on the C Drive (`C:\PHP`)</h2>

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

- CLick the `Install` button as shown below.

  <img src="https://github.com/user-attachments/assets/2eb69b21-2d20-4da7-a638-843f88832fa7" height="50%" width="50%" />


<h4>MySQL Server Installation Complete</h4>

- Click the `Finish` button to complete the process as shown below.

  <img src="https://github.com/user-attachments/assets/f25efa5f-7392-42cc-8080-a8147fd9cb26" height="50%" width="50%" />


---
---
<br />
<br />


<h2>Next Step </h2>




