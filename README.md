# Honeypot SSH Breach Detection & NIST Control Mapping

Windows honeypot deployment and SSH attack simulation with audit log analysis 
and firewall remediation, mapped to NIST 800-53 controls (AU-2, SI-4, AC-7, CA-7).

## Project Overview
Deployed a Windows 10 honeypot configured with OpenSSH to simulate and detect 
an SSH brute-force attack from a Kali Linux VM. Documented the full lifecycle 
from deployment and system hardening through attack simulation, detection via 
audit log analysis, and mitigation by blocking the attacker's source IP.

## GRC / Control Relevance
- **AU-2 / AU-6** (Event Logging & Audit Review) — detected activity via OpenSSH Event ID 4 and Windows Security Event ID 4624.
- **SI-4** (System Monitoring) — identified unauthorized access attempts through active log monitoring.
- **AC-7** (Unsuccessful Logon Attempts) — documented brute-force attempts and credential resilience testing via Hydra wordlist attack.
- **CA-7** (Continuous Monitoring) — demonstrated evidence collection and response workflow aligned to continuous monitoring methodology.

## Tools Used
- OpenSSH (Windows 10)
- Kali Linux / Hydra
- Windows Event Viewer
- Windows Defender Firewall (wf.msc)
- Nmap / Netstat

## Key Findings
- Successfully simulated an SSH brute-force attack from Kali VM (10.0.0.46) using Hydra with a custom wordlist.
- Detected activity via the OpenSSH operational log (Event ID 4), confirming attacker IP, username, and timestamp.
- Implemented a compensating control: custom inbound firewall rule blocking attacker IP (10.0.0.46) across all profiles.
- Confirmed mitigation: subsequent SSH connection attempt timed out.

## Artifacts
- [Honeypot Report (PDF)](Honeypot_Report_final.pdf)

## Note
*Developed as part of cybersecurity training. All simulations conducted in 
an isolated lab environment.*
