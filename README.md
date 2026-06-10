# WindowsServer2025HomeLab
This home lab demonstrates the deployment, configuration, and administration of a Windows Server 2025 environment simulating a real world enterprise network. The primary objective of this project was to build a hands-on foundation in system administration and foundational networking concepts.

By building this environment from scratch, I gained practical experience executing administrative tasks, managing directory objects, enforcing security baselines through Group Policy, and troubleshooting core enterprise network services, all skills directly transferable to an enterprise Tier 1 Help Desk or Technical Support role.

Environment & Tools Used
Hypervisor: Oracle VirtualBox

Operating Systems: * Windows Server 2025 Standard Evaluation (Desktop Edition) acting as the Domain Controller

Windows 11 Pro acting as the client workstation

Core Technologies: Active Directory Domain Services (AD DS), DNS Manager, Group Policy Management, Command Line Interface (CLI/PowerShell).

🛠️ Skills Demonstrated
Active Directory Management: Account provisioning, password resets, account unlocking, and object lifecycle management (disabling accounts for offboarding).

Organizational Structure: Designing efficient Organizational Unit (OU) hierarchies and managing Global Security Groups.

Group Policy Object (GPO) Implementation: Configuring security baselines (Password Policies) and automating enterprise desktop environments (Wallpaper policies).

Networking Foundations: Understanding domain name resolution (DNS), domain trust verification, and client-to-domain machine binding.

Command Line Troubleshooting: Utilizing tools like gpupdate /force to ensure rapid policy distribution and verify workstation compliance.

📖 Step-by-Step Implementation Guide
Part 1: Domain Controller Provisioning & Core Infrastructure
To establish the enterprise environment, I installed the necessary server roles and promoted the machine to a dedicated Domain Controller.

Installing Active Directory Domain Services (AD DS): Began by utilizing the Add Roles and Features Wizard in Windows Server Manager to install the AD DS binaries.

Tracking Installation Progress: Monitored the initial installation, ensuring the deployment of basic Remote Server Administration Tools (RSAT) and PowerShell AD modules.

Promoting the Server: Transitioned the standalone server into a dedicated Domain Controller.

Creating a New Active Directory Forest: Created a new internal network using the root domain name test.local.

Finalizing Active Directory Configuration: Finalized the setup parameters and initiated the formal configuration of the domain databases.

Verifying Successful Domain Authentication: Following a system reboot, verified successful domain promotion by logging into the newly formed NetBIOS domain as the Domain Administrator (TEST\Administrator).

Launching Core Admin Consoles: Successfully opened the Active Directory Users and Computers (ADUC) console, verifying the database infrastructure was fully operational.

Part 2: Network Management & Directory Architecture
With the Domain Controller operational, I audited core network services and configured an organized, scalable directory hierarchy modeled after a real company.

Verifying Domain Trusts: Audited the Active Directory Domains and Trusts snap-in to confirm the root forest layout and domain functional integrity.

Auditing DNS Manager: Opened the DNS Manager console to ensure that the domain controller was properly resolving queries and managing forward lookup zones for test.local.

Preparing Group Policy Management: Accessed the Group Policy Management console to audit the Default Domain Policies before deploying targeted changes.

Structuring Organizational Units (OUs): Formed dedicated OUs for core business departments (IT and HR) to allow for flexible administration and targeted Group Policy enforcement.

Provisioning User Objects: Practiced onboarding employee accounts by generating a standardized Test User account inside the directory.

Verifying Account Creation: Confirmed the new account object successfully populated within the target container and was ready for network authentication.

Implementing Security Groups: Created a Global Security Group named IT_Staff. This demonstrates an understanding of the industry-standard AGDLP principle (Accounts -> Global Groups -> Domain Local Groups -> Permissions) to assign access rights efficiently.

Part 3: Tier 1 Help Desk Operations & Endpoint Management
This section focuses on simulating high-volume Help Desk scenarios, managing the endpoint environment, and executing password/account maintenance tickets.

Domain Join (Endpoint Provisioning): Successfully bound a remote client workstation to the test.local network, demonstrating the capability to provision new endpoints for end-users.

Executing User Password Resets: Simulated a standard "I forgot my password" ticket. Processed the password reset and enforced the mandatory security practice: “User must change password at next logon”.

Unlocking Locked-Out Accounts: Addressed brute-force or lockout scenarios by using administrative permissions to unlock an employee's network account profile.

Executing Account Disabling (User Offboarding): Simulated a termination or offboarding workflow by disabling a user object, instantly revoking all active enterprise access privileges.

Configuring Password Policies: Established baseline account protection rules within the domain to control password complexity requirements, minimum length, and expiration terms.

Deploying Environment Standardization GPOs: Built a customized Group Policy Object to enforce a standard corporate desktop wallpaper across all connected user profiles automatically.

Forcing Group Policy Updates (CLI): Utilized the Windows Command Line to issue a gpupdate /force directive. This ensures newly deployed security and environment policies are pushed immediately to all endpoints without waiting for the standard background refresh cycle.

🎯 Key Takeaways & Help Desk Alignment
Active Directory Proficiency: I can confidently navigate ADUC to handle password resets, account lockouts, account disabling, group assignment, and OU navigation, reducing my ramp-up time during onboarding.

Troubleshooting Mindset: Setting up this lab required fixing real-world synchronization errors, setting correct static IP addresses, and configuring internal DNS forwarders. This sharpened my tier-1 diagnostic approach.

Enterprise Standards: By building separate department containers and groups, I understand how corporate permissions are restricted, allowing me to safely handle sensitive data or privilege inquiries.
