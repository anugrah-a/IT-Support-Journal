# Create Remote Domain User with Email, VPN, and RDS Access

## Task Summary
Provision a new remote user account with domain access, mailbox configuration, VPN connectivity, and Remote Desktop (RDS) access.

---

## Environment
- Environment Type: Production
- Directory Service: Active Directory
- Server OS: Windows Server 2019
- Mail System: Microsoft Exchange
- VPN Solution: Sophos VPN
- Remote Access: Remote Desktop Services (RDS)

---

## Purpose
Create a remote user account based on business requirements with:

- Proper OU placement
- Security group membership
- Shared drive access
- Mailbox access
- VPN connectivity
- RDS access
- Fully configured workstation

---

## Pre-Requisites

- Domain administrative privileges
- Authorized user request (HR / Management)
- Healthy Active Directory and Exchange environment
- VPN portal access
- RDS server operational

---

## Steps Performed

### 1. Active Directory User Creation

1. Opened **Active Directory Users and Computers (ADUC)**
2. Navigated to:Users > Employees
3. Created new user account
4. Set initial password (as per domain policy)

---

### 2. Security Group Assignment

Added user to required security groups:

- `Sales_Users`
- `USB_Disabled_Users`
- `RDS_Users` (for remote access)
- Additional role-based groups as required

> Shared drive and permission access controlled via group-based access.

---

### 3. Mailbox Configuration

1. Created mailbox via **Exchange Admin Center**
2. Assigned required shared mailbox permissions
3. Verified mailbox provisioning

---

### 4. VPN Configuration

1. Created VPN account in **Sophos VPN portal**
2. Connected to user workstation via remote support tool
3. Installed and configured Sophos VPN client
4. Tested VPN connectivity

---

### 5. Remote Desktop (RDS) Setup

1. Verified user is part of RDS security group
2. Connected to RDS server using Remote Desktop Connection
3. Confirmed successful login
4. Verified profile loading

---

### 6. Workstation Configuration

1. Configured Microsoft Outlook
2. Verified mailbox synchronization
3. Checked Windows and Office updates
4. Logged out after validation

---

## Verification Checklist

1. User can log into domain
2. Mailbox accessible via Outlook / OWA
3. VPN connection successful
4. RDS login working
5. Shared drive access verified
6. Group membership confirmed

---

## Rollback Procedure

If provisioning needs to be reversed:

1. Disable user account
2. Remove mailbox
3. Remove from all security groups
4. Disable VPN account
5. Document changes

---

## Common Mistakes / Observations

- Placing user in incorrect OU → Incorrect GPO applied
- Assigning NTFS permissions directly instead of using security groups
- Forgetting to add user to RDS group
- VPN configuration mismatch
- Not validating VPN connectivity before closing task

---

## Key Learning

- Role-based group membership simplifies access management.
- Always validate remote access (VPN + RDS) before task completion.
- Proper OU placement ensures correct Group Policy application.
- Remote user setup requires multi-layer validation (AD + VPN + RDS + Mail).

---

## Related Concepts

- Organizational Unit (OU) structure
- Group Policy processing (LSDOU)
- Role-Based Access Control (RBAC)
- Exchange mailbox provisioning
- VPN authentication flow
- RDS access control
