
<img width="1600" height="896" alt="Active Directory Domain Services" src="https://github.com/user-attachments/assets/6679af25-0359-42f1-9517-92f6958c3035" />

**Table of Contents**

<a id="top"></a>

<p align="center">
  <a href="#Overview">Overview</a> •
  <a href="#Environment-Overview">Environment Overview</a> •
  <a href="#Project-Objectives">Project Objectives</a> •
  <a href="#Steps-Performed">Steps Performed</a> •
  <a href="#Screenshots">Screenshots</a> •
</p>

  
## Overview
This project simulates a small enterprise Active Directory environment, demonstrating how users authenticate against a Domain Controller and how Group Policy Objects (GPOs) are centrally managed and enforced on domain-joined client machines.

The lab mirrors real-world IT infrastructure practices commonly used in corporate environments and highlights core identity and access management concepts.

This is an entry-level Active Directory home lab built using Windows Server 2022. The Windows Server 2022 ISO was used for both the Domain Controller and the client machine due to available resources. The client system was configured as a domain member to validate authentication, DNS functionality, and Group Policy enforcement. A Windows 10 ISO is recommended for those following along <br>

<p align="right"><a href="#top">⬆ Back to top</a></p>

## Environment Overview
--Host OS: Windows 10 / Windows 11 <br>
--Hypervisor: Oracle VirtualBox (Free)<br>
--Server OS: Windows Server 2022 (Desktop Experience)<br>
--Client OS: Windows Server 2022 (used as client due to availability)<br>
--Domain Name: homelab.local<br>

<p align="right"><a href="#top">⬆ Back to top</a></p>

## Project Objectives

--Understand how Active Directory works in a corporate environment<br>
--Configure a Domain Controller (AD DS + DNS)<br>
--Create Organizational Units (OUs) and user accounts<br>
--Apply and enforce Group Policy Objects (GPOs)<br>
--Join a client machine to a domain<br>
--Validate centralized authentication and policy enforcement<br>

<p align="right"><a href="#top">⬆ Back to top</a></p>

## Steps Performed
1. Virtualization Setup
2. Promoted server to Domain Controller
3. Created Organizational Units and users
4. Reset user passwords and unlocked accounts
5. Created and applied Group Policies
6. Tested policies on a domain-joined client machine<br>

<p align="right"><a href="#top">⬆ Back to top</a></p>

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
➡️ Open Server Manager<br>
&emsp;&emsp;Local Server → Computer Name<br>
&emsp;&emsp;Rename to: DC01<br>
&emsp;&emsp;Restart

<img width="1917" height="1001" alt="computer-name" src="https://github.com/user-attachments/assets/0eaebfac-1904-4167-8542-4f3e4eed9994" />

## Part 2 3/3: Install AD DS Role

<img width="1600" height="896" alt="Why Choose Role-Based or Feature-Based Installation This option is used when Installing server roles (like Active Directory, DNS, DHCP) Installing features (like Group Policy Management) Configuri" src="https://github.com/user-attachments/assets/28ec9e81-e58f-492a-82ab-381dbbdd4612" />

## Select Role-Based or feature-based installation

<img width="1908" height="969" alt="role-based-or-remote-install" src="https://github.com/user-attachments/assets/af59caf1-b566-4af9-ab84-83610cd83b3d" />

## Select Active Directory Domain Services, than go to installation

<img width="1600" height="896" alt="Untitled design (3)" src="https://github.com/user-attachments/assets/d90e0d18-2a2a-4c87-9b0f-aec666052055" />
<img width="1909" height="1027" alt="ADDS-install" src="https://github.com/user-attachments/assets/e450e0b9-afa7-44f8-9300-889961859d9d" />

## Promote this server to a domain controller

<img width="1600" height="896" alt="Untitled design (2)" src="https://github.com/user-attachments/assets/4e119855-890c-4ab2-96d7-6173856408eb" />

## Choose:

&emsp;&emsp;New forest <br>
&emsp;&emsp;Root Domain name: homelab.local<br>
&emsp;&emsp;Complete promotion and restart<br>

<img width="1914" height="1024" alt="ADDS-deployment-config" src="https://github.com/user-attachments/assets/f8b0eefa-8f45-4a62-a148-d7ae930787cb" />


## Alerts:

<img width="1911" height="1017" alt="alerts" src="https://github.com/user-attachments/assets/610aeccd-5f1f-465f-a631-f04973f07113" />
<img width="1600" height="896" alt="those alertswarnings are completely normal at this step  👍 You’re doing the most critical change in the lab turning a standalone server into a Domain Controller  Below is a clear breakdown of eac" src="https://github.com/user-attachments/assets/fe9100a7-5d9c-4ea5-875e-68bcf5914d88" />


## PART 3 1/3: Active Directory Core Tasks

Create Organizational Unit (OU)<br>
&emsp;&emsp;Open Active Directory Users and Computers<br>
&emsp;&emsp;Right-click domain → New → Organizational Unit<br>
&emsp;&emsp;Name: IT_Users

<img width="1911" height="1005" alt="AD-core-tasks1" src="https://github.com/user-attachments/assets/022291fe-a81d-4d4f-ac64-f53f0334891e" />
<img width="1909" height="1030" alt="AD-core-tasks2" src="https://github.com/user-attachments/assets/6f88cb6b-0bcc-437d-a23a-0941e82a0c8b" />

## Create Users
Right-click IT_Users → New → User<br>
Create users:<br>
&emsp;&emsp;testuser<br>
Set:<br>
&emsp;&emsp;Initial password<br>
&emsp;&emsp;Require password change at next login

<img width="1936" height="1038" alt="testuser-input" src="https://github.com/user-attachments/assets/bf172374-e2d9-4093-ad43-a932ca5d0ceb" />
<img width="1914" height="1017" alt="testuser-password" src="https://github.com/user-attachments/assets/b827adb3-1858-44d3-9b0b-36c3f46fe7b0" />
<img width="1906" height="1035" alt="tester-finished" src="https://github.com/user-attachments/assets/aace4d21-9fdf-48a5-b608-89ef70be0630" />

## Exercise: Password Reset (Help Desk Task)
Right-click user<br>
&emsp;&emsp;Reset Password <br>
&emsp;&emsp;Unlock account if needed <br>

<img width="1914" height="1015" alt="reset-user-psswd1" src="https://github.com/user-attachments/assets/2533416d-a0bf-448f-a3bd-be55af1479a9" />
<img width="1923" height="1028" alt="reset-user-psswd2" src="https://github.com/user-attachments/assets/7712d040-9de9-4237-ba0f-d0091ef2f5f4" />

## Part 4 1/3: Group Policy (GPO)
Create GPO<br>
&emsp;&emsp;Open Group Policy Management<br>
&emsp;&emsp;Right-click domain → Create GPO<br>
&emsp;&emsp;Name: Disable_Control_Panel<br>

<img width="1900" height="1038" alt="create-new-GPO1" src="https://github.com/user-attachments/assets/7c66c4a4-c083-44b5-b1c8-095d1c168f8f" />

## Verify GPO Creation 
&emsp;&emsp;The new GPO should now appear under the domain in Group Policy Objects and be linked to the domain.

<img width="1920" height="1038" alt="verify-GPO" src="https://github.com/user-attachments/assets/f9929872-c303-4186-9daa-603517f431e0" />

## Part 4 2/3: Enable the Policy: Edit GPO
Navigate:<br>
&emsp;&emsp;User Configuration<br>
&emsp;&emsp;Administrative Templates<br>
&emsp;&emsp;Control Panel<br>
Enable:<br>
&emsp;&emsp;Prohibit access to Control Panel

<img width="1931" height="1030" alt="nav-GPO" src="https://github.com/user-attachments/assets/8b850917-6918-4a22-95f4-c170bd424cea" />
<img width="1931" height="1001" alt="enable-GPO-policy" src="https://github.com/user-attachments/assets/f88d4f81-77d1-4766-bc4e-34e4ff3d58a4" />

## Part 4 3/3: Link GPO to OU
Link GPO to IT_Users OU
<img width="1920" height="1017" alt="link-ou-to-gpo1" src="https://github.com/user-attachments/assets/0ef6f606-6c21-4da4-bc8f-a624db833466" />


## Part 5 1/2: Client Machine (Proof It Works)
Create new VM:<br>
Name: Client01<br>
Install Windows Server 2022<br>
Set DNS to:<br>
&emsp;&emsp;192.168.56.10<br>

<img width="1929" height="1028" alt="create-client01" src="https://github.com/user-attachments/assets/e7f11a7e-376f-4559-95d2-031415526328" />

## Join Domain:
Enter:<br>
&emsp;&emsp;System Properties->Change<br>
Rename computer:<br>
&emsp;&emsp;Client01<br>
Select Member of Domain and Enter:<br>
&emsp;&emsp;homelab.local<br>

<img width="3840" height="1080" alt="image" src="https://github.com/user-attachments/assets/c998781c-ef57-45f3-a778-13e1ef8f4846" />


## Quick Note: Ping Checkers
In the command prompt of Client01, ping the homelab.lab domain on the DCO1 server that was built.<br> 
One issue I found is that if both VM's are not running, then this may not establish the necessary connection.

## Example of a successful ping to the homelab.local

<img width="1600" height="896" alt="Untitled design (4)" src="https://github.com/user-attachments/assets/2b8d7053-ae84-4a71-a7fe-44cfd6d34529" />

## Part 5 2/2: Validate Policy
Log in as:<br>
&emsp;&emsp;homelab\testuser<br>
Attempt to open Control Panel<br>
Confirm access denied

<img width="1920" height="1028" alt="policy-applied" src="https://github.com/user-attachments/assets/e33ae29a-6f41-4ac7-879f-ebd27b41c51e" />

## Congrats!!

<img width="1600" height="896" alt="C" src="https://github.com/user-attachments/assets/f826f3b1-5a0e-409c-a349-fc90608095e7" />

<p align="right"><a href="#top">⬆ Back to top</a></p>



