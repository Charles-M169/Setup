## <h2 id="table-of-contents"> 🗂️ Table of Contents </h2>

- [Network Setings for DC01](#network-settings-for-DC01)
  - [🛠️ Network Adaptors on VirtualBox for DC01](#network-adaptors-on-virtualBox-for-dc01)
  - [🌐 Renaming and configuring network adaptos on DC01](#renaming-and-configuring-network-on-dc01)
  
- [Network Setings for CHARL-CLT01](#network-settings-for-'charl-clt01')
  - [🛠️ Network Adaptors on VirtualBox for CHARL-CLT01](#network-adaptors-on-virtualBox-for-'charl-cl01')
  - [🌐 Renaming and configuring network adaptos on CHARL-CLT01](#renaming-and-configuring-network-on-'charl-clt01')
  - [🌐 Network Configuration](#network-configuration-client01)
  - [🧑‍💻 Join CLIENT01 to the Domain](#join-client01-to-the-domain)
- [✅ Final Check](#final-check)
- [📦 Wrapping Up](#wrapping-up)
- [🧠 Tips](#tips)
- [📦 What’s Next?](#whats-next)
- [💬 Questions or Feedback?](#questions-or-feedback)

## <h2 id="network-settings-for-DC01"> 🛠️ Network Setting for DC01</h2>
## <h2 id="network-adaptors-on-virtualBox-for-DC01"> 🌐 Network Adaptors on VirtualBox for DC01 </h2>
### 1. Network Adaptors on VirtualBox for DC01

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

...

## <h2 id="renaming-and-configuring-network-on-dc01"> 🌐 Renaming and configuring network adaptos on DC01 </h2>

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

...

## ## <h2 id="network-settings-for-'charl-clt01'"> 🛠️ Network Setting for CHARL-CLT01</h2>
## <h2 id="network-adaptors-on-virtualBox-for-'charl-cl01'"> 🌐 Network Adaptors on VirtualBox for CHARL-CLT01 </h2>

### 1. Network Adaptors for **CHARL-CLT01**

- Click on **CHARL-CLT01** → **Settings** → **Network** → **Adaptor 1**
  - Change 'Attached to' from 'NAT' to **Internal Network**.
  - Click 'Ok'.
 
    <img width="975" height="799" alt="image" src="https://github.com/user-attachments/assets/f585ade7-d685-4e0c-a103-0bbcc7410469" />
...
## <h2 id="network-configuration-client01"> 🌐 Network Configuration </h2>

### 1. Set DNS to **DC01**
- I am using **DC01** as my DNS.
- **Control Panel** → **Network and Internet** → **Network and Sharing Center** → **Change adapter settings**.

  <img width="975" height="869" alt="image" src="https://github.com/user-attachments/assets/c1563011-a0cc-4fcf-b758-735165e1c531" />

- Right-click **Ethernet1** and click `Properties`.

  <img width="975" height="802" alt="image" src="https://github.com/user-attachments/assets/9cc0b1c6-ddc2-4c12-944c-ffcbba39867e" />

- Select **Internet Protocol Version 4**, then click `Properties`.

  <img width="975" height="784" alt="image" src="https://github.com/user-attachments/assets/c0ec291e-50ef-42db-a73c-089652b9aaa1" />

- Set DNS to the **DC01** IP address, `172.16.0.1`, the click `OK`.

  <img width="975" height="782" alt="image" src="https://github.com/user-attachments/assets/d6374eea-47c4-467f-b79e-01362eadf88a" />

**Keep going, you're almost there! 🎉**
