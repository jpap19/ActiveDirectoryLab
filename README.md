<h1>Active Directory Home Lab</h1>

<h2>Description</h2>
In this lab, we are going to Setup a Basic Home Lab Running Active Directory (Oracle VirtualBox) | Add Users w/PowerShell.

Configuring and running this lab will help understand how active directory and windows networking work.
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Diskpart</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)

<h2>Program walk-through:</h2>

<p align="center">
 
This diagram shows the environment we are going to setup. The implementation will be in done in 4 Steps:


<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/Diagram.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />


STEP 1: Download and install oracle virtual box that will be used to setup and run virtual machines. Download Windows 10 ISO and Server 2019 ISO that will be installed on two separate virtual machines.

STEP 2: Create the first virtual machine that will act as the domain controller. Install Server 2019 on it and configure two Networks Interface Card (NIC1, NIC2). NIC1 wil face internet and get IP from our home router, NIC2 will be configured with the IP showing on the diagram and act as the internal or private network. 

STEP 3: Install Active Directory on the domain controller (DC Server19), Configure Network Adresse Translation (NAT) to allow private users to get to internet, 
Setup the DHCP on that DC so that any virtual machine created on the internal network will automatically get IP adresse. Then, run a powershell script to automatically create 1K users on Active Directory.

STEP 4: Create a second virtual machine and install Windows 10 on it, this will serve as a client and connect to the private or internal virtual box. Then login with one of the domain account.

Links to download required softwares:
 
Oracle VirtualBox: https://www.virtualbox.org/wiki/Downloads   

Server 2019 ISO: https://www.microsoft.com/en-us/evalcenter/download-windows-server-2019

Windows 10 ISO: https://www.microsoft.com/en-us/software-download/windows10ISO

Create Accounts Script: https://github.com/jpap19/AD_PS.git

STEP 1: Go to the link provided here above, download and install virtual box, Once it's installed, download and install its extension pack. Then download windows 10 ISO and Server 2019 ISO and save in a folder on the computer. oracle virtual box will be used to setup and run virtual machines, Windows 10 ISO and Server 2019 ISO will be installed on two separate virtual machines.
 
1.1 Virtual Box installed: <br/>

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/virtual%20box%20installed.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />
1.2 Windows 10 ISO and Server 2019 saved in a folder: <br/>

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/ISOs_win%2010_Server19.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />

STEP 2: Create the first virtual machine that will act as the domain controller. Install Server 2019 on it and configure two Networks Interface Card (NIC1, NIC2). NIC1 wil face internet and get IP from our home router, NIC2 will be configured with the IP showing on the diagram and act as the internal or private network. 

2.1 Domain Controler Virtual Machine created with two NICs adapter: <br/>

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/DC%20VM%20.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />

2.2 Server 2019 installed on Domain Controler, the two Network Interface cards renamed, the internal network adapter configured with the IP addresses showing on the diagram above: <br/>

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/NIC%20card%20renamed%20and%20conf.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />

2.3 Domain Controler internet connectivity tested successfuly by pinging the Google DNS Server: 8.8.8.8: <br/>

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/DC%20Internet%20Ping.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />

STEP 3: Install Active Directory on the domain controller (DC Server19), Configure Network Adresse Translation (NAT) to allow private users to get to internet, 
Setup the DHCP on that DC so that any virtual machine created on the internal network will automatically get IP adresse. Then, run a powershell script to automatically create 1K users on Active Directory.

3.1 Active Directory creation and Domain Service configuration (AD DS)

3.1.1 Installation of Active Directory (AD): <br/>

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/Installation%20AD.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />

3.1.2 Creation and configuration of Domain Service (DS): <br/>

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/Creation%20of%20DS.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />

3.1.3 Active Directory created and Domain Service configured (AD DS): <br/>

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/AD%20DS%20created.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />

3.1.4 Creation of one user in one Organization Unit (Admin group) in Active Directory Domain service: <br/>

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/user%20passou%20in%20domain%20Admin.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />

3.1.5 Login into the domain controler under the new group (Other) created with its new member(jean passou): <br/>

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/login%20into%20other%20Domain%20with%20user%20jean%20passou.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />

3.2 Installation of RAS and configuration of NAT(Network Address Translation) : <br/>

3.2.1 NAT Installation (choose remote access role)

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/NAT%20installation.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />

3.2.2 NAT Configuration

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/NAT%20configuration.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />

3.2.3 NAT installed and configured under remote access role.

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/NAT%20configured%20under%20remote%20access.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />

3.3 DHCP configuration on the Domain Controller : <br/>

3.3.1 DHCP Role installation

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/dhcp%20conf%202.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />

3.3.2 DHCP Scope setting up

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/dhcp%20IP%20range%20conf.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />

3.3.3 DHCP created with the Scope

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/dhcp%20created%20with%20the%20scope.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />

3.4 Accounts Creation for 1K users in AD DS using a PowerShell Script : <br/>

3.4.1 PowerShell Script folder downloaded saved in desktop of the Domain Controller (DC-Server19); and the "Create_Users" file loaded in PowerShell ISE run as administrator.

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/Run%20PowerShell%20ISE%20as%20admin.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />

3.4.2 PowerShell Script running and creating the 1K users accounts.

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/powershell%20users%20creation.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />

3.4.3 PowerShell Script created automatically 1K accounts in Active Directory

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/powershell%20users%20created%20in%20AD2.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />

STEP 4: Create a second virtual machine and install Windows 10 on it, this will serve as a client and connect to the private or internal virtual box. Then login with one of the domain account.

4.1 Create a second virtual machine and install Windows 10

4.1.1 CLIENT Virtual Machine created with on the internal network (Private network).

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/Client1%20VM%20created%20on%20the%20internal%20network.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />

4.1.2 Windows installed on Client VM and IPs connectivity verified.  

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/Client1%20windows%20installed%20and%20IPs%20verified.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />

4.1.3 Client Internet connectivity verified by pinging the google DNS server. Also the domain created on Active Directory: "mydomain.com" is pinging succufully.

this prove that any machine created on the internal network will automatically get assigned and IP addresse and will be able to reach to the internet through the default gateway.

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/client%20DNS%20reachability.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />

4.1.4 Client Computer renamed as "CLIENT1" and configured to join the domain "mydomain.com", and has joined it successfully.

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/client%20renamed%20and%20Domain%20conf2.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />

4.1.5 DHCP Server has leased one IP addresse to the CLIENT1 computer

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/client%20IP%20addresse%20leased%20in%20dhcp%20server.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />

4.1.6 CLIENT1 computer added to Active Directory after joining the domain "mydomain.com"

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/CLIENT1%20computer%20has%20joined%20the%20AD%20after%20joining%20the%20mydomain.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />

4.2 Logged into CLIENT1 using some accounts amount the 1k accounts created  in the Active Directory.

4.2.1 Logged into CLIENT1 using the credentials of the user having the username zvarian.

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/logged%20as%20zvarian.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />

4.2.2 Logged into CLIENT1 using the credentials of the user having the username ystrandberg.

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/logged%20in%20as%20ystrandberg.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
