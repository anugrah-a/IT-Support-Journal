# Veeam Backup Failure – NAS Not Detected in File Explorer

---

## Environment
- Environment Type: Client
- Backup Server: Windows Server 2016
- Backup Software: Veeam Backup & Replication
- Storage: Network Attached Storage (NAS)

---

## Issue Summary

Veeam backup job failed because the NAS repository was not accessible from the backup server.

---

## Detailed Problem

Observed behavior:

- NAS not visible in File Explorer on Veeam server.
- Backup job failed due to repository path not being found.
- NAS was reachable via web browser (management interface accessible).
- Indicates NAS was powered on and operational.
- Only SMB/file access from server was failing.

---

## Initial Analysis

Possible causes considered:

- Network discovery disabled
- Network profile set to Public instead of Private
- SMB service issue
- Temporary network communication issue
- Windows Explorer not refreshing network shares

Primary suspicion:  
**Network discovery or network profile configuration issue**

---

## Troubleshooting Steps

1. Verified NAS is reachable via browser (confirmed device is online).
2. Checked if NAS is accessible via IP address.
3. Restarted Veeam backup server.
4. After restart, NAS became visible in File Explorer.
5. Retried Veeam backup job → Backup succeeded.

Potential solution identified (if issue persists):

- Change network profile to **Private** in Local Security Policy / Network Settings
- Ensure Network Discovery is enabled

---

## Root Cause

Temporary network discovery or SMB communication issue between Veeam server and NAS.

Likely caused by:

- Network profile set to Public
- Network discovery service not functioning properly
- Windows service state requiring restart

---

## Resolution

Restarted Veeam server, which restored network visibility of NAS share.

Backup job executed successfully after restart.

---

## Verification

- Confirmed NAS visible in File Explorer
- Verified NAS share accessible via UNC path
- Retried backup job successfully
- Confirmed backup completed without errors

---

## Lessons Learned

- NAS being reachable via browser does not guarantee SMB/file access is working.
- Network profile (Public vs Private) affects discovery and file sharing.
- Always test access via UNC path before troubleshooting Veeam itself.
- Restart can temporarily resolve service-level network discovery issues.
- Investigate underlying cause if issue repeats (avoid relying only on restart).

---

## Mistakes / Things to Avoid

- Assuming NAS is down without verifying via web interface
- Ignoring Windows network profile configuration
- Not checking SMB access before modifying Veeam configuration

---

## Related Concepts to Study

- Veeam repository configuration
- SMB protocol behavior
- Windows Network Profile (Public vs Private)
- Network Discovery services
- Backup repository troubleshooting
