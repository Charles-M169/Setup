# Lab Setup, Tools and Configuration.

## Lab Setup:

* ### Download and Install VirtualBox for the host machine
    - Download VirtualBox here: <a href="https://www.virtualbox.org/wiki/Downloads" target="_blank">Oricle VirtualBox Website</a>

    -Run and complete the installation.

## Microsoft Windows Server Setup:

* ### Windows Server Download & Installation
    - ##### Download Microfost Windows Server ISO File Here: <a href="https://info.microsoft.com/ww-landing-evaluate-windows-server-2025.html" target=" _blank">Windows Server 2025 Download Website</a>

    - ***This is a +7GB file, It may take long depending on your machine's resources, so plan accordingly.***
      
    - Follow the installation guide below
 
      1. Create a Virtual Machine and allocate resources on VirtualBox
         - ##### Open VirtualBox and Click "New"
         - ##### Under "Virtual machine name and operating system"
              &gt;  VM Name: DC01
           
              &gt;  VM Folder: Leave as it is
           
              &gt;  ISO Imaage: Select the downloaded Windows Server ISO file from the folder is saved or downloaded to
           
              &gt; OS Edition: Will autofill after the server image is selected
           
              &gt; NB: Uncheck "Proceed with Unattended Installation"
           
              &gt; OS: Leave as "Microsoft Windows"
           
              &gt; OS Version: Microsoft Server 2025 (64-bit)
 
             <img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/f2aaa412-1faa-48c5-a507-8fbefe28d625" />

          - ##### Skip "Unattednded guest OS installation"
           
          - ##### Under "Specify Virtual hardware"
           
              &gt; Base Mempry: 2048MB(2GB)
     
              &gt; Number of CPU: 1
 
              <img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/03a27394-f4e3-4e83-9d6e-079ae74f8ce4" />

           
           - ##### Under "Specify Virtual Disk"
           
              &gt; Disk Size: 50GB

              <img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/a7fe0c6f-a34b-4fa5-ac7e-0aa613b3bd62" />

           - ##### Click "Finish" and the VM will be created with the summory of the machine resources
     
              <img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/4f8dc099-e2b0-47bd-a38a-1858b9f52525" />

        2. Windows Server installation and setup
           - ##### Click "Start" to initiate windows server setup
           - ##### Your will be promptd to choose Language & Time selection
             
             <img width="975" height="639" alt="image" src="https://github.com/user-attachments/assets/09eb6808-8098-47f0-ab9f-858e7a4fa645" />
      
           - ##### Prompt to choose Keybourd & Input Language
     
             <img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/dc071361-12d5-48bb-a57a-e11d468adfea" />
      
           - ##### Setup option: Select "Ïnstall Windows Server" & check "I agree everything will be deleted including files, apps. and settings"

             <img width="975" height="670" alt="image" src="https://github.com/user-attachments/assets/a6fb94b2-1de1-4f38-8d8b-e78df86be083" />


           - ##### Select Image: Windows Server 2025 Standard Evaluation (Desktop Experience)
          
             <img width="975" height="644" alt="image" src="https://github.com/user-attachments/assets/765470d8-0fd9-4c76-9d8c-15db5d47c84d" />
    
           - ##### Accept application notice and licence terms
     
             <img width="975" height="672" alt="image" src="https://github.com/user-attachments/assets/31c7bbbe-46db-4fe5-a86c-456af9fd0cdf" />
      
           - ##### Select "Disk 0 Unallocatted Space"
     
             <img width="975" height="647" alt="image" src="https://github.com/user-attachments/assets/d1114d1c-644a-4bf1-b578-8cf1bd901b3f" />
      
           - ##### Select Ïnstall
          
             <img width="975" height="663" alt="image" src="https://github.com/user-attachments/assets/60e4fb57-3740-4947-851d-a265fb6aa71e" />

           - ##### Create a password for Administrator account

             <img width="975" height="617" alt="image" src="https://github.com/user-attachments/assets/28880d97-2a52-432b-bdce-eac860b1b060" />

           - ##### Once done, you should be able to log into your administraator acount.

             <img width="975" height="678" alt="image" src="https://github.com/user-attachments/assets/fb1babd0-b4af-41fc-afc3-0fab51b6645c" />

