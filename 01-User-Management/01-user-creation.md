# Create Domain User with Email Access

## Task Summary
Provision a new domain user account with required access permissions, mailbox configuration, and workstation setup.

## Environment
- Environment Type: Production
- Directory Service: Active Directory
- Server OS: Windows Server 2019
- Mail System: Microsoft Exchange
- Client OS: Windows 10/11

## Purpose
Create a new domain user account based on business requirements.  
The user must have:
- Proper Organizational Unit placement
- Required security group membership
- Shared drive access
- Mailbox access
- Remote access (if applicable)
- Fully configured workstation

---

## Pre-Requisites
- Domain administrative privileges
- User details from HR or authorized requestor
- Healthy Active Directory and Exchange environment

---

## Steps Performed

### 1. Active Directory User Creation
1. Opened **Active Directory Users and Computers (ADUC)**
2. Navigated to appropriate OU:
3. Created new user account
4. Set initial password
5. Configured password options (as per policy)

### 2. Group Membership Assignment
Added user to required security groups based on role:

- `Sales_Users`
- `USB_Disabled_Users`
- `RDS_Users` (for remote users)
- Additional role-based groups as required

> Access to shared drives is controlled via group-based permissions.

### 3. Mailbox Configuration
1. Created mailbox via **Exchange Admin Center**
2. Assigned required shared mailbox access
3. Verified mailbox provisioning

### 4. Workstation Setup
1. Connected to user workstation via TeamVeiwer
2. Installed and configured anydesk for future use (if required)
3. Configured Microsoft Outlook
4. Checked for Windows and Office updates
5. Verified domain login
6. Logged out after validation

---

## Verification Checklist

1. User successfully logs into domain
2. Mailbox accessible via Outlook / OWA
3. Group membership confirmed
4. Shared drive access verified
5. Remote access functioning (if applicable)

---

## Rollback Procedure

If account creation needs reversal:

1. Disable user account
2. Remove mailbox
3. Remove from all security groups
4. Document action taken

---

## Common Mistakes / Observations

- Placing user in incorrect OU → Incorrect GPO applied
- Assigning NTFS permissions directly instead of using security groups
- Forgetting to assign required shared mailbox access
- Not verifying RDS group for remote users

---

## Key Learning

Role-based group membership ensures:
- Scalable access control
- Easier management
- Reduced manual permission errors

---

## Related Concepts

- Organizational Unit (OU) design
- Group Policy processing order (LSDOU)
- Role-Based Access Control (RBAC)
- Exchange mailbox provisioning workflow
