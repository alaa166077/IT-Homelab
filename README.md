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

## In Progress

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
VirtualBox NAT Network (simulated ISP/WAN)
│
┌─────────────────────────────────────┐
│     WAN CARP Virtual IP (shared)    │
│  OPNsense Master — OPNsense Backup  │
│  (Active)              (Passive)    │
│         pfSync Sync Network         │
│     LAN CARP Virtual IP (shared)    │
└─────────────────────────────────────┘
│
Internal Network (Intnet) — 10.200.200.0/24
├── Kali Linux        — 10.200.200.10
└── Windows 10 Client — 10.200.200.20
```

> All client VMs use the shared LAN CARP Virtual IP as their gateway.
> Client VMs must not have secondary NAT adapters to ensure all traffic flows through OPNsense security controls.

---

# Technologies Planned

- OPNsense Firewall
- Kali Linux
- Suricata IDS/IPS
- Squid Web Proxy + SquidGuard
- CARP / pfSync / High Availability
- Wazuh (planned)
- MISP (planned)
- TheHive (planned)
- Cortex (planned)
- Multi-WAN Failover and Load Balancing (in progress)

---

# Repository Structure

- `README.md` — Main project overview and progress tracking
- `opnsense` — OPNsense firewall deployment, IDS/IPS, and proxy configuration
- `high-availability` — CARP, pfSync, and HA cluster configuration and validation

---

# Notes

This repository documents the deployment process, troubleshooting methodology, architectural decisions, and lessons learned while building the SOC homelab environment. Each section reflects real configuration challenges encountered and resolved during the build process.
