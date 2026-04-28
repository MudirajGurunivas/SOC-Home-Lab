# Incident Report - Brute Force Attack Detection

## Incident Details
- Date: April 27, 2026
- Severity: High
- Type: Brute Force Attack
- Status: Detected

## Summary
A brute force SSH attack was simulated against the Ubuntu 
virtual machine. The attacker attempted multiple failed 
login attempts using common passwords. The attack was 
successfully detected using Splunk SIEM.

## Timeline
- 21:27 - Attack started using Hydra tool
- 21:27 - Multiple failed SSH login attempts generated
- 21:28 - Splunk detected failed password attempts
- 21:28 - Brute Force Detection alert triggered

## Attack Details
- Attack Type: SSH Brute Force
- Tool Used: Hydra v9.5
- Target: 127.0.0.1 (local machine)
- Username attempted: fakeuser, root
- Passwords tried: rockyou.txt wordlist

## Detection Method
- SIEM Tool: Splunk Enterprise
- Log Source: /var/log/auth.log
- Search Query: index=main "Failed password" | stats count by host
- Alert Name: Brute Force Detection
- Trigger Condition: More than 5 failed login attempts

## Impact Analysis
- No valid credentials were found
- No unauthorized access was gained
- System integrity maintained

## Recommendations
1. Implement account lockout after 3 failed attempts
2. Disable SSH password authentication, use SSH keys instead
3. Implement fail2ban to automatically block attacking IPs
4. Monitor auth.log continuously using SIEM
5. Use strong unique passwords on all accounts

## Lessons Learned
- Brute force attacks are clearly visible in authentication logs
- SIEM tools can detect attacks in real time
- Early detection prevents unauthorized access
- Proper alerting is critical in a SOC environment

## Analyst
- Name: Gurunivas
- Role: SOC Analyst (Home Lab)
- Date: April 27, 2026
