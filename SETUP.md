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

### 2. Network Adaptors

- Click **Settings** at the top and select **Network**

- **Adaptor 1**:
  - Leave the default NAT adapter.
 
<img width="975" height="733" alt="image" src="https://github.com/user-attachments/assets/53bb3bba-6a74-4bad-83c8-199ceb65d5d9" />

- **Adapter 2**
  - Check 'Enable Adaptor'
  - Attached to: 'Internal Network'
  - Name: 'Charl_Net'
  - Leave everything as it is and click 'Finish'

<img width="975" height="703" alt="image" src="https://github.com/user-attachments/assets/a25d8e5b-6913-4871-bb67-3da864886d1b" />

**First virtual machine has been created🎉**

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
 
    <img width="975" height="608" alt="image" src="https://github.com/user-attachments/assets/e26a952b-1f06-45e4-b7d2-03220c28604d" />

  - Double click **CD Drive (D:) VirtualBox Guest Additions**
  - Look for and double click on **VBoxWindowsAdditional-arm64** to begin installation
  - Click 'Next' until installation is complete and 'Finish' to restart
 
    <img width="975" height="691" alt="image" src="https://github.com/user-attachments/assets/c6e7b389-547d-445e-9a83-a8c80adbf40a" />
  -   
[🔝 Back to Top](#top)

---

## <h2 id="network-and-ad-configuration-dc01"> 🌐 Network & AD Configuration </h2>

### 1. Renaming adaptors
- **Control Panel** → **Network and Internet** → **Network and Sharing Center** → **Change adapter settings**.

  <img width="975" height="549" alt="image" src="https://github.com/user-attachments/assets/27870879-ebff-412f-acd1-8a67825ef982" />

- Run ipconfig on CMD to confirm the adaptor s as to which belongs to 'NAT adaptor' and which to 'Internal network adaptor'.
- Ethernet 1: This belongs to 'NAT' adaptor
- Ethernet 2: This belongs to 'Internal Network' adaptor

  <img width="975" height="444" alt="image" src="https://github.com/user-attachments/assets/94720d2a-6eb2-41ab-b473-0a23f9b6f108" />

- I rename 'Ethernet 1' to **'_INTERNET'** and 'Ethernet 2' to **'ÇHARL_NAT'**

  <img width="975" height="545" alt="image" src="https://github.com/user-attachments/assets/0797e2d8-debe-4940-b840-86a1d5a66dbd" />

### 2. Set Static IP on DC01 (CHARL_NAT)
- **Control Panel** → **Network and Internet** → **Network and Sharing Center** → **Change adapter settings**.

  <img width="975" height="545" alt="image" src="https://github.com/user-attachments/assets/b3828aaa-deda-4e83-b6a9-5587cd52b037" />

- Right-click **CHARL_NAT** and click `Properties`.

  <img width="975" height="526" alt="image" src="https://github.com/user-attachments/assets/e9c242cb-c592-4ff1-b1a5-88c9cfd480fd" />

- Select **Internet Protocol Version 4**, then click `Properties`.
- Use the following:
  - IP: `172.16.0.1`
  - Subnet: `255.255.255.0`
  - Gateway: (leave blank)
  - DNS: `127.0.0.1`
- Click `OK`.
 
  <img width="975" height="500" alt="image" src="https://github.com/user-attachments/assets/d6d9fb63-bfd2-4873-b91f-8c728cd4170d" />

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
- Log in (obviously).
- **Server Manager** → **Manage** → **Add Roles and Features**.

![Add Roles and Features](images/ad-setup/dc01-ad/01-roles-and-features.png)

- Click through defaults until **Server Roles**.
- Check **Active Directory Domain Services**. 

![Check AD DS](images/ad-setup/dc01-ad/02-check-ad.png)

- Click `Add Features`.

![Add Features](images/ad-setup/dc01-ad/03-add-features.png)

- Click through remaining prompts and click `Install`. 
  - **DO NOT CLOSE THE WINDOW!**
  - You closed it, didn't you? I knew it! Don't worry, keep going and we'll learn how to pay attention to big bold warnings.

![Install](images/ad-setup/dc01-ad/04-install-ad.png)

- Ignore these lies. Or don't. Your call.

![Don't Close](images/ad-setup/dc01-ad/05-do-not-close.png)

[🔝 Back to Top](#top)

---

### 4. Promote DC01 to Domain Controller
- Select **Promote this server**.

![Promote Server](images/ad-setup/dc01-ad/06-promote-server.png)

- And for those of you didn't pay attention to the warning about closing the window, you'll see a yellow notification like this on your Server Manager Dashboard. Click on it.
- Click **Promote this server to a domain controller**.

![Didn't Listen](images/ad-setup/dc01-ad/07-promote-server-did-not-listen.png)

- Select **Add a new forest**.
- Set the Root domain name to `corp.local`.

![Domain Name](images/ad-setup/dc01-ad/08-add-forest.png)

- Set DSRM password.
  - Write it down.
  - You already forgot it, didn't you?
  - Seriously, you'll need it for certain recovery tasks.
- Click `Next`.

![Set DSRM Password](images/ad-setup/dc01-ad/09-dsrm-password.png)

- Accept defaults in the following sections and click `Install`.
  - The yellow warnings are ok. As long as there are no actual errors you'll be fine. Trust me...

![Install Forest](images/ad-setup/dc01-ad/10-install-forest.png)

- Server will reboot automatically after configuration.

![Reboot](images/ad-setup/dc01-ad/11-reboot.png)

**Congrats! You’ve just created your own domain controller! 🎉**

[🔝 Back to Top](#top)

---

## Client Machine (CLIENT01)

## <h2 id="virtual-machine-setup-client01"> 🛠️ Virtual Machine Setup </h2>

### 1. Create the virtual machine (VM).
- Open **VMware Workstation Pro**.
- Select **Create a New Virtual Machine**.
  
![Create a New Virtual Machine](images/vm-installation/client01-setup/01-create-vm.png)
  
- Choose **Typical (recommended)** and click `Next`.
  
![Typical Installation](images/vm-installation/client01-setup/02-typical-config.png)
  
- Select **I will install the operating system later**, then click `Next`.
  
![Install Later](images/vm-installation/client01-setup/03-install-os-later.png)
  
- **OS: Microsoft Windows** → **Version: Windows 10**.
- Click `Next`.

![Select OS](images/vm-installation/client01-setup/04-select-os.png)
  
- Name the virtual machine **CLIENT01**, choose a save location, then click `Next`.

![Name and Location](images/vm-installation/client01-setup/05-name-location.png)

- Allocate **40 GB** of storage (Dynamic allocation is fine), then click `Next`.

![Disk Capacity](images/vm-installation/client01-setup/06-disk-capacity.png)

- Click `Customize Hardware`.

![Customize Hardware](images/vm-installation/client01-setup/07-customize-hardware.png)


[🔝 Back to Top](#top)

---

### 2. Hardware Customization
- **Memory**: 4096 MB (4GB) recommended, but the default may work fine depending on your system.
- **Processors**: 2

<img src="images/vm-installation/client01-setup/08-ram-processor.png" alt="RAM and CPU" width="448" height="450">

- **CD/DVD (SATA)**: Choose `Use ISO image file` and load your Windows 10 ISO.

<img src="images/vm-installation/client01-setup/09-select-iso.png" alt="Select ISO" width="448" height="450">

- **Network Adapters**:
  - Leave the default NAT adapter.
  - Click 'Add'.
 
<img src="images/vm-installation/client01-setup/10-add-network.png" alt="Add Adapter" width="448" height="450">

  - Select **Network Adapter**, then click `Finish`.

![Select Adapter](images/vm-installation/client01-setup/11-select-second-adapter.png)

  - Select **Host-only: A private network shared with the host**, then click `Close`

<img src="images/vm-installation/client01-setup/12-hostonly-adapter.png" alt="Host Only Adapter" width="448" height="450">

- Click `Finish`.

**That's TWO virtual machines ready to go. Nicely done! 🎉**

[🔝 Back to Top](#top)

---

## <h2 id="windows-os-installation-client01"> 💽 Windows OS Installation </h2>

### Installing Windows 10
- Power on **CLIENT01**.
- When prompted to **Press any key to boot from CD or DVD**, press any key.
  - **REMEMBER**: Don't be a slow-poke here!

![Press Any Key](images/os-installation/client01-os/01-press-any-key.png)

- Accept the license terms, click `Next`.
- Choose **Custom: Install Windows only (advanced)**.

![Custom Install](images/os-installation/client01-os/03-custom-install.png)

- Select drive and click `Next`.

![Select Drive](images/os-installation/client01-os/04-select-drive.png)

- Once installed, log in.
  - Choose **Offline Account**, **Domain Join Instead**, or **Skip** Microsoft sign-in (depending on version).

![Log In](images/os-installation/client01-os/05-domain-join-instead.png)

- Create a local user like `LabUser`.
- Finish setup.
- Install VMware Tools.
  - This improves performance, mouse behavior, and screen resolution.
  - But you knew that already, didn't you? Or did you skip a section? You rebel.

![Install VMware Tools](images/os-installation/client01-os/06-install-vmware-tools.png)

  - Click `Next`.
  - Select **Typical**, click `Next`.

  ![VMware Tools Typical Install](images/os-installation/client01-os/07-vmware-tools-typical.png)

  - Click `Install`, then `Finish`.
  - Click `Yes` to restart.
    - There's a mandatory restart coming up in a few steps after you rename this computer, so you can hold off on restarting if you want to. Or can you...? (This sounds familiar, doesn't it?).

**You could do this in your sleep! Keep up the great work! 🎉**

[🔝 Back to Top](#top)

---

## <h2 id="network-configuration-client01"> 🌐 Network Configuration </h2>

### 1. Set DNS to **DC01**
- We're using **DC01** as our DNS.
- **Control Panel** → **Network and Internet** → **Network and Sharing Center** → **Change adapter settings**.

![Change Adapter Settings](images/network-setup/client01-network/01-change-adapter-settings.png)

- Right-click **Ethernet1** and click `Properties`.

![Ethernet1 Properties](images/network-setup/client01-network/02-ethernet1-properties.png)

- Select **Internet Protocol Version 4**, then click `Properties`.

![IPv4 Properties](images/network-setup/client01-network/03-ethernet-properties.png)

- Set DNS to the **DC01** IP address, `192.168.100.10`, the click `OK`.

![Set DNS](images/network-setup/client01-network/04-set-dns.png)

**Keep going, you're almost there! 🎉**

[🔝 Back to Top](#top)

---

## <h2 id="join-client01-to-the-domain"> 🧑‍💻 Join CLIENT01 to the Domain </h2>

### 2. Rename CLIENT01
- **Control Panel** → **System** → **Rename This PC (advanced)**.
  - **System** may sometimes be **About** depending on Windows version.

![System Settings](images/ad-setup/client01-ad/01-system-settings.png)

- Click `Change`.

![System Properties](images/ad-setup/client01-ad/02-system-properties.png)

- Rename to **CLIENT01**, then click `OK`.

![Rename Computer](images/ad-setup/client01-ad/03-change-name.png)

- Click `OK`.

![Restart Now](images/ad-setup/client01-ad/04-restart.png)

- Close **System Properties**
- Click `Restart Now`

![Restart Now](images/ad-setup/client01-ad/05-restart-now.png)

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
