# Active Directory using Oracle VirtualBox: New User and Computer Accounts 

## Project Summary 
This project covers the creation of a Domain Controller VM, Active Directory configuration, network setup with RAS/NAT, DHCP server implementation, PowerShell automation for user management, and client-machine integration. 

## Project Overview
- Download Windows 10 and Server 2019 ISO images for VM installations.
- Configure the Domain Controller with dual NICs for internet and private network access.
- Set up Active Directory, DNS, DHCP, and user administration.
- Automate user creation with PowerShell.
- Create a Windows 10 client machine, connect it to the domain, and explore Active Directory integration.

## Project Steps  

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
  
<img src="https://imgur.com/zeMvfWn.png" height="60%" width="60%" alt="Alt text" title="Create OU for admins">
  
<img src="https://imgur.com/shPT2Jt.png" height="60%" width="60%" alt="Alt text" title="Create new user">

<img src="https://imgur.com/UDngEFQ.png" height="60%" width="60%" alt="Alt text" title="Assign domain admin privileges">
  
4. **Network Configuration: RAS/NAT**
   - Set up RAS/NAT (Remote Access Server/Network Address Translation) to enable private network clients to access the internet through the Domain Controller.
   - Purpose: To allow Windows 10 clients to be on private virtual network and still be able to access the internet through the domain. 

5. **DHCP Server Set up** 
   - Set up DHCP server on the Domain Controller, allowing client computers to obtain IP addresses automatically.
   - Note: When AD DS is installed on the Domain Controller, it automatically installs DNS. Use DC as DNS server.  
   - Configure address lease durations and DHCP options, including DNS and gateway settings.

<img src="https://imgur.com/A6UUPaP.png" height="60%" width="60%" alt="Alt text" title="Set up complete">

6. **PowerShell Automation:**
   - Utilize a PowerShell script to automate the creation of a thousand new users in Active Directory.
     
<img src="https://imgur.com/8JeS4C2.png" height="60%" width="60%" alt="Alt text" title="PowerShell Script">

<img src="https://imgur.com/AndFlgx.png" height="60%" width="60%" alt="Alt text" title="Users in AD">

7. **Client Machine Setup:**
   - Create a second VM for a client computer running Windows 10.
   - Connect the client VM to the VirtualBox private network.
   - Rename client machine "Client1" and join it to the domain.
   - Log in using one of the domain accounts.
  
<img src="https://imgur.com/Q8Jx1QM.png" height="60%" width="60%" alt="Alt text" title="Ping to ensure client connection to network">

<img src="https://imgur.com/FYmL8gX.png" height="60%" width="60%" alt="Alt text" title="Client address lease">

<img src="https://imgur.com/JWxlOmD.png" height="60%" width="60%" alt="Alt text" title="Client computer is a member of domain">

8. **Client successfully added to domain!**
<img src="https://imgur.com/eFUoTKU.png" height="60%" width="60%" alt="Alt text" title="Client successfully added">

## Real-Life Scenario: Account Creation Process

Imagine this real-life scenario: You've just been hired, and your name has been added to a batch file. The following morning, like clockwork, the batch script runs, orchestrating the creation of all the new accounts, including yours. With this automated process in place, you find your account ready and waiting. Now, consider your "Client 1 VM" – your corporate laptop. Thanks to this streamlined system, you can seamlessly log in using your credentials, as it's now part of the domain and fully integrated into the network. This straightforward account creation process demonstrates the power of automation and efficient network management.

## Installation Media 
- Windows 10 ISO
- Windows Server 2019 ISO

## Languages Used
- PowerShell 
  
   
