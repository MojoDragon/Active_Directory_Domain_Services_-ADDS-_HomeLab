# Active_Directory_Domain_Services_-ADDS-_HomeLab

**Table of Contents**

*   [Overview](#Overview)
*   [Getting Started](#getting-started)
    *   [Prerequisites](#prerequisites)
    *   [Installation](#installation)
*   [Usage](#usage)
*   [Contributing](#contributing)

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


## What I Learned
- How Active Directory manages users and access
- Importance of DNS in domain environments
