# Active_Directory_Domain_Services_-ADDS-_HomeLab

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


## PART 1: Create Domain Controller VM (DC01)

<img width="2000" height="1485" alt="Untitled design" src="https://github.com/user-attachments/assets/ff5be8c6-2da0-4c25-8103-ba075a5bc1fe" />




## What I Learned
- How Active Directory manages users and access
- Importance of DNS in domain environments
