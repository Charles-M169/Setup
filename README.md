<h1 id="top"> 🧩 Active Directory: Basic Tasks Walkthrough (Beginner Edition) </h1>

Welcome! Active Directory can feel like quantum mechanics from the outside looking in, so we’ll keep things super simple in this walkthrough. You’ll perform some beginner-friendly but essential Active Directory tasks inside the lab environment you *should* have already set up. If you haven't completed the [Lab Setup Guide](../lab-setup-guide.md), I recommend starting there first.

This walkthrough assumes **zero Active Directory experience** (like I had before this) and is designed to guide you slowly and clearly through common tasks. You’ll be working inside your Windows Server 2019 VM (`DC01`) and your Windows 10/11 client machine (`CLIENT01`), both of which should already be part of the same domain.

---

## 📜 Table of Contents

- [📁 Step 1. Create Organizational Units (OUs)](#-step-1-create-organizational-units-ous)
- [👤 Step 2. Create User Accounts](#-step-2-create-user-accounts)
- [👥 Step 3. Create Security Groups](#-step-3-create-security-groups)
- [🔗 Step 4. Add Users to Groups](#-step-4-add-users-to-groups)
- [🧠 Step 5. Move CLIENT01 into the Appropriate OU](#step-5)
- [🖥️ Step 6. Create and Link a GPO](#-step-6-create-link-and-push-a-gpo)
- [🧪 Step 7. Test the GPO](#-step-7-test-the-gpo)
- [📦 Wrapping Up](#-wrapping-up)
- [💬 Questions or Feedback?](#questions-or-feedback)

---

## 📁 Step 1. Create Organizational Units (OUs)

OUs (Organizational Units) help organize users, groups, and computers into logical containers. You’ll start by creating two OUs: one for IT Support and one for HR.

1. Open **Server Manager** → **Tools** → **Active Directory Users and Computers**.
   or **Start** → **Windows Administrative Tools** → **Active Directory Users and Computers**

<img width="975" height="958" alt="image" src="https://github.com/user-attachments/assets/1460e80a-ed54-4a4e-970f-3c34b2bb12ba" />

2. In the left panel, expand your domain (`charl.com`).
3. Right-click `charl.com` → **New** → **Organizational Unit**.

<img width="975" height="968" alt="image" src="https://github.com/user-attachments/assets/8d06be15-352a-4f70-8c4b-da067df88236" />

4. Name it: `_Admins`, and click OK.
   - 🔒 **Best practice**: Leave **"Protect container from accidental deletion"** checked. For *lab* purposes, I uncheck it.

<img width="975" height="990" alt="image" src="https://github.com/user-attachments/assets/9def0b46-b8aa-48b2-84e4-e37b98e87b4d" />

5. Right-click `Departments` → **New** → **Organizational Unit** again.
   - 💡 **Tip**: You can also left click `Departments` and right-click in the detail window to bring up the menu. I'll show you in the screenshot.

<img width="975" height="1014" alt="image" src="https://github.com/user-attachments/assets/f8cf0288-e7c9-45de-99d0-3412eac53ee5" />

6. Use this process to create two sub-OUs:
   - '_Admins'
   - `_HR'
   - `_ITSupport`

<p float="left">
  <img width="975" height="836" alt="image" src="https://github.com/user-attachments/assets/b9cf896b-6e40-43e0-ab72-2700c064db31" />
  <img width="975" height="835" alt="image" src="https://github.com/user-attachments/assets/74461c96-9d66-41bc-a40c-4f1237214673" />
  <img width="975" height="734" alt="image" src="https://github.com/user-attachments/assets/8726788d-6b42-4c1a-ba29-02ed7e6c90ab" />

🎉 We have a clean structure for organizing your user accounts and departments.

[🔝 Back to Top](#top)

---

## 👤 Step 2. Create User Accounts

Let’s create one user for each department.

1. In **Active Directory Users and Computers**, right-click `_Admins` → **New** → **User**.
   - 💡 **Tip**: We can also left click `_Admins` and right-click in the detail window to bring up the menu. I'll stop pestering you with reminders going forward. 

<img width="975" height="688" alt="image" src="https://github.com/user-attachments/assets/761bdeea-7bbd-430c-bc72-68a8b2beaa0e" />

2. Use these details:
   - **First name**: `Charles`
   - **Last name**: `Matsimela`
   - **User logon name**: `Charles.M`
3. Click `Next`.

<img width="975" height="733" alt="image" src="https://github.com/user-attachments/assets/3187fc08-762a-474b-9d81-7da559d834cb" />

4. Set a password.
   - Don't forget this one. Maybe write it down this time...
   - 🔒 **Best practice**: Leave “User must change password at next logon” checked. This is a security habit used in real-world environments.
5. Click `Next`, then click `Finish`.

<img width="975" height="763" alt="image" src="https://github.com/user-attachments/assets/17c52b9b-b340-404b-8cfd-28f5b60fd2e1" />

6. Repeat for the `_HR` OU, Use these details:
   - **First name**: `Kagiso`
   - **Last name**: `Mohlala`
   - **User logon name**: `Kagiso.M`
7. Click `Next`.

   <img width="975" height="743" alt="image" src="https://github.com/user-attachments/assets/4233b616-e237-4d13-a912-7e0d2bbe5ec9" />

8. Set a password.
   - Don't forget this one. Maybe write it down this time...
   - I uncheck “User must change password at next logon” and check "Password never expires".
9. Click `Next`, then click `Finish`.

   <img width="975" height="786" alt="image" src="https://github.com/user-attachments/assets/0d38bca6-61bd-4eae-a77a-df810c3693e5" />

10. Repeat for the 'ITSupport' OU, Use these details:
   - **First name**: `John`
   - **Last name**: `Kekana`
   - **User logon name**: `John.k`
11. Click `Next`.

   <img width="975" height="785" alt="image" src="https://github.com/user-attachments/assets/ed11e024-240a-4662-aa27-e9ca7e566343" />

12. Set a password.
   - I uncheck “User must change password at next logon” and check "Password never expires".
13. Click `Next`, then click `Finish`.

   <img width="975" height="785" alt="image" src="https://github.com/user-attachments/assets/821e42d1-c21a-46b1-a980-aeccc162e1e5" />

14. Making this account a 'Domain admin'
   - Right click on the user 'Charles Matsimela'
   - Select 'Properties'
     
     <img width="949" height="734" alt="image" src="https://github.com/user-attachments/assets/1a9ecbaa-b85e-42f2-863a-a33cb196f41a" />

   - Click 'Member of'
     
     <img width="975" height="853" alt="image" src="https://github.com/user-attachments/assets/318f0700-cf73-480a-ab7b-08150202450a" />

   - Click 'Add'
   - Under **Object names to select (examples)** type: 'domain admin' and click 'Check Names'
   - Click 'Ok'
     
     <img width="975" height="916" alt="image" src="https://github.com/user-attachments/assets/8031a79d-20e5-4ba4-8989-706cb0cbc3fc" />

   - Then 'Apply' and finilly click 'Ok'
     
     <img width="975" height="815" alt="image" src="https://github.com/user-attachments/assets/514d8424-c8ef-4b54-9fa4-2ee4cd870b39" />

🎉 Way to go Neo. You've just mastered creating new users in Active Directory!

[🔝 Back to Top](#top)

---

## 👥 Step 3. Create Security Groups

Groups are used to manage permissions or apply policies to multiple users at once. Let's create some groups!

1. In **Active Directory Users and Computers**, right-click `_Admins` → **New** → **Group**.

<img width="975" height="784" alt="image" src="https://github.com/user-attachments/assets/9facee03-cd0c-4b4b-9842-0dff2e88e0bd" />

2. Use these details:
   - Group name: `Domain Admins`
   - Group scope: `Global`
   - Group type: `Security`
4. Click `OK`.

<img width="975" height="786" alt="image" src="https://github.com/user-attachments/assets/2791c1df-7b11-4824-890c-a8dd36cb1433" />

🧑‍💻 Repeat for `_HR`:

<img width="975" height="742" alt="image" src="https://github.com/user-attachments/assets/6421d4ac-0559-4e1f-a439-775f51480f39" />

- Use these details:
   - Group name: `Manager`
   - Group scope: `Global`
   - Group type: `Security`
- Click `OK`.

<img width="975" height="755" alt="image" src="https://github.com/user-attachments/assets/a43117a0-b135-4e1f-b983-6a90d17b9201" />

🧑‍💻 Repeat for `_ITSupport`:

<img width="975" height="721" alt="image" src="https://github.com/user-attachments/assets/c81cb9e7-8aac-4945-b569-02268d7e62c0" />

- Use these details:
   - Group name: `HelpDesk`
   - Group scope: `Global`
   - Group type: `Security`
- Click `OK`.

<img width="975" height="776" alt="image" src="https://github.com/user-attachments/assets/93c7fcc6-0af7-4598-a81c-44818f03ded9" />


🎉 It's starting to look like you know what you're doing! I'm sure glad one of us does...

[🔝 Back to Top](#top)

---

## 🔗 Step 4. Add Users to Groups

Let’s assign our users to their department groups.

1. Still in **Active Directory Users and Computers**, double-click `jsmith` in the `HR` OU.

![Double Clicky](images/ad-tasks/groups/05-double-click-jsmith.png)

2. Go to the **Member Of** tab, then click `Add...`

![Member Of Tab](images/ad-tasks/groups/06-member-of-tab.png)

3. Type `Managers`, click `Check Names`, then click `OK`.

![Check Name: Managers](images/ad-tasks/groups/07-managers-check-names.png)

![Name Checked: Managers](images/ad-tasks/groups/08-managers-ok.png)

4. Click `OK` to close **John Smith Properties** window.

![Close Properties](images/ad-tasks/groups/09-close-jsmith-properties.png)

🧑‍💻 Do the same for `jdoe` in `ITSupport`:

![Double Clicky](images/ad-tasks/groups/10-double-click-jdoe.png)

![Member Of Tab](images/ad-tasks/groups/11-member-of-tab.png)

- Add `jdoe` to `HelpDesk`.

![Check Name: Managers](images/ad-tasks/groups/12-helpdesk-check-names.png)

![Name Checked: Managers](images/ad-tasks/groups/13-helpdesk-ok.png)

🎉 Now we're cookin'. Keep up the great work, we're almost done!

[🔝 Back to Top](#top)

---

<h2 id="step-5"> 🖥️ Step 5. Move CLIENT01 into the Appropriate OU </h2>

To make sure GPOs apply correctly, you need to move your client machine (`CLIENT01`) into the OU you're working with.

I learned this the hard way...

Follow these steps:

1. In **Active Directory Users and Computers**, expand your domain (`corp.local`) and click on **Computers**.

![AD Users and Computers](/images/ad-tasks/gpo/09-users-and-computers.png)

2. In the right panel, right-click `CLIENT01`, the click `Move...`.

![Move CLIENT01](/images/ad-tasks/gpo/10-move-client.png)

3. Choose the `HR` OU
4. Click `OK`.

![Select HR](/images/ad-tasks/gpo/11-move-to-hr.png)

✅ **Why this matters:** GPOs targeting computers will only work if the computers are in the right OU. 

🎉 Nicely done! Just think of the tea you could spill around the office with this kind of power. 🤔

[🔝 Back to Top](#top)

---

## 🧠 Step 6. Create, Link, and Push a GPO

We’ll now create a **Group Policy Object (GPO)** that displays a message when users log in. This will help confirm the GPO is working.

1. Open **Server Manager** → **Tools** → **Group Policy Management**.

![Server Manager - Tools](/images/ad-tasks/gpo/01-tools.png)

2. Expand `corp.local` → `Departments`.
3. Right-click `HR` → **Create a GPO in this domain, and Link it here...**

![Create a GPO](/images/ad-tasks/gpo/02-create-gpo.png)

4. Name it: `HR Login Message`, then click OK.

![Name GPO](/images/ad-tasks/gpo/03-name-hr-gpo.png)

5. Right-click the new GPO under `HR` and click `Edit`.

![Edit HR GPO](/images/ad-tasks/gpo/04-edit-hr-gpo.png)

6. In the **Group Policy Management Editor**, navigate to:
   - **Computer Configuration** → **Policies** → **Windows Settings** → **Security Settings** → **Local Policies** → **Security Options**
7. Find and double-click **Interactive logon: Message title for users attempting to log on**.

![Interactive Logon:](/images/ad-tasks/gpo/05-message-title.png)

8. Set the title to 'HR Notice' and click `OK`.

![Interactive Logon:](/images/ad-tasks/gpo/06-set-title.png)

9. Find and double-click **Interactive logon: Message text for users attempting to log on**.

![Interactive Logon:](/images/ad-tasks/gpo/07-message-text.png)

10. Set the message to 'This system is for HR use only.' and click `OK`.

![Set Title](/images/ad-tasks/gpo/08-set-message.png)

11. In the left panel, right-click `HR` and click **Group Policy Update...**
   - 💡 This pushes the GPO update remotely to all computers in that OU — including `CLIENT01`.

![Push GPO](/images/ad-tasks/gpo/12-update.png)    

✔️ This message will now show every time a user logs into CLIENT01.

🎉 Now you're ready to test!

[🔝 Back to Top](#top)

---

## 🧪 Step 7. Test the GPO

Now let's test that the login message works.

1. Power on `CLIENT01`, or restart if it's already running.

2. You should see the login message!

![Login Message](/images/ad-tasks/test/03-log-in-message.png)

🎉 That’s it! The GPO is working, and you’re officially dangerous.

[🔝 Back to Top](#top)

---

## 📦 Wrapping Up

Awesome job! You just completed some of the most common beginner tasks in Active Directory:

- Creating and organizing OUs
- Creating users and groups
- Assigning users to groups
- Creating and linking a Group Policy Object
- Testing the effects of your configuration

🎉 Great job! I was mostly confident you could do it. 😉 

This walkthrough is meant to build confidence and familiarity. Once you're comfortable here, you’ll be ready to explore more advanced tasks—like password policies, folder redirection, or managing permissions.

[🔝 Back to Top](#top)

---

## <h2 id="questions-or-feedback"> 💬 Questions or Feedback? </h2>

If you find anything confusing, run into trouble, or just want to reach and tell me how awesome I am for making this, feel free to [open an issue](https://github.com/learnbuilddeploylabs/active-directory-home-lab/issues) or email me at learnbuilddeploylabs@gmail.com.

[🔝 Back to Top](#top)
