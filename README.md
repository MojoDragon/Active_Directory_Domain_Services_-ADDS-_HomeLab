
<img width="1600" height="896" alt="Active Directory Domain Services" src="https://github.com/user-attachments/assets/6679af25-0359-42f1-9517-92f6958c3035" />

**Table of Contents**

*   [Overview](#Overview)
*   [Tools & Technologies](#Tools-&-Technologies)
*   [Objectives](#Objectives)
*   [Steps Performed](#Steps-Performed)
*   [Troubleshooting](#Troubleshooting)
*   [Screenshots](#Screenshots)
*   [What I Learned](#What-I-Learned)
  
## Overview
This project simulates a small enterprise Active Directory environment, demonstrating how users authenticate against a Domain Controller and how Group Policy Objects (GPOs) are centrally managed and enforced on domain-joined client machines.

The lab mirrors real-world IT infrastructure practices commonly used in corporate environments and highlights core identity and access management concepts.

This is an entry-level Active Directory home lab built using Windows Server 2022. The Windows Server 2022 ISO was used for both the Domain Controller and the client machine due to available resources. The client system was configured as a domain member to validate authentication, DNS functionality, and Group Policy enforcement. A Windows 10 ISO is recommended for those following along 

## Tools & Technologies
- Windows Server 2022 ISO [link](https://www.microsoft.com/en-us/evalcenter/download-windows-server-2022)       
- Oracle VirtualBox
- Active Directory Domain Services (AD DS)
- DNS
- Group Policy Management

## Objectives
-- Install and configure Active Directory
- Create and manage users
- Perform password resets
- Apply Group Policy Objects (GPOs)

## Steps Performed
1. Virtualization Setup
2. Promoted server to Domain Controller
3. Created Organizational Units and users
4. Reset user passwords and unlocked accounts
5. Created and applied Group Policies
6. Tested policies on a domain-joined client machin

## Troubleshooting
- Resolved DNS issues by correcting adapter settings
- Fixed login errors by verifying group policies

## Screenshots

## PART 0: Install VirtualBox 
Download VirtualBox. Go to the Oracle VirtualBox website <br>
Download: VirtualBox Platform Package (Windows hosts), VirtualBox Extension Pack (same version)

<img width="1186" height="728" alt="virtualbox-download" src="https://github.com/user-attachments/assets/ca8bf633-dc8b-41ee-ad20-430f32d1cbb6" />

## Remember to allocate enough space :) &emsp; &emsp; &emsp; Virtual Box Main Window

<img width="480" height="378" alt="virtualbox-space-allocation" src="https://github.com/user-attachments/assets/385dd458-74f0-4956-be06-f4b2a0e8654c" />&emsp; <img width="480" height="378" alt="virtualbox-main-window" src="https://github.com/user-attachments/assets/5ce667f4-ed44-4839-9494-affda3de3b77" />


## PART 1 1/3: Create Domain Controller VM (DC01)

<img width="2000" height="1485" alt="Untitled design" src="https://github.com/user-attachments/assets/ff5be8c6-2da0-4c25-8103-ba075a5bc1fe" />

## PART 1 2/3: Hardware Settings 

<img width="956" height="736" alt="vm-hardware-settings" src="https://github.com/user-attachments/assets/368188ea-0e9d-4864-a65c-bb2761994882" />

## Part 1 3/3: Install Windows Server <br>
If a failure to boot error message occurs, don't worry. Please ensure that you have your Windows Server ISO file handy. Select the file, then Mount and Reboot.
<img width="1863" height="1012" alt="mount-reboot-iso-file" src="https://github.com/user-attachments/assets/f4351141-bb24-4c2b-b30a-75c2f0d06c79" />

## Select the Operating System you want to install
Since this exercise guide is generally for those getting their feet wet. I would recommend the following for these reasons: <br>

➡️ Windows Server 2022 Standard Evaluation (Desktop Experience)

✔ Has a full graphical interface
✔ Best for Active Directory learning
✔ Easiest to follow tutorials 


<img width="1863" height="885" alt="windows-server-install" src="https://github.com/user-attachments/assets/b978b314-77a2-4137-88c5-3357b8b66b26" />

## No Operating System = No Upgrade
If you accidentally select the "Upgrade", it will not allow the upgrade because there is no operating system (OS). Press the back arrow and do the following:

➡️ Select Custom install, then hit next on the following screen. Remember, persistence is key! 

<img width="1920" height="1080" alt="Untitled design (1)" src="https://github.com/user-attachments/assets/24ced819-eb4b-4507-93df-9f6c0c6dde7e" />

## Login and Congrats! 

<img width="1920" height="1002" alt="server-desktop" src="https://github.com/user-attachments/assets/7be4d7e0-ffef-432f-864f-4df928321bef" />

## PART 2 1/3: Network & Domain Setup

Domain Controllers must not use DHCP. An active directory needs a fixed IP address because it depends on DNS. Stability is important.

➡️ Open Control Panel<br>
   &emsp;&emsp; Network and Internet → Network Connections<br>
   &emsp;&emsp;Right-click Ethernet → Properties<br>
   &emsp;&emsp;Select IPv4 → Properties<br>

Configure:<br>
    &emsp;&emsp;IP: 192.168.56.10<br>
    &emsp;&emsp;Subnet: 255.255.255.0<br>
    &emsp;&emsp;DNS: 127.0.0.1

<img width="1929" height="1012" alt="static-ip-config" src="https://github.com/user-attachments/assets/7c749f8f-1bd6-4248-9477-91a39ddbb2bb" />

## Part 2 2/3: Rename Servers
Open Server Manager<br>
&emsp;&emsp;Local Server → Computer Name<br>
&emsp;&emsp;Rename to: DC01<br>
&emsp;&emsp;Restart

<img width="1917" height="1001" alt="computer-name" src="https://github.com/user-attachments/assets/0eaebfac-1904-4167-8542-4f3e4eed9994" />


## What I Learned
- How Active Directory manages users and access
- Importance of DNS in domain environments
