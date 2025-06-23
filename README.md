# cybersecurity_internship
# Task 1: Port Scanning & Packet Analysis

## Tools Used
- Kali Linux (VM on VMware)
- Nmap
- Wireshark

## What I Did
- Scanned my local network `192.168.194.0/24` using Nmap to detect live hosts and open ports.
- Ran:sudo nmap -sS 192.168.194.0/24
- Captured network packets using Wireshark while the scan was running.
- Saved scan output and screenshots for documentation.

##IP Addresses and Open Ports Found

| IP Address        | Open Port | Service |
|------------------|-----------|---------|
| 192.168.194.1     | 3306/tcp  | MySQL   |
| 192.168.194.254   | None      | —       |
| 192.168.194.128   | None      | —       |

##  Security Insights
- **MySQL (port 3306)** open on 192.168.194.1 — a potential security risk if exposed publicly.
- Other devices had no open ports or were filtered, likely protected by firewalls.

## 📊 Wireshark Packet Analysis
- Captured packets on interface `eth0` during the scan.
- Applied display filter:tcp.flags.syn == 1 && tcp.flags.ack == 0
to view SYN packets sent during the Nmap scan.
- This helped confirm Nmap’s behavior and active port scanning.

## Folder contains:-
- `scan_results.txt – Nmap scan output
- `nmap_scan.png – Screenshot of terminal running Nmap
- `wireshark_capture.png – Screenshot of SYN packets in Wireshark

