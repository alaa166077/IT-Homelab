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
- High Availability firewall cluster (CARP + pfSync)
- CARP Virtual IP configuration on WAN and LAN interfaces
- pfSync firewall state synchronization between Master and Backup nodes
- XML-RPC configuration replication
- Outbound NAT with shared WAN Virtual IP for session continuity
- Failover validation through live traffic interruption testing
- Multi-WAN failover with Gateway Groups and policy-based routing
- Failover validation through live WAN interface failure simulation
- Ubuntu Server 24.04 LTS deployment with static IP and SSH access
- Wazuh v4.14.5 all-in-one deployment (server + indexer + dashboard)
- Wazuh dashboard accessible via HTTPS
- Wazuh agent deployed on Windows 10 client
- Wazuh agent deployed on Ubuntu Server

## In Progress

- MISP threat intelligence platform deployment

## Planned

- MISP threat intelligence platform
- TheHive incident response platform
- Cortex analyzer integration

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
├── Kali Linux        — 10.200.200.10
├── Windows 10 Client — 10.200.200.20
├── Ubuntu Server     — 10.200.200.21
└── Wazuh v4.14.5     — 10.200.200.5
```

> All VMs use OPNsense as their sole gateway (10.200.200.254) and DNS server.
> No secondary NAT adapters on any VM — all traffic flows through OPNsense.

---

# Technologies

- OPNsense Firewall
- Kali Linux
- Suricata IDS/IPS
- Squid Web Proxy + SquidGuard
- CARP / pfSync / High Availability
- Multi-WAN Failover and Load Balancing
- Wazuh SIEM + XDR
- Ubuntu Server 24.04 LTS
- MISP (in progress)
- TheHive (planned)
- Cortex (planned)

---

# Repository Structure

- `README.md` — Main project overview and progress tracking
- `opnsense` — OPNsense firewall deployment, IDS/IPS, and proxy configuration
- `high-availability` — CARP, pfSync, and HA cluster configuration and validation
- `multi-wan` — Multi-WAN failover, Gateway Groups, and policy-based routing
- `wazuh` — Wazuh SIEM deployment, agent installation, and configuration

---

# Notes

This repository documents the deployment process, troubleshooting methodology, architectural decisions, and lessons learned while building the SOC homelab environment. Each section reflects real configuration challenges encountered and resolved during the build process.
