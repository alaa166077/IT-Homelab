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
- OPNsense installation
- UFS filesystem deployment
- Persistent boot issue resolution
- WAN/LAN network configuration
- Internal Network architecture setup
- Kali Linux VM deployment

---

# Current Network Architecture

Internet
│
VirtualBox NAT
│
OPNsense WAN
│
OPNsense LAN (10.200.200.254/24)
│
Internal Network (Intnet)
│
Kali Linux

---

# Technologies Planned

- OPNsense Firewall
- Kali Linux
- Suricata IDS/IPS
- Wazuh
- MISP
- TheHive
- Cortex
- HA / CARP / pfSync
- Proxy and Web Filtering

---

# Repository Structure

- README.md → Main project overview
- opnsense → OPNsense deployment and troubleshooting notes

---

# Notes

This repository documents the deployment process, troubleshooting methodology, architectural decisions, and lessons learned while building the SOC homelab environment.
