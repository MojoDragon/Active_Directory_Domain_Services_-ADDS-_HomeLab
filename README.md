# Active_Directory_Domain_Services_-ADDS-_HomeLab
##Overview
Entry-level Active Directory home lab using Windows Server 2022 and Windows 10. Practiced user account creation, password management, domain joining, DNS configuration, and basic Group Policy to understand how IT support teams manage users and troubleshoot access issues.
## Tools & Technologies
- Windows Server 2022 ISO [link](https://www.microsoft.com/en-us/evalcenter/download-windows-server-2022) (Domain Controller)
- Windows Server 2022 ISO (client machine)
          Note: Windows Server was used for both the Domain Controller and client machine due to available resources. The client was configured as a domain member to validate authentication, DNS, and Group Policy behavior.
- Oracle VirtualBox
- Active Directory Domain Services
- Command Prompt

## Objectives
-- Install and configure Active Directory
- Create and manage users
- Perform password resets
- Apply Group Policy Objects (GPOs)

## Steps Performed

1. Installed Windows Server and configured static IP
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
