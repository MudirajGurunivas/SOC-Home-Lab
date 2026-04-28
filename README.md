# SOC Home Lab 🛡️

## About
I built a home SOC (Security Operations Center) lab from scratch 
to detect simulated cyber attacks using industry-standard tools.
This project demonstrates real blue team skills used by SOC analysts daily.

## Tools Used
- VirtualBox - Virtual machine platform
- Ubuntu 24.04 - Linux operating system
- Splunk Enterprise - SIEM tool for log analysis and detection
- Hydra - Attack simulation tool
- OpenSSH - Used to simulate brute force attacks

## What I Did
1. Set up a virtual machine running Ubuntu 24.04
2. Installed and configured Splunk Enterprise SIEM
3. Configured Splunk to monitor /var/log/auth.log
4. Simulated a brute force SSH attack using Hydra
5. Detected failed login attempts in Splunk
6. Built a custom detection alert in Splunk

## Detection Rules Built
### Brute Force Detection
- Tool: Splunk
- Query: index=main "Failed password" | stats count by host
- Alert triggers when: more than 5 failed login attempts detected
- Purpose: Detects SSH brute force attacks in real time

## What I Learned
- How SIEM tools collect and analyze security logs
- How brute force attacks appear in authentication logs
- How to build detection rules and alerts in Splunk
- How Linux authentication logs work (/var/log/auth.log)
- Real workflow of a SOC analyst

## Project Status
- [x] Virtual machine set up
- [x] Ubuntu 24.04 installed
- [x] Splunk installed and configured
- [x] Attack simulated using Hydra
- [x] Detection rule built in Splunk

## Author
Aspiring SOC Analyst | Cybersecurity Student
