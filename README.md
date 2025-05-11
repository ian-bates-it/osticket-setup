# osTicket Setup


<p align="center">
<img src="https://github.com/user-attachments/assets/046c7817-d6d6-462e-a48e-11ae3efd9ba1" height="30%" width="30%"/>
</p>

<br />
<br />


---

## Install osTicket Software

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


<h2>Create the directory C:\PHP</h2>



