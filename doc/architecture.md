# Network Security Lab — IDS/IPS Monitoring with Suricata & Fail2ban
## Architecture Overview
This lab simulates a real-world network attack scenario across two isolated subnets, with an Ubuntu server acting as a monitored gateway between an attacker and a vulnerable target.

## Components
 Metasploitable 2192.168.10.10Intentionally vulnerable target

| Host     | IP       | Role     |
|:---------|:--------:|---------:|
| Kali Linux     | 192.168.20.10    | Attacker — runs scans, exploits    |
| Ubuntu Server     | 192.168.20.1 / 192.168.10.1    | Gateway with Suricata IDS + Fail2ban    |
| Metasploitable     | 192.168.10.10   | Intentionally vulnerable target   |

## What This Lab Demonstrates
Intrusion Detection — Suricata inspects traffic passing through the Ubuntu gateway and generates alerts for suspicious activity (port scans, exploit attempts, etc.)

Intrusion Prevention — Fail2ban reads Suricata logs and automatically blocks offending IPs via iptables

Attack Simulation — Kali launches real attacks (Nmap, Metasploit, etc.) against Metasploitable to trigger detection rules

Network Segmentation — Two separate subnets isolate attacker from victim, with all traffic routed through the monitored server

## Network Topology
Network 1 (192.168.10.0/24) — Internal network hosting the vulnerable target

Network 2 (192.168.20.0/24) — External/attacker network