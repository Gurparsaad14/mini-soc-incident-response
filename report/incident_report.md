## Summary
There were multiple failed SSH authentication attempts detected on an Ubuntu host. The time between each attempt was short, possibly indicating brute-force activity.

## What Happened
- There were multiple SSH failures within the same time window.
- Events were collected from auth logs and analysed using Linux CLI triage and SQLite queries.\

## Evidence
- Raw evidence: `raw_logs/auth.log`
- CLI outputs: `analysis/failed_ssh_attempts.txt`, `analysis/auth_timeline.txt`
- SQL results: `analysis/sql_results.txt`
- Key metric: **22 failed SSH attempts** (SQLite query)

## Impact
- There was no successful compromise in the controlled lab.

## Recommendations (NIST CSF)
- **Protect:** Disable password authentication for SSH; require SSH keys. Enforce strong password policy for local accounts.
- **Protect/Detect:** Implement rate limiting / lockouts (e.g., fail2ban) for repeated authentication failures.
- **Detect:** Centralise logs into a SIEM and alert on abnormal spikes of failed SSH logins.
- **Respond:** Document triage steps (confirm source IP, frequency, targeted accounts) and escalation thresholds.
- **Recover:** Review access controls and rotate credentials if compromise is suspected; verify SSH configuration baseline.
