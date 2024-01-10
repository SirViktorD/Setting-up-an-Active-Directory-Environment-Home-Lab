# Setting-up-an-Active-Directory-Environment-Home-Lab
<h1> SETUP AN ACTIVE DIRECTORY </h1>

 ###

<h2>Project Description</h2>
In this comprehensive and hands-on project, it's intend to guide you through the process of establishing a robust Active Directory environment within a home lab setting. Active Directory is a critical component for centralized network management and security, making this project an invaluable learning experience for individuals interested in cybersecurity and network administration.<br />

<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 

<h2>Environments Used </h2>

- <b>VirtualBox VM</b>
- <b>Server 2019</b>
- <b>Windows 10</b>

<h2>Project Step-by-Step walk-through:</h2>

<p align="center">
 <b>Step 1: Prepare Virtual Environment </b> <br/>
   
<b>Description:</b> Setting up a virtual environment is the foundation of this cybersecurity project. 
  Virtualization allows you to run multiple operating systems on a single physical machine. <br/>
<b>Actions:</b> <br/>
 - Download and Install VirtualBox: VirtualBox is a free and open-source virtualization tool. Install it on your host machine. <br/>
 - Download Windows 10 and Server 2019 ISO files: Obtain the installation files for both operating systems. <br/>
 - Create two virtual machines: In VirtualBox, create two separate virtual machines for Windows Server 2019 (Domain Controller) and Windows 10 (Client). <br/>
 
 <p align="center">
<b>-------------------------------------------------------------------------  <br/>
<>Download and Install VirtualBox. <br/>
<img src="https://imgur.com/Wns6MZw.png" height="70%" width="70%" alt="AD Steps"/>
<br/>
<br/>
  <p align="center">
<b>-------------------------------------------------------------------------  <br/>
<>Download Windows 10 ISO <br/>
<img src="https://imgur.com/8V4Z0VB.png" height="70%" width="70%" alt="AD Steps"/>
<br/>
<br/>
   <p align="center">
<b>-------------------------------------------------------------------------  <br/>
<>Download Server 2019 ISO <br/>
<img src="https://imgur.com/RAAgND4.png" height="70%" width="70%" alt="AD Steps"/>
<br/>
<br/>
    <p align="center">
<b>-------------------------------------------------------------------------  <br/>
<>Create Virtual Machines <br/>
<img src="https://imgur.com/jF45AkU.png" height="70%" width="70%" alt="AD Steps"/>
<br/>
<br/>
  <p align="justify">
- Open VirtualBox and click on "New" to create a new virtual machine. <br/>
- Follow the wizard to set up the virtual machine, specifying details like name, type (Windows), version (Windows 10 or Other Windows), memory, hard disk, etc. <br/>
<br/>
<p align="center">
  <b>-------------------------------------------------------------------------  <br/>
<> Create Virtual Machines for Server 2019 <br/>
<img src="https://imgur.com/VMSKJdW.png" height="70%" width="70%" alt="AD Steps"/>
<br/>
<br/>
- Repeat the process to create the second virtual machine for Server 2019. <br/>
 <br/>
<p align="center">
  <b>-------------------------------------------------------------------------  <br/>
<> Install Windows Server 2019 <br/>
<img src="https://imgur.com/bq4ScD2.png" height="70%" width="70%" alt="AD Steps"/>
<br/>
<br/>
- Install Windows Setup for Server 2019. <br/>  
  <b>-------------------------------------------------------------------------  <br/>
 <br/>
<p align="center">    
<b>Step 2: Domain Controller Setup. <br/>
  
<b>Description:</b> Configuring the Domain Controller involves initial network setup, including assigning IP addresses and renaming network adapters for better identification. <br/>

<b>Actions:</b> <br/>
- Assign IP addresses: Configure IP addresses for both network adapters on the Domain Controller. <br/>
- Rename network adapters: Give meaningful names to the network adapters for easier identification. <br/>
- Rename the Domain Controller PC: Provide a clear and identifiable name for the Domain Controller. <br/>
- Restart Domain Controller to apply new configuarations. <br/>
<br/>

<p align="center">
<b>-------------------------------------------------------------------------  <br/>
 <> Configure two network adapters. <br/>
<img src="https://imgur.com/tCsOEHH.png" height="70%" width="70%" alt="AD Steps"/>
<br/>
<br/>
   <p align="justify">
- On the Domain Controller's operating system, go to Network and Sharing Center to rename the adapters for easy identification. <br/>
- Configure the network adapters: one attached to NAT for internet access and another to the internal network for VirtualBox private communication. <br/>
<br/>
     <p align="center">
<b>-------------------------------------------------------------------------  <br/>
<b> > Assign IP addresses for both network adapters. <br/>
<img src="https://imgur.com/qVV3I0N.png" height="70%" width="70%" alt="AD Steps"/>
<br/>
<br/>
   <p align="justify">
- Set static IP addresses for both adapters. For this example, we used 172.16.0.1/24 for the internal network and obtain an IP from the home router for the external adapter. <br/>
- Restart the Domain Controller: After configuring adapters and renaming, restart the Domain Controller to apply changes. <br/>
<br/>
     
 <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b>Step 3: Active Directory Installation. <br/>
  
<b>Description:</b> Installing Active Directory is crucial for creating and managing the domain within the network. <br/>
<b>Actions:</b> <br/>
- Install AD/DS role: Use the Server Manager to install the Active Directory Domain Services (AD/DS) role. <br/>
- Create a new forest: Specify the domain name during the installation to create a new forest. <br/>
- Post-deployment configuration: Complete the required post-deployment configurations. <br/>
- Restart the Domain Controller: Allow the system to restart to apply the changes. <br/>
<br/>

  <p align="center">
<b>-------------------------------------------------------------------------  <br/>
<b> <> Install AD/DS role <br/>
<img src="https://imgur.com/xS3ubgg.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br /> 
<p align="justify">
- Open Server Manager on the Domain Controller. <br/>
- Click on "Manage" and select "Add Roles and Features. <br/>
<br/>  
<p align="center">
<b>-------------------------------------------------------------------------  <br/>
<b> <> Install AD/DS role: follow through setup wizard <br/>
<img src="https://imgur.com/IVhJiC7.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br />
  <p align="justify">
- Select "Active Directory Domain Services" during the role installation process. <br/>
<br/>
<p align="center">
<b>-------------------------------------------------------------------------  <br/>
<b> <> Create Forest:  <br/>
<img src="https://imgur.com/AuH1D6N.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br />
<p align="justify">
- Follow the Active Directory Domain Services Installation Wizard. <br/>
- Choose "Add a new forest" and enter the desired domain name. <br/>
<br/>
<p align="center">
  <b>-------------------------------------------------------------------------  <br/>
<b> <> DS Restore Mode password. <br/>
<img src="https://imgur.com/Ns1BKcR.png" height="70%" width="70%" alt="AD Steps"/>
<br />
- Complete the wizard, including specifying the Directory Services Restore Mode password. <br/>
  <br />
 <p align="center">
  <b>-------------------------------------------------------------------------  <br/>
<b> <> Post-deployment configuration <br/>
<img src="https://imgur.com/pbTg0Vo.png" height="70%" width="70%" alt="AD Steps"/>
<br /> 
- After the installation completes, a notification appears. Click on it to start the post-deployment configuration. <br/> 
  <br />
 <p align="center">
  <b>-------------------------------------------------------------------------  <br/>
<img src="https://imgur.com/fKumRAm.png" height="70%" width="70%" alt="AD Steps"/>
<br /> 
- Promote the server to a domain controller by choosing the appropriate options and following the wizard through. <br/>
  <br />
  <p align="center">
<b>-------------------------------------------------------------------------  <br/>
  <b> <> Restart DC <br/>
<img src="https://imgur.com/3qwPM6N.png" height="70%" width="70%" alt="AD Steps"/>
<br />
- Restart the Domain Controller to activate Active Directory. <br/>
<br />
    
<p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b>Step 4: Create an Admin Account. <br/>
  
<b>Description:</b> Setting up an administrative account in the Active Directory ensures proper management of the domain. <br/>

<b>Actions:</b> <br/>
- Open Active Directory Users and Computers: Access this tool from the Administrative Tools in the Start menu. <br/>
- Create an organizational unit: Establish a new organizational unit named "Admin. <br/>
- Create a user: Generate a user account within the "Admin" folder. <br/>
- Make the user a Domain Admin: Assign administrative privileges to the user. <br/>

<p align="center">
<b>-------------------------------------------------------------------------  <br/>
<b> <> Create Admin Account <br/>
<img src="https://imgur.com/CX7QS24.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br /> 
<p align="justify">
- Go to Start > Administrative Tools > Active Directory Users and Computers: This is the management console for Active Directory. <br/>
<br/>
<p align="center">
<b>-------------------------------------------------------------------------  <br/>
<b> <> Create Organizational Unit (OU) <br/>
<img src="https://imgur.com/rHA0MPQ.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<p align="justify">
- Create a new organizational unit (OU); Organize users by creating an OU to hold administrative accounts. <br/>
- Right-click on the domain name, choose "New," and then "Organizational Unit. <br/>
<br/>
 <p align="center">
<b>-------------------------------------------------------------------------  <br/>
<b> <> Add Organizational Unit (OU) <br/>
<img src="https://imgur.com/CRmc79W.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br /> 
<p align="justify">
  - Add Organizational Unit (OU) named "Admin"  <br/>
 <br/>
<p align="center">
<b>-------------------------------------------------------------------------  <br/>
  <b> <> Create Admin User <br/>
<img src="https://imgur.com/M6aWqYu.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br /> 
<p align="justify">
<br/>
<p align="center">
<b>-------------------------------------------------------------------------  <br/>

<img src="https://imgur.com/7iayL0v.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br /> 
<p align="justify">
 - Within the "Admin" OU, right-click, choose "New," and then "User." <br/>
  - Create a user in the "Admin" folder: to Establish an administrative user account within the designated OU. <br/>
  <br/>
 <br/>
<p align="center">
<b>-------------------------------------------------------------------------  <br/>
<img src="https://imgur.com/BrrAl0A.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br /> 
<p align="justify"> 
 - Make the new user a Domain Admin: Grant administrative privileges to the created user. <br/>
 <br/>
<p align="center">
<b>-------------------------------------------------------------------------  <br/>
<b> <> Login new user <br/>
<img src="https://imgur.com/zpSVFE0.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br /> 
<p align="justify">
 - Login with the new user Created. <br/>
 <br/>
<br/>
 
<p align="center">  
  <b>-------------------------------------------------------------------------  <br/>
<b>Step 5: Install RAS/NAT <br/>
<b>Description:</b> RAS/NAT installation allows the Domain Controller to manage network access and routing for connected clients. <br/>

<b>Actions:</b> <br/>
- Install RAS/NAT: Use Server Manager to install the Remote Access Server/Network Address Translation (RAS/NAT). <br/>
- Configure and enable Routing and Remote Access: Access the Routing and Remote Access tool to enable routing and configure NAT. <br/>
- Select external adapter: Choose the external adapter connected to the ISP during the configuration. <br/>
<br/>
<p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> <> Install RAS/NAT Role <br/>
<img src="https://imgur.com/CjGDZtt.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br />
<p align="justify"> 
 - In Server Manager, go to "Manage" and select "Add Roles and Features. <br/>
 <br/>
     <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> >   <br/>
<img src="https://imgur.com/RlDZFXb.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br />
  <p align="justify"> 
 - Install Remote Access Server/Network Address Translation (RAS/NAT): These services enable remote connectivity and handle the translation of private network addresses. <br/>
 <br/>
  <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> >   <br/>
<img src="https://imgur.com/Csgy7A2.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br />
  <p align="justify"> 
 - Choose "Remote Access" during the role installation process. <br/>
 <br/>
   <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> > Configure Routing and Remote Access  <br/>
<img src="https://imgur.com/qIzuXV7.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br />
  <p align="justify"> 
- After installation, open Routing and Remote Access from the Tools menu in Server Manager. <br/>
- Right-click on the server name and select "Configure and Enable Routing and Remote Access. <br/>
 <br/>
      <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> >   <br/>
<img src="https://imgur.com/VqvZKce.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br />
  <p align="justify"> 
 - Configure and enable Routing and Remote Access: Set up routing and remote access on the Domain Controller. <br/>
 - Click next to follow setup wizard through subsequent steps. <br/>
 <br/>  
  <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> >   <br/>
<img src="https://imgur.com/JtDBq9J.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br />
  <p align="justify"> 
 - Select NAT on the Configuration page: Choose Network Address Translation to facilitate communication between the private network and the internet. <br/>
 <br/> 
     <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> >   <br/>
<img src="https://imgur.com/K6gzVPP.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br />
  <p align="justify"> 
    - Select External Adapter: Choose the external adapter assigned earlier that connects to the ISP for NAT. <br/>
    - Click next to continue setup wizard
 <br/>
  <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> >   <br/> 
<img src="https://imgur.com/5vY95DK.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br />
  <p align="justify"> 
- RAS setup complete. <br/>
- After installation, open Routing and Remote Access from the Tools menu in Server Manager. <br/>
 <br/>  
<p align="center">  
  <b>-------------------------------------------------------------------------  <br/>
<b>Step 6: DHCP Server Setup <br/>
  
<b>Description:</b> Setting up DHCP ensures that clients on the network receive IP addresses automatically. <br/>

<b>Actions:</b> <br/>
- Install DHCP role: Use Server Manager to install the DHCP role. <br/>
- Configure DHCP scope: Define the scope by specifying the IP address range. <br/>
- Authorize and refresh: Authorize the DHCP server and refresh the domain server to apply changes. <br/>
<br/>
  <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> <> Install DHCP Role <br/>
<img src="https://imgur.com/Dnps7Ae.png" height="70%" width="70%" alt="AD Steps"/>
<br /> 
<br />
  <p align="justify"> -
  - In Server Manager, go to "Manage" and select "Add Roles and Features. <br/>
  - Select the Server selection to install roles. <br/>
 <br/>
       <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> >   <br/>
<img src="https://imgur.com/JBbsiHh.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br />
  <p align="justify"> 
- Select DHCP Sever to Install DHCP role on the Domain Controller. <br/> 
- DHCP (Dynamic Host Configuration Protocol) automatically assigns IP addresses to devices on a network. <br/>
 <br/>
     <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> >   <br/> 
<img src="https://imgur.com/F6D373a.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br />
  <p align="justify"> 
- Close Wizard after Feature Installation is Completed. <br/>
 <br/> 
     <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> <> Configure DHCP Scope  <br/> 
<img src="https://imgur.com/qSithV2.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br />
  <p align="justify"> 
- After Role installation, open DHCP from the Tools menu in Server Manager. <br/>
- Right-click on the server name and select "New Scope. <br/>
 <br/> 
     <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> >   <br/> 
<img src="https://imgur.com/Sxj8PO0.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br />
  <p align="justify"> 
- Follow the wizard to define the scope, including IP address range, subnet mask, default gateway, and DNS server. <br/> <br/>
 <br/> 
       <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> <>  Configure DHCP scope with IP address range  <br/> 
<img src="https://imgur.com/Pysh0Bf.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br />
  <p align="justify"> 
- Define the range of IP addresses that the DHCP server can assign to devices. <br/> <br/>
 <br/> 
     <p align="center"> 
<b>-------------------------------------------------------------------------  <br/>
<b> >   <br/> 
<img src="https://imgur.com/vmtCrlT.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br />
  <p align="justify"> 
- Configure DHCP Option, select yes then click next to follow setup wizard. <br/> <br/>
 <br/> 
       <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> >   <br/> 
<img src="https://imgur.com/YTfKrWM.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br /> 
  <p align="justify"> 
- Assign Router IP address (Default gateway). <br/> <br/>
 <br/> 
         <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> >   <br/> 
<img src="https://imgur.com/zFC6BVC.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br />
  <p align="justify"> 
- Assign server address (DNS). <br/>
 <br/> 
     <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> >   <br/> 
<img src="https://imgur.com/uxFRfSU.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br />
  <p align="justify"> 
- DHCP scope config complete click finish to close Wizard. <br/>
 <br/> 
     <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> <> Authorize and Refresh DHCP Server  <br/> 
<img src="https://imgur.com/OOCJQu4.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br />
  <p align="justify"> 
 - Right-click on the DHCP server in DHCP Manager and choose "Authorize. <br/>
 - Refresh the DHCP server. <br/>
    <br/> 
    <br/>
     <p align="center">  
  <b>-------------------------------------------------------------------------  <br/>
  <b>Step 7: PowerShell Script for User Creation <br/>
  
<b>Description:</b> Using PowerShell, a script is created to automate the process of generating a large number of user accounts in Active Directory. <br/>

<b>Actions:</b> <br/>
- Configure server for internet browsing: Enable internet access and file downloads. <br/>
- Disable Enhanced Security Configuration: Turn off enhanced security settings in Internet Explorer. <br/>
- Run PowerShell script: Execute the PowerShell script to generate and add 1000 users to Active Directory. <br/>
<br/>
  <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> <> Configure Internet Browsing <br/>
<img src="https://imgur.com/Z0v6Aum.png" height="70%" width="70%" alt="AD Steps"/>
<br /> 
<br />
  <p align="justify"> -
  - Configure the server to allow internet browsing/download files: Adjust server settings to enable internet access and file downloads. <br/>
  - Open Server Manager, click on "Local Server," and find "IE Enhanced Security Configuration." Turn it off for administrators and users (Note: This step is for a lab environment). <br/>
 <br/>
   <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> <> Disable Enhanced Security Configuration  <br/> 
<img src="https://imgur.com/smgWlM8.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br />
  <p align="justify"> 
- Disable Enhanced Security Configuration in IE: Turn off enhanced security settings in Internet Explorer to facilitate browsing. <br/>
- Open Internet Explorer and go to "Internet Options." Disable Enhanced Security Configuration for administrators and users. <br/>
 <br/>
    <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> >   <br/> 
<img src="https://imgur.com/E5MVDiw.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br />
  <p align="justify"> 
- Random 1000 Users/names generated to notepad. <br/>
 <br/>
    <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> <> PowerShell User Creation Script   <br/> 
<img src="https://imgur.com/eCL5Zrb.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br />
  <p align="justify"> 
- Open PowerShell ISE and execute the PowerShell script to create 1000 users in Active Directory. <br/>
 <br/>
    <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> >>   <br/> 
<img src="https://imgur.com/WhbnuPT.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br />
  <p align="justify"> 
- Set Execution Policy - this enable us run scripts, load configuration files, or profiles on powershell. <br/>
 <br/>
    <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> >   <br/> 
<img src="https://imgur.com/iGRHLJL.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br />
  <p align="justify"> 
- Change the file directory to folder having generated users/names file. <br/>
 <br/>
 <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> <> Execute Script to Create Users  <br/> 
<img src="https://imgur.com/cU65EIc.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br />
  <p align="justify"> 
- Use PowerShell to create 1000 users in Active Directory: Run a PowerShell script to automate the creation of a large number of user accounts. <br/>
<br/>
   <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> <> New Users <br/>
<img src="https://imgur.com/x0n20Lb.png" height="70%" width="70%" alt="AD Steps"/>
<br /> 
<br />
  <p align="justify">
  - New Users Created. <br/>
  <br/>
     <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<br/>
  <b>Step 8: Windows 10 Virtual Machine Installation  <br/>
  
<b>Description:</b> Install Windows 10 on a virtual machine, ensuring it receives an IP address from the DHCP configured on the Domain Controller. <br/>

<b>Actions:</b> <br/>
- Install Windows 10: Follow the installation process for Windows 10 on the virtual machine. <br/>
- Confirm internet connection: Check the IP configuration to confirm internet connectivity. <br/>
<br/>
  <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> <> Install Windows 10 <br/>
<img src="https://imgur.com/RawfELs.png" height="70%" width="70%" alt="AD Steps"/>
<br /> 
<br />
  <p align="justify">
  - Install Windows 10 CLIENT for User. <br/>
  - Install Windows 10 on the virtual machine: Use the previously downloaded Windows 10 ISO file to install the operating system on the Client virtual machine. <br/>
 <br/>
    
 <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> >>  <br/> 
<img src="https://imgur.com/vqun9OD.png" height="70%" width="70%" alt="AD Steps"/>
<br />
<br />
  <p align="justify"> 
- Installing Windows 10. <br/>
 <br/>
      <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> <> New Users <br/>
<img src="https://imgur.com/U5cP7t5.png" height="70%" width="70%" alt="AD Steps"/>
<br /> 
<br />
  <p align="justify">
  - Select Window 10 pro for Installation: as this windows OS version allow CLIENT Workgroup to join Domain. <br/>
  - Click Next to follow setup wizard
  <br/>
      <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> >  <br/>
<img src="https://imgur.com/kIBhbns.png" height="70%" width="70%" alt="AD Steps"/>
<br /> 
<br />
  <p align="justify">
  - Accept License Terms then click next to follow setup Wizard. <br/>
  <br/>
    <p align="center"> 
<b>-------------------------------------------------------------------------  <br/>
<b> <>  <br/>
<img src="https://imgur.com/JmUoqOL.png" height="70%" width="70%" alt="AD Steps"/>
<br /> 
<br />
  <p align="justify">
  - Follow setup Wizard. <br/>
  <br/>
           <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> <>  Confirm the internet connection <br/>
<img src="https://imgur.com/RUuGeuq.png" height="70%" width="70%" alt="AD Steps"/>
<br /> 
<br />
  <p align="justify">
 - Check the IP configuration of the Windows 10 machine to ensure it has internet connectivity. <br/>
  <br/>
      <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<br/>
  <b>Step 9: DHCP Router Configuration <br/>
  
<b>Description:</b> If the Default Gateway isn't assigned, configure the DHCP Router under server options on the Domain Controller. <br/>

<b>Actions:</b> <br/>
- Access DHCP Router settings: Navigate to server options in the DHCP configuration on the Domain Controller. <br/>
- Configure DHCP Router: Set up the DHCP Router to resolve any issues with the Default Gateway. <br/>
<br/>
 <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
   <br/>
<b> <> Configure DHCP Router <br/>
<img src="https://imgur.com/5NwMZ1z.png" height="70%" width="70%" alt="AD Steps"/>
<br /> 
<br />
  <p align="justify">
  - If the Default Gateway isn't assigned on the Windows 10 machine, go to the DHCP options on the Domain Controller. <br/>
  - Configure the DHCP Router option with the IP address of the Domain Controller. <br/>
    
 <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
 <br/>
<b> <> Restart Router IP <br/>
<img src="https://imgur.com/ymSpDsZ.png" height="70%" width="70%" alt="AD Steps"/>
<br /> 
<br />
  <p align="justify">
  - Restart Router IP to apply configuaration complete. <br/>
  - Right Click on the domain, under All Task drop-down select Restart
    <br/>
 <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
   <br/>
<b> <> confirm CLIENT1 PC assigned address <br/>
<img src="https://imgur.com/6k2MqMz.png" height="70%" width="70%" alt="AD Steps"/>
<br /> 
<br />
  <p align="justify">
  - To confirm connectivity ping an external ip-address i.e www.google.com, if it returns an echo-reply then we can ping our DC domain. <br/>
 <br/>
  <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<br/>
  <b>Step 10: Join Client PC to Domain  <br/>
  
<b>Description:</b> Connect the Windows 10 virtual machine to the domain created on the Domain Controller. <br/>

<b>Actions:</b> <br/>
- Join domain workgroup: Access system properties on the Windows 10 machine and join the domain workgroup. <br/>
- Enter username and password: Provide the credentials created in earlier steps. <br/>
- Restart the client PC: Ensure changes take effect. <br/>
<br/>
     <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
 <br/>
<b> <> Domain Join <br/>
<img src="https://imgur.com/72EC6oY.png" height="70%" width="70%" alt="AD Steps"/>
<br /> 
<br />
  <p align="justify">
  - Connect CLIENT PC DOMAIN. <br/>
  - On the Windows 10 machine, go to System Properties. <br/>
  <br/>
       <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
   <br/>
<b> >> <br/>
<img src="https://imgur.com/UU86dt0.png" height="70%" width="70%" alt="AD Steps"/>
<br /> 
<br />
  <p align="justify">
  - Click on "Change" under the Computer Name tab and join it to the domain using the created username and password. <br/>
  <br/>
          <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
   <br/>
<b> <> Join the Windows 10 virtual machine to the domain <br/>
<img src="https://imgur.com/b9RvuV0.png" height="70%" width="70%" alt="AD Steps"/>
<br /> 
<br />
  <p align="justify">
  - Configure system properties on the Windows 10 machine to join the domain created on the Domain Controller. <br/>
  <br/>
      <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
   <br/>
<b> <> Enter the created username and password <br/>
<img src="https://imgur.com/SLmvgaq.png" height="70%" width="70%" alt="AD Steps"/>
<br /> 
<br />
  <p align="justify">
  - Use the credentials of the user created in the "Admin" OU to join the domain. <br/>
  <br/>
    <p align="center"> 
  <b>-------------------------------------------------------------------------  <br/>
   <br/>
     <b> >> <br/>
<img src="https://imgur.com/FTn7EDy.png" height="70%" width="70%" alt="AD Steps"/>
<br /> 
<br />
  <p align="justify">
  - Workgroup Connected to DOMAIN successful. <br/>
  <br/>
       <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
  <b> <> Restart Client PC <br/>
<img src="https://imgur.com/Q9BSI2K.png" height="70%" width="70%" alt="AD Steps"/>
<br /> 
<br />
  <p align="justify">
  - Restart CLIENT PC to apply changes. <br/>
  - This Ensure changes take effect by restarting the Windows 10 virtual machine. <br/>
  <br/>
  <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<br/>
  <b>Step 11: Confirm Setup  <br/>
  
<b>Description:</b> Verify the success of the setup by logging into the client PC using the created user credentials. <br/>

<b>Actions:</b> <br/>
- Log in: Use the user credentials to log into the Windows 10 machine. <br/>
- Confirm setup: Check for successful connectivity to the domain via the Domain Controller. <br/>
<br/>
        <p align="center">  
<b>-------------------------------------------------------------------------  <br/>
<b> <> New Users <br/>
<img src="https://imgur.com/kOFpVhq.png" height="70%" width="70%" alt="AD Steps"/>
<br /> 
<br />
  <p align="justify">
  - confirm CLIENT1 PC joined to domain on DC <br/>
  <br/>
    <p align="center">
<b>-------------------------------------------------------------------------  <br/>
<b> <> Confirm successful setup and configuration <br/>
<img src="https://imgur.com/IoNPhrE.png" height="70%" width="70%" alt="AD Steps"/>
<br /> 
<br />
  <p align="justify">
  -  Verify that the Windows 10 machine CLIENT1 connected to the domain and has access to resources through the Domain Controller. <br/>
  <br/>
      <p align="center">
<b>-------------------------------------------------------------------------  <br/>
<b> <> sign in with New user <br/>
<img src="https://imgur.com/OEqezzC.png" height="70%" width="70%" alt="AD Steps"/>
<br /> 
<br />
  <p align="justify">
  - Login to the client PC: Use the created user credentials to log in to the Windows 10 machine. <br/>
  <br />
       <p align="center">
<b>-------------------------------------------------------------------------  <br/>
<b> <> Confirm signed in user was successfully <br/>
<img src="https://imgur.com/A8u3wsQ.png" height="70%" width="70%" alt="AD Steps"/>
<br /> 
<br />
  <p align="justify">
  - We can confirm the signed in user was successfully by running the cmd "whoami" to display CLIENT1 user informantion. <br/>
  <br/>
  <br />  
    <p align="center">
<b>-------------------------------------------------------------------------  <br/>
<b>-------------------------------------------------------------------------  <br/>
<br />
<br />
<h2>SUMMARY</h2>
 <p align="justify">
<b>  This comprehensive guide outlines the detailed steps involved in setting up an Active Directory environment in a home lab, covering networking, domain services, and user management. Always exercise caution and ensure security measures are in place, especially when working with configurations that involve networking and domain services.<br/>  
  <br/> <br />
  
<p align="center">
<b>------------------------------------------------------------------------- <br/>
<b>-------------------------------------------------------------------------  <br/>
 <br/>
<b> * * * THANK YOU FOR READING THROUGH. FEEL FREE TO DROP YOU COMMENTS ANYTIME. * * * <br/>
<br/>


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!># Setting-up-an-Active-Directory-Environment-Home-Lab
