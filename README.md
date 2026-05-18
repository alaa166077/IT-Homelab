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
- WAN/LAN network configuration and Internal Network architecture
- Kali Linux VM deployment
- Windows 10 client VM deployment
- Suricata IDS/IPS deployment and custom rule validation
- Transparent HTTP/HTTPS Web Proxy configuration (Squid + SquidGuard)
- SSL inspection and certificate authority setup
- Category-based web filtering with ACL blacklists
- High Availability firewall cluster (CARP + pfSync)
- CARP Virtual IP configuration on WAN and LAN interfaces
- pfSync state synchronization and XML-RPC configuration replication
- Failover validation through live traffic interruption testing
- Multi-WAN failover with Gateway Groups and policy-based routing
- Ubuntu Server 24.04 LTS deployment with static IP and SSH access
- Wazuh v4.14.5 all-in-one deployment (server + indexer + dashboard)
- Wazuh agent deployed on Windows 10 and Ubuntu Server
- Docker Engine installation on dedicated Ubuntu SOC Server
- TheHive 5.2 deployment via Docker Compose
- Cortex deployment via Docker Compose
- MISP deployment via Docker Compose

## Planned

- TheHive and Cortex integration
- MISP and TheHive integration
- Wazuh and TheHive integration

---

# Current Network Architecture

```
Internet
│
VirtualBox NAT (WAN)
│
OPNsense Firewall — 10.200.200.254/24
│
Internal Network (intnet) — 10.200.200.0/24
├── Kali Linux          — 10.200.200.10
├── Windows 10 Client   — 10.200.200.20
├── Ubuntu Server       — 10.200.200.21  (Wazuh agent)
├── Wazuh v4.14.5       — 10.200.200.5   (SIEM + XDR)
└── Ubuntu SOC Server   — 10.200.200.253 (TheHive + Cortex + MISP)
```

> All VMs use OPNsense as their sole gateway and DNS server.
> No secondary NAT adapters on any VM.

---

# Technologies

- OPNsense Firewall
- Kali Linux
- Suricata IDS/IPS
- Squid Web Proxy + SquidGuard
- CARP / pfSync / High Availability
- Multi-WAN Failover
- Wazuh SIEM + XDR
- Docker + Docker Compose
- TheHive 5.2
- Cortex
- MISP
- Ubuntu Server 24.04 LTS

---

# Repository Structure

- `README.md` — Project overview and progress tracking
- `opnsense` — Firewall deployment, IDS/IPS, and proxy configuration
- `high-availability` — CARP, pfSync, and HA cluster configuration
- `multi-wan` — Multi-WAN failover and Gateway Groups
- `wazuh` — Wazuh SIEM deployment and agent installation
- `thehive-cortex-misp` — TheHive, Cortex, and MISP Docker deployment

---

# Notes

This repository documents the deployment process, troubleshooting methodology, architectural decisions, and lessons learned while building the SOC homelab. Each section reflects real configuration challenges encountered and resolved during the build.
