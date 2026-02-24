# Outlook Mailbox Removal and Migration to Gmail

---

## Environment
- Environment Type: Production
- Client OS: Windows 11
- Email Client: Microsoft Outlook

---

## Task Summary

Removed two existing email accounts from Outlook, added a new Gmail account, and migrated inbox data (including subfolders) to the new Gmail mailbox.

---

## Purpose

User requested:

- Removal of two existing email accounts
- Addition of a new Gmail account
- Migration of all emails of second email and subdirectories to new Gmail account

Ensure safe transition without data loss.

---

## Pre-Requisites

- Remote access to user system (TeamViewer)
- Authorized user request
- Credentials for accounts being added
- Sufficient mailbox storage in destination account

---

## Steps Performed

### 1. Remote Access

1. Connected to user's computer via TeamViewer.
2. Verified Outlook configuration and existing accounts.

---

### 2. Backup of Existing Mailboxes

1. Exported both existing mailboxes to PST files.
2. Saved backup files securely before making changes.

> Backup performed to ensure rollback capability in case of failure.

---

### 3. Remove First Email Account

1. Navigated to: Outlook → Account Settings → Account Settings
2. Selected account: user1@companyname.com.au
3. Removed account as requested.

---

### 4. Add New Gmail Account

1. Added new Gmail account: newmail@gmail.com
2. 2. Completed authentication.
3. Verified mailbox synchronization.

---

### 5. Migrate Inbox and Subfolders

1. Selected old mailbox: user2@companyname.com
2. Moved:
- Inbox emails
- All subdirectories
- Important folders
3. Confirmed data fully copied to Gmail mailbox.

---

### 6. Remove Old Email Account

1. Removed: user2@companyname.com
2. Confirmed only new Gmail account remains in Outlook.

---

## Verification

- New Gmail account successfully added.
- Old accounts successfully removed.
- Inbox and subfolders visible in new Gmail account.
- User verified that all required emails were migrated.

---

## Rollback Procedure

If issue occurs:

1. Re-import PST backup files.
2. Re-add previous email accounts.
3. Restore original folder structure.
4. Reconfigure Outlook if required.

---

## Common Mistakes / Observations

- Not taking backup before removing account.
- Moving emails instead of copying without backup.
- Not verifying destination mailbox storage limit.
- Removing account before confirming successful migration.
- Incorrect IMAP/SMTP configuration for Gmail.

---

## Lessons Learned

- Always take full mailbox backup before making structural changes.
- Verify destination mailbox capacity before migration.
- Confirm data migration before removing source account.
- User confirmation is important before final cleanup.

---

## Related Concepts

- Outlook PST Backup & Restore
- IMAP vs POP configuration
- Gmail Account Integration with Outlook
- Mailbox Migration Best Practices
- Data Integrity Verification
