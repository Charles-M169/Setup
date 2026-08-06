<h1 id="top"> 🧪 Active Directory Lab Setup Guide (Oracle VirtualBox) </h1>

This is a step-by-step guide for building Active Directory lab from scratch using Oracle VirtualBox. I'll create two virtual machines: a Domain Controller (Windows Server 2025) and a Client Machine (Windows 10 Pro), configure them, join the domain, and get everything set up for hands-on Active Directory tasks.

---

## <h2 id="table-of-contents"> 🗂️ Table of Contents </h2>

- [⚙️ Oracle VirtualBox Installation](#Oracle-VirtualBox-installation)
- [Domain Controller (DC01)](#domain-controller-dc01)
  - [🛠️ Virtual Machine Setup](#virtual-machine-setup-dc01)
  - [💽 Windows Server 2025 Installation](#windows-server-2025-installation-dc01)
  - [🌐 Network and AD Configuration](#network-and-ad-configuration-dc01)
- [Client Machine (CLIENT01)](#client-machine-client01)
  - [🛠️ Virtual Machine Setup](#virtual-machine-setup-client01)
  - [💽 Windows OS Installation](#windows-os-installation-client01)
  - [🌐 Network Configuration](#network-configuration-client01)
  - [🧑‍💻 Join CLIENT01 to the Domain](#join-client01-to-the-domain)
- [✅ Final Check](#final-check)
- [📦 Wrapping Up](#wrapping-up)
- [🧠 Tips](#tips)
- [📦 What’s Next?](#whats-next)
- [💬 Questions or Feedback?](#questions-or-feedback)

---

## <h2 id="Oracle-VirtualBox-installation"> ⚙️ Oracle VirtualBox Installation </h2>

1. Download [Oracle VirtualBox](https://www.virtualbox.org/wiki/Downloads) from the official Oarle ViartualBox site.
2. Right click and run the installer as administrator.
3. Leave the default installation settings unless you have specific reason to change them.
4. Complete the installation and reboot if prompted.
5. Run VirtualBox normally.

---

## Domain Controller (DC01) 

## <h2 id="virtual-machine-setup-dc01"> 🛠️ Virtual Machine Setup </h2>

### 1. Create the Virtual Machine (VM)
- Open **VirtualBox**.
- Select **New** and fill-in the necessary details.
- Under **Virual machine name and operating system**
   - VM Name: DC01
   - ISO Image: Select from the folder in which the downloaded Microsoft server 2025 is saved
   - NB: Uncheck 'Proceed with Unattended Installation' then
   - OS Version: Windows Server 2025
  
<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/15e53e8a-25cd-4920-b488-7c9b4395a055" />
  
- Under **Specify Virtual Hardware**
  - Base Memory: 2048 = 2GB
  - Number of CPU: 1
  - NB: This settings depends on the resources of the Host machine
  
<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/c1830af7-681b-4c60-bf0d-4a1643aa7727" />
  
- Select **Specific virtual hard disk**
  - Disk Size: 50GB
  
<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/f1f2aef1-9419-4d7c-bd8a-137f263afd89" />
  
- Click **Finish**.

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/8ee74b0c-b197-4f5b-a4f3-57fffcac6a60" />

[🔝 Back to Top](#top)

---

## <h2 id="windows-server-2025-installation-dc01"> 💽 Windows Sever 2025 Installation </h2>

### Installing Windows Server 2025
- Power on **DC01** by clicking **Start**.
- When prompted to **Press any key to boot from CD or DVD**, Do not press any key.
- Under **Windows Server 2025 Setup** Settings
  - Language to install: 'English'
  - Time and currency format: 'English'
 
    <img width="975" height="639" alt="image" src="https://github.com/user-attachments/assets/93f3665e-7fe0-48ec-a50a-174b80431f0b" />

  - Keyboard or input method: 'US'
  - Then click 'Next'
 
    <img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/3c4a20fb-60ad-4b4a-8a86-f16ec4f08bcf" />
 
  - Setup option, click on **Install Windows Server**
    
    <img width="975" height="670" alt="image" src="https://github.com/user-attachments/assets/8eb7b262-8f3e-4aa2-a308-f4f56c50aade" />

  - 'Accept' Application notice and license terms.

    <img width="975" height="672" alt="image" src="https://github.com/user-attachments/assets/93982555-ce92-40ff-a608-0b6a5760d92b" />

  - Select drive and click'Next'.  

    <img width="975" height="647" alt="image" src="https://github.com/user-attachments/assets/d00cf9ec-49ec-430f-9178-f40c6cef8a5e" />

  - `Ready to install` click **Install**.

    <img width="975" height="663" alt="image" src="https://github.com/user-attachments/assets/f52c6aff-e4d5-46fb-8878-4429d081ffc0" />

  - It will take a few minutes or so depending on your resource.
 
    <img width="975" height="661" alt="image" src="https://github.com/user-attachments/assets/83ea695f-fc83-41b1-8b22-a4af5de7175b" />

  - Create a password for 'Administrator' account
 
    <img width="975" height="617" alt="image" src="https://github.com/user-attachments/assets/37b32246-673c-486c-8842-de4c394e5dec" />

  - Then 'Login' to your administrator account
 
    <img width="975" height="678" alt="image" src="https://github.com/user-attachments/assets/547125fc-0e00-4534-9c8c-ec50639c4ddf" />

  - **Windows Server 2025 installed successfully**
 
    <img width="975" height="857" alt="image" src="https://github.com/user-attachments/assets/e6747788-b2c3-45e9-a64c-2b718c07adb5" />

- Making Windows Server automatically fill the screen.
  - Click **Devices** at the 'Manu Bar' of 'VirtualBox', select **Insert Guest Addition CD Image**
  - Open **file Explorer** on Windows Sever, and click **This PC**
 
    <img width="975" height="691" alt="image" src="https://github.com/user-attachments/assets/34a1963b-9547-4b2a-a678-a667f65f83ec" />

  - Double click **CD Drive (D:) VirtualBox Guest Additions**
  - Look for and double click on **VBoxWindowsAdditional-arm64** to begin installation
  - Click 'Next' until installation is complete and 'Finish' to restart
 
    <img width="975" height="691" alt="image" src="https://github.com/user-attachments/assets/c6e7b389-547d-445e-9a83-a8c80adbf40a" />
    
[🔝 Back to Top](#top)

---



[🔝 Back to Top](#top)

---

### 3. Rename DC01
- There are 2 ways you can rename the Windows server PC
- Firstly, via **Control Panel** → **System and Security** → **System**.

  <img width="975" height="813" alt="image" src="https://github.com/user-attachments/assets/721508b9-9919-47bd-be2a-bd3232460760" />

- Then click on 'Rename your PC'

  <img width="975" height="914" alt="image" src="https://github.com/user-attachments/assets/bbc192ce-0984-49cc-ac69-ca5ea4f4daee" />


- Secondly, in **Server Manager**, click on **Local Server**.
- Click on the computer name in blue.

  <img width="975" height="931" alt="image" src="https://github.com/user-attachments/assets/5c835eca-68da-4163-bce5-d8272a2e9c23" />

- Click `Change`.

  <img width="975" height="921" alt="image" src="https://github.com/user-attachments/assets/c4079169-6814-4dfd-886b-649da2f81ae8" />

- Set Computer name to `DC01`, then click `OK`.

  <img width="975" height="927" alt="image" src="https://github.com/user-attachments/assets/7517c6c0-8829-4e52-b325-122e14154ef0" />


- Click `OK` again.
- Click `Close`.
- Click `Restart Now`

[🔝 Back to Top](#top)

---

### 4. Install Active Directory Domain Services (AD DS)
- Log in to Windows Server.
- Navigate to **Server Manager** → **Manage** → **Add Roles and Features**.
- Click 'Next'

  <img width="975" height="905" alt="image" src="https://github.com/user-attachments/assets/09a0fa26-d759-4831-b007-1abe0b4177a0" />

- By default **Role-based or feature-based installation** is selected, click 'Next'.

  <img width="975" height="849" alt="image" src="https://github.com/user-attachments/assets/b3d0abeb-3ace-425e-af00-5b4b647f0987" />

- By default the server **DC01** is selected, click 'Next'

  <img width="975" height="862" alt="image" src="https://github.com/user-attachments/assets/443e2984-015a-415a-9d49-cb5ad27e5d4d" />

- Check **Active directory Domain services**

  <img width="975" height="932" alt="image" src="https://github.com/user-attachments/assets/30530aff-03f0-473b-8cdd-10c3b9cef7c8" />

- Click 'Add Features'

  <img width="975" height="847" alt="image" src="https://github.com/user-attachments/assets/e3a32d3d-c31c-45fe-b126-c063e810dc0f" />

- Click 'Next' through remaining prompts and click `Install`.

  <img width="975" height="897" alt="image" src="https://github.com/user-attachments/assets/f3e4c9a7-3ccd-4759-aa05-63a75ba5e47a" />

 - Installation will begin, it may take a while to finish

   <img width="975" height="897" alt="image" src="https://github.com/user-attachments/assets/daf6b720-8bb9-42f2-9c2c-1bd74c92ac44" />

 - Once installation is complete, click 'close'

   <img width="975" height="898" alt="image" src="https://github.com/user-attachments/assets/2ea7e6d3-d527-4d7b-a61b-261108defa97" />
  

[🔝 Back to Top](#top)

---

### 4. Promote DC01 to Domain Controller
- Click on The notification icon
- Click **Promote this server to a domain controller**.

  <img width="975" height="892" alt="image" src="https://github.com/user-attachments/assets/dcd9d378-be62-4eb4-86ab-4b2d0518212d" />

- Select **Add a new forest**.
- Set the Root domain name to `charl.com`, and click 'Next'

  <img width="975" height="964" alt="image" src="https://github.com/user-attachments/assets/c0781549-ec75-427d-b887-a18f633a3939" />

- Set DSRM password, and click 'Next'

<img width="975" height="940" alt="image" src="https://github.com/user-attachments/assets/7e8333d8-ffad-4ea8-9c73-88eca5ac45b5" />

- Leave 'DNS Options' as default and click `Install`.
  - The yellow warnings are ok. As long as there are no actual errors you'll be fine.

  <img width="975" height="895" alt="image" src="https://github.com/user-attachments/assets/2925a218-46b8-41ff-bc7e-06d5cd2227ee" />

- Leave 'Additional Options' as Default and click 'Next'

  <img width="975" height="894" alt="image" src="https://github.com/user-attachments/assets/82cb7c5b-4034-403d-9f92-9dc3af11254f" />

- Leave 'Paths' as default and click Next

  <img width="975" height="893" alt="image" src="https://github.com/user-attachments/assets/ab8037da-181d-4e7f-aaa1-0a3730a4e818" />

- Clcik 'Next' on 'Review Options'

  <img width="975" height="947" alt="image" src="https://github.com/user-attachments/assets/98ab3a34-18f7-4781-9665-f76cd99921f9" />

- Click 'Install' once prerequisites Checks is done

  <img width="975" height="850" alt="image" src="https://github.com/user-attachments/assets/ed70c45b-0169-4958-b335-d250ba50cf9e" />

- Server automatically reboot once configuration is done
- The administrator account at login will now be CHARL\Administrator

  <img width="975" height="959" alt="image" src="https://github.com/user-attachments/assets/50d8c764-61b9-431f-9a45-5ebbf54f866c" />

### 5. Add RAS/NAT
 - 

**Domain controller successfully created! 🎉**

[🔝 Back to Top](#top)

---

## Client Machine (CLIENT01)

## <h2 id="virtual-machine-setup-client01"> 🛠️ Virtual Machine Setup </h2>

### 1. Create the virtual machine (VM).
- I create the VM on VirtualBox the same way I did for DC01
- Here is a summary of the created VM.

  <img width="975" height="530" alt="image" src="https://github.com/user-attachments/assets/bfc1cfa2-18e7-4bfd-9d6e-ceee959a89b5" />

[🔝 Back to Top](#top)

---

### 2. Network Adaptors for **CHARL-CLT01**

- Click on **CHARL-CLT01** → **Settings** → **Network** → **Adaptor 1**
  - Change 'Attached to' from 'NAT' to **Internal Network**.
  - Click 'Ok'.
 
    <img width="975" height="799" alt="image" src="https://github.com/user-attachments/assets/f585ade7-d685-4e0c-a103-0bbcc7410469" />

**That's TWO virtual machines ready to go! 🎉**

[🔝 Back to Top](#top)

---

## <h2 id="windows-os-installation-client01"> 💽 Windows OS Installation </h2>

### Installing Windows 10
- Power on **CHARL-CL01**.
- When prompted to **Press any key to boot from CD or DVD**, Do not press a key.
- Windows Setup will commence.
- Choose 'Language to install', 'Time and currency format' and 'Keyboard or input method'.
- Click, 'Next'

  <img width="975" height="634" alt="image" src="https://github.com/user-attachments/assets/10c38ccf-f46f-4533-baa1-add9aae31d53" />

- When prompted to 'Activate Windows', I select **I do not have a product key**.

  <img width="975" height="631" alt="image" src="https://github.com/user-attachments/assets/894b3cdb-8d49-47c0-977e-d495f6dd5622" />

- I accept the license terms, and click 'Next'.

  <img width="975" height="647" alt="image" src="https://github.com/user-attachments/assets/072c8c0a-75b5-443a-a95b-dee969f8b825" />

- Choose **Custom: Install Windows only (Advanced)**

  <img width="975" height="633" alt="image" src="https://github.com/user-attachments/assets/e869a5f2-aa53-4a04-be4d-e89de0760604" />

- Select drive and click 'Next'.

  <img width="975" height="611" alt="image" src="https://github.com/user-attachments/assets/b2fa3ca7-dfc2-4d9e-9f8b-6ae6970fc75b" />

- Installation will take a while, depending on machine resources.

  <img width="975" height="677" alt="image" src="https://github.com/user-attachments/assets/8941b321-20bf-4618-a2bf-2385fb1e4b0f" />

- Once installed, you'll be promped to set up **Basic** settings
  - Which include **Region**, **Keyboard Layout**, and **Second Keyboard**. Choose and click 'Yes'
 
    <img width="975" height="805" alt="image" src="https://github.com/user-attachments/assets/3b0abb22-34af-4fc8-97ed-702d19974d81" />

- Under **Account Settings**
  - Choose **Set up for personal use** and when prompted to 'Add account', I choose **Offline account** and click ''Next
 
    <img width="975" height="800" alt="image" src="https://github.com/user-attachments/assets/2fd014d1-a908-4959-9aec-6538c76df818" />

   - Microsoft sign in/up, Ichoose **Limited experience**, then click 'Next'
 
     <img width="975" height="798" alt="image" src="https://github.com/user-attachments/assets/79e3b3f2-fca7-4586-83b8-a65652bb0d21" />

   - Setup a User, click 'Next'
 
     <img width="975" height="802" alt="image" src="https://github.com/user-attachments/assets/847672b0-3284-494b-b66a-97bf0dd6f4a6" />

   - Create a password for the user, click 'Next'.
 
     <img width="975" height="803" alt="image" src="https://github.com/user-attachments/assets/1fe23ca8-9f8f-4457-842c-ddb2ddda6f0e" />

   - Create security questions for the account incase we forget the password, and click 'Next'.
 
     <img width="975" height="799" alt="image" src="https://github.com/user-attachments/assets/7e7ef7d2-864e-417c-9922-5d0362164bd7" />

- Under **Service settings**
  - Choose privacy settings and and clcik 'Accept'.
 
    <img width="975" height="795" alt="image" src="https://github.com/user-attachments/assets/215da766-370f-49eb-b570-0344b834636f" />

  - Customize the experience or skip, I 'Skip'.
 
    <img width="975" height="798" alt="image" src="https://github.com/user-attachments/assets/d698b5b0-2b39-4f3a-86f9-4183a2bda5ec" />

-Once done, we are logged into our Windows client machine.

<img width="975" height="801" alt="image" src="https://github.com/user-attachments/assets/22ff4c10-146b-4700-8505-f68f4a92726d" />

 **Windows 10 installed successfully! 🎉**

[🔝 Back to Top](#top)

---


[🔝 Back to Top](#top)

---

## <h2 id="join-client01-to-the-domain"> 🧑‍💻 Join CLIENT01 to the Domain </h2>

### 2. Rename CLIENT01
- **Control Panel** → **System** → **Rename This PC (advanced)**.
  - **System** may sometimes be **About** depending on Windows version.

  <img width="975" height="809" alt="image" src="https://github.com/user-attachments/assets/2c3fd1df-4c26-4a4f-97c6-2da90ced1964" />

- Rename to **CHARL-CLT01**, then click `Next`.

  <img width="975" height="795" alt="image" src="https://github.com/user-attachments/assets/ace4dfde-ed7e-4c6f-ac55-242f53e0612a" />

- Click `Restart Now`

  <img width="975" height="797" alt="image" src="https://github.com/user-attachments/assets/723275b7-2810-4d7f-982b-c0b60a8c2812" />

[🔝 Back to Top](#top)

---

### 3. Join the Domain
- Log back in to **CLIENT01**. 
- **Control Panel** → **System** → **Rename This PC (advanced)**.
  - **System** may sometimes be **About** depending on Windows version.

![System Settings](images/ad-setup/client01-ad/01-system-settings.png)

- Click `Change`.

![System Properties](images/ad-setup/client01-ad/02-system-properties.png)

- Select **Domain**, set to `corp.local`, then click `OK`.

![Set Domain](images/ad-setup/client01-ad/06-set-domain.png)

- Log in with your **DC01** credentials.
  - **CORP\administrator**
- Click `OK`.

![Join Domain](images/ad-setup/client01-ad/07-log-in-admin.png)

- Click `OK` to close the notification.

![Domain Joined](images/ad-setup/client01-ad/08-domain-joined.png)

- Click `OK`.

![Restart Notification](images/ad-setup/client01-ad/04-restart.png)

- Click `CLOSE` to close **System Properties**.
- Click `Restart Now` to... well, to restart.

![Restart Now](images/ad-setup/client01-ad/05-restart-now.png)

**Congrats! You now have a domain-joined client machine! 🖥️**

[🔝 Back to Top](#top)

---

## <h2 id="final-check"> ✅ Final Check </h2>

You now have a fully functional domain controller and a domain-joined Windows 10 client! 🎉  

Try logging in to CLIENT01 with **CORP/administrator**.

![Test Log In](images/ad-setup/client01-ad/09-log-in-to-test.png)

From here, you can start testing Active Directory tasks like creating users, groups, OUs, and applying GPOs (tutorial coming soon!).


[🔝 Back to Top](#top)

---

## <h2 id="wrapping-up"> 📦 Wrapping Up </h2>

Awesome job! You've just finished installing and setting up your very own virtual enterprise environment. Here's what you've accomplished:

- Installed and configured virtual machines using VMware
- Installed Windows operating systems
- Set up Active Directory
- Configured IP and DNS settings
- Joined a client machine to your domain

This walkthrough was designed to help you build confidence in setting up virtual environments and operating systems—and now you've done exactly that. You’ve laid the groundwork for your own homelab, and I’m sure you’ll be expanding and experimenting in no time! 🚀

[🔝 Back to Top](#top)

---

## <h2 id="tips"> 🧠 Tips </h2>

- Take **snapshots** at major milestones!
- Make sure **both adapters** (NAT & Host-only) are configured correctly.
- If login fails, double-check DNS settings and domain name format (`CORP\username`).


[🔝 Back to Top](#top)

---

## <h2 id="whats-next"> 📦 What's Next? </h2>

👉 [Jump to the AD Task Walkthrough ➡️](link-to-ad-tasks-readme)

[🔝 Back to Top](#top)

---

## <h2 id="questions-or-feedback"> 💬 Questions or Feedback? </h2>

If you find anything confusing or run into trouble, feel free to [open an issue](https://github.com/learnbuilddeploylabs/active-directory-home-lab/issues) or email me at learnbuilddeploylabs@gmail.com. Remember, this guide is made by a learner (that's me), for learners (that's you).

[🔝 Back to Top](#top)
