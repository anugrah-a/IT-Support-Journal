# Client Performance Issue – High Memory Usage (Browser Crashes)

---

## Environment
- Environment Type: User Workstation
- Operating System: Windows 10
- Hardware: 8 GB RAM, HDD Storage
- Role: IT Support Intern

---

## Issue Summary

User reported:

- Browser crashes
- Slow system performance
- System becoming unresponsive when multiple browser tabs were open

---

## Purpose

Diagnose memory-related performance issue and recommend appropriate solution.

---

## Pre-Requisites

- Remote access to user's computer (TeamViewer)
- Administrative access (if required)

---

## Troubleshooting Steps

1. Logged into user's computer via remote support.
2. Checked browser version and updated to latest version.
3. Opened **Task Manager → Performance tab**.
4. Monitored:
   - Memory usage
   - CPU usage
   - Disk activity
5. Checked for pending Windows Updates.
6. Opened multiple websites in browser to simulate user behavior.
7. Observed memory usage increasing significantly.
8. Noted that available RAM dropped to very low levels when multiple tabs were open.
9. Identified system configuration:
   - Windows 10
   - 8 GB RAM
   - HDD (non-SSD)

---

## Findings

- High memory consumption when using multiple browser tabs.
- HDD storage causing slower paging and system response.
- 8 GB RAM insufficient for heavy browser usage.
- System relying on paging file due to limited RAM.

---

## Root Cause

Hardware limitation:

- Insufficient RAM (8 GB)
- Mechanical HDD causing slow disk I/O
- High browser memory consumption

---

## Resolution

### Temporary Solution

- Advised user to:
  - Keep minimum required tabs open
  - Close unnecessary background applications

### Permanent Recommendation

- Upgrade system to:
  - Minimum **16 GB RAM**
  - **SSD storage**
  - Windows 11 (if hardware supports)

---

## Verification

- User confirmed system usable when limiting browser tabs.
- Memory usage stabilized with fewer open applications.

---

## Lessons Learned

- Always monitor resource usage before assuming software issue.
- 8 GB RAM may be insufficient for heavy browser workloads.
- HDD significantly impacts system performance under memory pressure.
- Task Manager and Resource Monitor are critical troubleshooting tools.
- Hardware upgrades can be the correct long-term solution.

---

## Common Mistakes / Things to Avoid

- Blaming browser without checking memory usage.
- Ignoring disk performance impact.
- Not verifying hardware configuration.
- Reinstalling software unnecessarily without analyzing resource usage.

---

## Related Concepts

- Windows Memory Management
- Paging File / Virtual Memory
- Disk I/O performance
- Resource Monitor usage
- Capacity Planning
