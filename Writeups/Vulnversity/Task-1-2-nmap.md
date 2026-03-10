# Vulnversity Commands

## Task 1-2: Reconnaissance

## Scan IP

```bash
nmap -sV -Pn [ip] -oA full_scan

About Nmap
Nmap (Network Mapper) is a powerful network scanning tool used for:

Discovering active devices on a network.

Scanning for open ports.

Identifying services and their versions running on open ports.

Detecting the operating system of the target.

Option Breakdown
-sV – Enables version detection: probes open ports to determine service/version information.

-Pn – Skips the host discovery phase (no ping). Treats all hosts as online. Useful when the target blocks ICMP ping requests.

-oA full_scan – Outputs the scan results in all formats (normal, XML, and grepable) with the base filename full_scan.
