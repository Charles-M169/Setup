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
           
        2. Skip "Unattednded guest OS installation"
           
        4. Under "Specify Virtual hardware"
              &gt; Base Mempry: 2048MB(2GB)
           
              &gt; Number of CPU: 1
           
        5. Under "Specify Virtual Disk"
           
              &gt; Disk Size: 50GB

           
