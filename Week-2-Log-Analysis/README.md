# SSH Failed Login Activity – SOC Analysis

## Objective
To understand how Linux authentication logs are used by a SOC analyst to detect suspicious login activity.

## Environment
- Operating System: Kali Linux
- Log Source: systemd journal
- Service: OpenSSH (SSH)

## Logs Analyzed
- journalctl (SSH related logs)
- sshd-session authentication events

## Observed Events
Multiple failed SSH login attempts were observed using an invalid username.

Example log entries:
- Failed password for invalid user
- Invalid user login attempts
- Repeated failures from the same source

## Analysis
The logs show repeated failed authentication attempts within a short time window.
Such behavior is commonly associated with brute-force attacks.
In this case, the source IP address was `::1` (localhost), confirming the activity was generated locally for testing and learning purposes.

## Conclusion
No real attack was detected.
The failed login attempts were intentionally generated to understand how SSH brute-force attempts appear in logs.

## Recommendations
- Monitor SSH authentication logs regularly
- Disable SSH service when not required
- Implement protections such as fail2ban
- Use strong passwords or key-based authentication
