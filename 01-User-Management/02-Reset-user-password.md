# Reset Domain User Password

## Task Summary
Reset the password of a domain user account upon authorized request and verify successful login.

## Environment
- Environment Type: Production
- Directory Service: Active Directory
- Server OS: Windows Server 2019

## Purpose
Provide password reset support for a domain user who is unable to access their account.

---

## Pre-Requisites
- Domain administrative privileges
- Valid user request (authorized)
- Username or user identification details

---

## Steps Performed

1. Opened **Active Directory Users and Computers (ADUC)**
2. Navigated to the appropriate Organizational Unit (OU)
3. Located the user account using username
4. Right-clicked user → Selected **Reset Password**
5. Set new temporary password
6. Enabled option:
   - **User must change password at next logon** (if required)
7. Communicated temporary password securely to the user

---

## Verification

- User confirmed successful domain login
- Verified account is not locked
- Confirmed no authentication errors

---

## Rollback / Recovery Procedure

If issue persists:

1. Reset password again
2. Check if account is locked out
3. Verify account is enabled
4. Confirm user is in correct OU
5. Review password policy requirements

---

## Common Mistakes / Observations

- Resetting password without checking account lock status
- Not enforcing password change at next login (security risk)
- Password not meeting domain complexity requirements
- Communicating password through insecure channels

---

## Key Learning

- Always verify account lockout status before resetting password.
- Follow domain password policy requirements.
- Maintain secure password communication practices.
- Proper OU placement ensures correct policy application.

---

## Related Concepts

- Organizational Unit (OU) structure
- Domain password policy
- Account lockout policy
- Authentication process in Active Directory
