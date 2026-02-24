# RDS Server Performance Issue – Browsers Crashing

## Environment
- Environment Type: Client
- Server OS: Windows Server 2019
- Service: Remote Desktop Services (RDS)
- Role: IT Support Intern

---

## Issue Summary

RDS server was running slowly, and web browsers (Firefox and Chrome) were becoming unresponsive and crashing.

---

## Detailed Problem

Observed symptoms:

- RDS sessions were slow for multiple users.
- Browsers froze or became unresponsive after opening.
- Network connectivity appeared normal.
- Issue affected multiple RDS users.

---

## Initial Analysis

Possible causes considered:

- High CPU or RAM utilization
- Multiple active RDS sessions consuming resources
- Corrupted browser profile or outdated browser version
- Pending Windows updates requiring restart
- Temporary system resource leak

---

## Troubleshooting Steps

1. Logged into RDS Server with administrative account.
2. Verified browser behavior (confirmed unresponsive state).
3. Monitored system resource usage:
   - Opened **Task Manager**
   - Checked **CPU usage**
   - Checked **Memory utilization**
   - Reviewed active RDS sessions
   - Identified high resource consumption
4. Checked system uptime.
5. Informed RDS users about planned restart.
6. Requested users to save their work.
7. Restarted RDS Server.
8. After reboot:
   - Verified CPU and memory returned to normal levels
   - Updated Firefox and Chrome
   - Tested browser functionality
9. Confirmed system performance returned to normal.
10. Notified users that system was operational.

---

## Root Cause

Likely temporary resource exhaustion or system instability due to:

- High memory usage
- Multiple active sessions
- Long uptime without restart
- Browser process instability

(Exact root cause not fully confirmed due to limited monitoring history.)

---

## Resolution

- Restarted RDS Server
- Updated web browsers
- Verified resource usage normalized

---

## Verification

- Browsers opened and functioned normally
- No crashes observed
- RDS sessions responsive
- CPU and memory usage within acceptable limits
- Users confirmed normal operation

---

## Lessons Learned

- Always monitor CPU and RAM before restarting a server.
- RDS servers require regular performance monitoring.
- Long uptime can lead to performance degradation.
- Restart can resolve temporary instability but should not replace root cause analysis.
- Keep browsers and applications updated in shared server environments.

---

## Mistakes / Things to Avoid

- Restarting without checking resource utilization
- Not reviewing Event Viewer logs
- Ignoring session limits and resource allocation
- Restarting without user communication

---

## Related Concepts to Study

- RDS session management
- Windows Performance Monitor (PerfMon)
- Event Viewer troubleshooting
- Memory leak detection
- Server capacity planning
