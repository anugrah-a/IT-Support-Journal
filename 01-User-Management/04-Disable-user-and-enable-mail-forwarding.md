# Disable User Account and Enable Mail Forwarding

## Task Summary
Disable a former employee’s domain account and configure email forwarding to another authorized user to ensure business continuity.

---
## Environment
- Environment Type: Production
- Directory Service: Active Directory
- Server OS: Windows Server 2019
- Mail System: Microsoft Exchange
- Firewall: Sophos Firewall

---

## Purpose
When an employee leaves the organization:

- Disable domain account to prevent login access
- Preserve mailbox data
- Enable email forwarding to an authorized recipient
- Disable related firewall/VPN access

---

## Pre-Requisites

- Domain administrative privileges
- Authorized HR confirmation
- Access to Exchange Control Panel (ECP)
- Access to firewall management portal

---

## Steps Performed

### 1. Disable Active Directory Account

1. Opened **Active Directory Users and Computers (ADUC)**
2. Navigated to:Users > Sales
3. Located user account
4. Right-clicked → Selected **Disable Account**

---

### 2. Configure Mail Forwarding

1. Logged into **Exchange Control Panel (ECP)**
2. Located the disabled user mailbox
3. Enabled mail forwarding:user@company.com → user2@company.com
4. Saved configuration

> Mailbox was not deleted to retain historical data.

---

### 3. Disable Firewall Access

1. Logged into **Sophos Firewall portal**
2. Located user account
3. Disabled user to prevent VPN/firewall authentication

---

## Verification

- Attempted domain login → Access denied (account disabled)
- Sent test email to original mailbox
- Confirmed email successfully forwarded to designated recipient
- Verified firewall/VPN account is disabled

---

## Rollback Procedure

If reactivation is required:

1. Enable user account in AD
2. Disable mail forwarding
3. Re-enable firewall/VPN access
4. Reset password before reactivation

---

## Common Mistakes / Observations

- Disabling wrong user account
- Forgetting to enable mail forwarding
- Accidentally deleting mailbox instead of disabling account
- Not disabling VPN/firewall access
- Not confirming HR approval before action

---

## Key Learning

- Always verify user identity before disabling account.
- Disabling account is safer than immediate deletion.
- Email forwarding ensures business continuity.
- Access must be revoked across all systems (AD, Exchange, Firewall).

---

## Related Concepts

- Organizational Unit (OU) structure
- Group Policy application
- Exchange mailbox management
- Access deprovisioning process
- Identity lifecycle management
