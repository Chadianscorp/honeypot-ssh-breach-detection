# honeypot-ssh-breach-detection
Windows honeypot deployment and SSH breach simulation with audit log analysis and firewall remediation — mapped to NIST 800-53 controls (AU-2, SI-4, AC-7, CA-7)
# Honeypot SSH Breach Detection & NIST Control Validation

## Project Overview
Deployed a Windows 10 honeypot configured with OpenSSH to simulate and detect 
an SSH brute-force attack from a Kali Linux VM. Documented the full lifecycle 
from deployment and system hardening through breach simulation, detection via 
audit log analysis, and mitigation by blocking the attacker's source IP.

## GRC / Control Relevance
This project demonstrates practical validation of the following NIST SP 800-53 
Rev. 5 controls:
- **AU-2 / AU-6** (Event Logging & Audit Review) — detected breach via OpenSSH 
  Event ID 4 and Windows Security Event ID 4624
- **SI-4** (System Monitoring) — identified unauthorized access attempt through 
  active log monitoring
- **AC-7** (Unsuccessful Logon Attempts) — documented brute-force attempts and 
  credential resilience testing
- **CA-7** (Continuous Monitoring) — demonstrated evidence collection and 
  response workflow aligned to continuous monitoring methodology

## Tools Used
- OpenSSH (Windows 10)
- Kali Linux / Hydra
- Windows Event Viewer
- Windows Defender Firewall (Wf.msc)
- Nmap / Netstat

## Key Findings
- Successfully simulated SSH brute-force attack from Kali VM (10.0.0.46)
- Detected breach via OpenSSH operational log (Event ID 4) confirming 
  attacker IP, username, and timestamp
- Implemented compensating control: custom inbound firewall rule blocking 
  attacker IP across all profiles unconditionally
- Confirmed mitigation: subsequent SSH connection attempt timed out

## Artifacts
- [Honeypot Report (PDF)](Honeypot_Report_final.pdf)

## Note
*Developed as part of cybersecurity training. All simulations conducted in 
an isolated lab environment.*
