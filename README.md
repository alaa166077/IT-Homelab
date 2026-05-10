# IT-Homelab

Building a SOC and network security homelab using OPNsense, Kali Linux, Wazuh, MISP, TheHive, Cortex, IDS/IPS, and centralized monitoring.

---

# Objectives

- Build a realistic SOC environment
- Practice network security engineering
- Deploy monitoring and threat detection tools
- Learn firewalling, IDS/IPS, SIEM, and incident response workflows
- Develop troubleshooting and infrastructure documentation skills

---

# Current Progress

## Completed

- VirtualBox environment setup
- OPNsense installation and persistent boot configuration
- UFS filesystem deployment
- WAN/LAN network configuration
- Internal Network architecture setup
- Kali Linux VM deployment
- Windows 10 client VM deployment
- Suricata IDS/IPS deployment and custom rule validation
- Transparent HTTP/HTTPS Web Proxy configuration (Squid + SquidGuard)
- SSL inspection and certificate authority setup
- Category-based web filtering with ACL blacklists
- Firewall rules for proxy bypass prevention

## In Progress

- High Availability (HA) / CARP / pfSync configuration
- Multi-WAN failover and load balancing

## Planned

- Wazuh SIEM deployment
- MISP threat intelligence platform
- TheHive incident response platform
- Cortex analyzer integration

---

# Current Network Architecture

```
Internet
│
VirtualBox NAT
│
OPNsense WAN (em0)
│
OPNsense LAN (em1) — 10.200.200.254/24
│
Internal Network (Intnet)
├── Kali Linux        — 10.200.200.10
└── Windows 10 Client — 10.200.200.20
```

> All client VMs use OPNsense as their sole gateway and DNS server.
> Client VMs must not have secondary NAT adapters to ensure all traffic flows through OPNsense security controls.

---

# Technologies Planned

- OPNsense Firewall
- Kali Linux
- Suricata IDS/IPS
- Squid Web Proxy + SquidGuard
- Wazuh
- MISP
- TheHive
- Cortex
- HA / CARP / pfSync
- Multi-WAN Failover and Load Balancing

---

# Repository Structure

- `README.md` — Main project overview and progress tracking
- `opnsense` — OPNsense deployment, configuration, and troubleshooting notes

---

# Notes

This repository documents the deployment process, troubleshooting methodology, architectural decisions, and lessons learned while building the SOC homelab environment. Each section reflects real configuration challenges encountered and resolved during the build process.
