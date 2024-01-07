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

Create Accounts Script: https://github.com/jpap19/Acticve-Directory-LAB/tree/main/AD_PS_Master

STEP 1: Go to the link provided here above, download and install virtual box, Once it's installed, download and install its extension pack. Then download windows 10 ISO and Server 2019 ISO and save in a folder on the computer. oracle virtual box will be used to setup and run virtual machines, Windows 10 ISO and Server 2019 ISO will be installed on two separate virtual machines.
 
Virtual Box installed: <br/>

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/virtual%20box%20installed.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />

Windows 10 ISO and Server 2019 saved in a folder: <br/>

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/ISOs_win%2010_Server19.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />

STEP 2: Create the first virtual machine that will act as the domain controller. Install Server 2019 on it and configure two Networks Interface Card (NIC1, NIC2). NIC1 wil face internet and get IP from our home router, NIC2 will be configured with the IP showing on the diagram and act as the internal or private network. 

Domain Controler Virtual Machine created with two NICs adapter: <br/>

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/DC%20VM%20.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />

Server 2019 installed on Domain Controler, the two Network Interface cards renamed, the internal network adapter configured with the IP addresses showing on the diagram above: <br/>

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/NIC%20card%20renamed%20and%20conf.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />

Domain Controler internet connectivity tested successfuly by pinging the Google DNS Server: 8.8.8.8: <br/>

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/DC%20Internet%20Ping.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />

STEP 3: Install Active Directory on the domain controller (DC Server19), Configure Network Adresse Translation (NAT) to allow private users to get to internet, 
Setup the DHCP on that DC so that any virtual machine created on the internal network will automatically get IP adresse. Then, run a powershell script to automatically create 1K users on Active Directory.

Installation of Active Directory (AD): <br/>

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/Installation%20AD.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />
Creation and configuration of Domain Service (DS): <br/>

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/Creation%20of%20DS.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />
Active Directory created and Domain Service configured (AD DS): <br/>

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/AD%20DS%20created.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />
Creation of one user in Admin group in Active Directory Domain service: <br/>

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/user%20passou%20in%20domain%20Admin.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />
Login into the domain controler under the new group (Other) created with its new member(jean passou): <br/>

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/login%20into%20other%20Domain%20with%20user%20jean%20passou.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />
Virtual Box installed: <br/>

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/virtual%20box%20installed.png" height="80%" width="80%" alt="Active Directory Lab"/>
<br />
<br />
Windows 10 ISO and Server 2019 saved in a folder: <br/>

<img src="https://github.com/jpap19/ActiveDirectoryLab/blob/main/Images/ISOs_win%2010_Server19.png" height="80%" width="80%" alt="Active Directory Lab"/>
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
