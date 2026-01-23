# SSH Failed Login Activity – SOC Analysis

## Objective
To analyze Linux authentication logs and identify failed SSH login attempts.

## Environment
- OS: Kali Linux
- Log Source: systemd journal (SSH logs)

## Tools Used
- journalctl
- grep
- SSH service

## Methodology
1. Generated SSH login attempts using an invalid user.
2. Monitored system logs using journalctl.
3. Filtered failed authentication attempts using grep.

## Findings
- Multiple failed SSH login attempts detected.
- Invalid user "testuser" attempted to authenticate.
- Source IP address was ::1 (localhost).
- Repeated failures indicate possible brute-force or user enumeration activity.

## Conclusion
The system successfully logged and detected unauthorized SSH login attempts. Log analysis confirms that authentication failures are clearly recorded and traceable.

## Recommendations
- Disable SSH access for unused users.
- Implement fail2ban to block repeated failed attempts.
- Monitor SSH logs continuously in SOC environments.

