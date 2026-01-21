# Active_Directory_Domain_Services_-ADDS-_HomeLab

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

## Step 0.1: 
Download VirtualBox. Go to the Oracle VirtualBox website
Download: VirtualBox Platform Package (Windows hosts), VirtualBox Extension Pack (same version)

<img width="1186" height="728" alt="virtualbox-download" src="https://github.com/user-attachments/assets/ca8bf633-dc8b-41ee-ad20-430f32d1cbb6" />

## Remember to allocate enough space :)                                                                                                                                                 Virtual Box Main Window

<img width="480" height="378" alt="virtualbox-space-allocation" src="https://github.com/user-attachments/assets/7255c339-be80-41f2-8cc4-362c0aa60f89" /> <img width="480" height="378" alt="virtualbox-main-window" src="https://github.com/user-attachments/assets/73274ac5-14a7-4d5a-9afc-13cba08c4cce" />

## What I Learned
- How Active Directory manages users and access
- Importance of DNS in domain environments
