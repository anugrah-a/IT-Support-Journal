# Increase DHCP Scope (Expand IP Address Range)

## Change Summary
Expanded the existing DHCP IPv4 scope by increasing the available IP address range to accommodate additional devices.

---

## Environment
- Environment Type: Production
- Service: DHCP Server
- Server OS: Windows Server 2019

---

## Reason for Change

New devices were unable to obtain IP addresses.

The existing DHCP scope was fully utilized, causing devices to receive:

- APIPA address (169.254.x.x)
- No network connectivity

---

## Before Change

- Users reported network connectivity issues.
- Devices failed to obtain IP from DHCP server.
- Systems automatically assigned APIPA addresses.
- DHCP scope had no available IP addresses remaining.

---

## Change Performed

1. Opened **DHCP Management Console**
2. Navigated to: IPv4 → Existing Scope
3. Reviewed current IP range and utilization
4. Increased the IP address range by adding 50 additional IP addresses
5. Applied changes

---

## After Change

- Devices successfully obtained IP addresses from DHCP server.
- No further APIPA addresses observed.
- Network connectivity restored for affected devices.

---

## Validation

- Checked client device IP using:

```powershell
ipconfig
```
- Confirmed client IP address falls within the updated DHCP scope range
- Verified lease allocation in DHCP Management Console
- Ensured no scope conflicts or overlapping IP ranges exist
- Checked exclusion ranges and reservations for accuracy

---

## Rollback Plan

If issues occur after scope expansion:

1. Revert DHCP scope range to previous configuration
2. Remove newly added IP range
3. Review subnet configuration and exclusion ranges
4. Restart DHCP service (if required)
5. Validate client IP allocation after rollback

---

## Impact

- Restored IP address allocation for new devices
- Prevented further network connectivity outages
- Reduced risk of IP exhaustion
- Improved network capacity planning

---

## Lessons Learned

- Regularly monitor DHCP scope utilization.
- APIPA address (169.254.x.x) indicates DHCP failure.
- Capacity planning is critical as network devices increase.
- Ensure expanded IP range does not overlap with reserved or static IP addresses.
- Always document subnet details and exclusion ranges before modifying scope.
