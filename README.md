# Active Directory using Oracle VirtualBox
---------

<br> 

# Part 1: Active Directory using Oracle VirtualBox: New User and Computer Accounts 

## Part 1: Project Summary 
Part 1 of the project covers the creation of a Domain Controller VM, Active Directory configuration, network setup with RAS/NAT, DHCP server implementation, PowerShell automation for user management, and client-machine integration. 

## Part 1: Project Overview
   - Download Windows 10 and Server 2019 ISO images for VM installations.
   - Configure the Domain Controller with dual NICs for internet and private network access.
   - Set up Active Directory, DNS, DHCP, and user administration.
   - Automate user creation with PowerShell.
   - Create a Windows 10 client machine, connect it to the domain, and explore Active Directory integration.

## Part 1: Project Steps  

1. **Domain Controller VM Setup**
   - Create a Virtual Machine (VM) for the Domain Controller (Server 2019).
   - Configure IP addressing with 2 Network Interface Cards (NICs).
   - Internet NIC: Automatically obtains an IP address from the home network.
   - Internal NIC: Manually set up for internal network.

2. **Active Directory Installation and Configuration** 
   - Install Active Directory Domain Services (AD DS). 
   - Perform post-deployment configuration: create the domain.
  
3. **Create Administrative account**
   - Note: Create our own dedicated admin account, instead of using the default admin account. 
   - Establish a dedicated Domain Adminstrator account.
   - Use: Active Directory Users and Computers 
   - Create an Organizational Unit (OU) to organize administrative accounts.
   - Create sub Organization Unit for users.
   - Assign domain admin privileges to a specific user.
     
<br>
<p align="center">  
   <img src="https://imgur.com/zeMvfWn.png" height="60%" width="60%" alt="Alt text" title="Create OU for admins">
     
   <img src="https://imgur.com/shPT2Jt.png" height="60%" width="60%" alt="Alt text" title="Create new user">
   
   <img src="https://imgur.com/UDngEFQ.png" height="60%" width="60%" alt="Alt text" title="Assign domain admin privileges">
</p>
<br>

4. **Network Configuration: RAS/NAT**
   - Set up RAS/NAT (Remote Access Server/Network Address Translation) to enable private network clients to access the internet through the Domain Controller.
   - Purpose: To allow Windows 10 clients to be on private virtual network and still be able to access the internet through the domain. 

5. **DHCP Server Set up** 
   - Set up DHCP server on the Domain Controller, allowing client computers to obtain IP addresses automatically.
   - Note: When AD DS is installed on the Domain Controller, it automatically installs DNS. Use DC as DNS server.  
   - Configure address lease durations and DHCP options, including DNS and gateway settings.

<br>
<p align="center">
   <img src="https://imgur.com/A6UUPaP.png" height="60%" width="60%" alt="Alt text" title="Set up complete">
</p>
<br>

6. **PowerShell Automation:**
   - Utilize a PowerShell script to automate the creation of a thousand new users in Active Directory.
 
<br>
<p align="center">    
   <img src="https://imgur.com/8JeS4C2.png" height="60%" width="60%" alt="Alt text" title="PowerShell Script">
   
   <img src="https://imgur.com/AndFlgx.png" height="60%" width="60%" alt="Alt text" title="Users in AD">
</p>
<br>

7. **Client Machine Setup**
   - Create a second VM for a client computer running Windows 10.
   - Connect the client VM to the VirtualBox private network.
   - Rename client machine "Client1" and join it to the domain.
   - Log in using one of the domain accounts.
  
<br>
<p align="center">
   <img src="https://imgur.com/Q8Jx1QM.png" height="60%" width="60%" alt="Alt text" title="Ping to ensure client connection to network">
   
   <img src="https://imgur.com/FYmL8gX.png" height="60%" width="60%" alt="Alt text" title="Client address lease">
   
   <img src="https://imgur.com/JWxlOmD.png" height="60%" width="60%" alt="Alt text" title="Client computer is a member of domain">
</p>
<br>

8. **Client successfully added to domain!**

<br>
<p align="center">
<img src="https://imgur.com/eFUoTKU.png" height="60%" width="60%" alt="Alt text" title="Client successfully added">
</p>
<br>

## Real-Life Scenario: Account Creation Process

Imagine this real-life scenario: You've just been hired, and your name has been added to a batch file. The following morning, like clockwork, the batch script runs, orchestrating the creation of all the new accounts, including yours. With this automated process in place, you find your account ready and waiting. Now, consider your "Client 1 VM" – your corporate laptop. Thanks to this streamlined system, you can seamlessly log in using your credentials, as it's now part of the domain and fully integrated into the network. This straightforward account creation process demonstrates the power of automation and efficient network management.

## Installation Media 
   - Windows 10 ISO
   - Windows Server 2019 ISO

## Languages Used
   - PowerShell
  
<br>

----------------------------------------------------------

<br>

# Part 2: Active Directory using Oracle VirtualBox: Group Policy 

## Part 2: Project Summary 
Part 2 of the project focuses on managing an Active Directory environment, including user and group management, folder sharing, computer account configuration, organizational unit structuring, password security enforcement, and group policy administration.

## Part 2: Project Overview
   - User and group management
   - Folder sharing
   - Computer account configuration 
   - Organizational unit structuring 
   - Password security 
   - Group policy administration 
   
## Part 2: Project Steps  

1. **User and Group Management**
     - Created a new user, 'Bob Ross,' and a dedicated 'Sales' group for the sales department.
     - Effectively added Bob Ross to the 'Sales' group, streamlining user access.
 
<br>
 <p align="center">
   <img src="https://imgur.com/l7nEEmy.png" height="60%" width="60%" alt="Alt text" title="Bob Ross in Sales Department">
 </p>
<br>

2. **Folder Sharing and Permissions**
     - Established the 'Sales Data' folder as a shared network resource, enhancing accessibility.
     - Implemented precise permissions for the 'Sales' group, ensuring secure data handling.

<br>
<p align="center">       
   <img src="https://imgur.com/nh80JaZ.png" height="60%" width="60%" alt="Alt text" title="Sales Data folder in network">
   
   <img src="https://imgur.com/6G5h33g.png" height="60%" width="60%" alt="Alt text" title="Sales Data folder permissions">
</p>
<br>

3.  **Computer Account Configuration**
     - Successfully renamed a computer to 'Client2' and integrated it into the domain environment.

<br>
<p align="center">
   <img src="https://imgur.com/TIQToHQ.png" height="60%" width="60%" alt="Alt text" title="Client 2 added to domain">
</p>
<br>

4.  **Organizational Unit (OU) Structure**
     - Strategically organized the Active Directory by creating OUs for the Atlanta office location, Atlanta users, and Atlanta computer accounts.
     - Demonstrated proficiency in moving users, such as Bob Ross, from the Users container into specific OUs.

<br>
<p align="center">
   <img src="https://imgur.com/Kxkxfdz.png" height="60%" width="60%" alt="Alt text" title="Atlanta, Users, Computer OU">
   
   <img src="https://imgur.com/vPTZS1V.png" height="60%" width="60%" alt="Alt text" title="Bob Ross: User in Atlanta office">
</p>
<br>

5. **Password Security**
     - Enforced best security practices by requiring Bob Ross to reset his password upon initial login.
  
<br>
<p align="center">
   <img src="https://imgur.com/NtZWPZk.png" height="60%" width="60%" alt="Alt text" title="Reset password for Bob Ross">
</p>
<br>

6. **Group Policy Administration**
     - Utilized Group Policy to customize wallpaper and power settings for Atlanta users, showcasing group policy management skills.
  
<br>
<p align="center">
   <img src="https://imgur.com/YhXXBnv.png" height="60%" width="60%" alt="Alt text" title="Wallpaper Group Policy">
   
   <img src="https://imgur.com/wQrCDPL.png" height="60%" width="60%" alt="Alt text" title="Wallpaper">
   
   <img src="https://imgur.com/4GGQtZK.png" height="60%" width="60%" alt="Alt text" title="Power Settings Group Policy">
   
   <img src="https://imgur.com/JohjPp0.png" height="60%" width="60%" alt="Alt text" title="Power Settings">
</p>
<br>

   
