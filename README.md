
# *teckie1 HomeLab - Proxmox Cyberlab architecture*

>*Segmentatation - Self-hosted - Learning focused*
# Overview 

This homelab is built around Proxmox VE as the central platform, replacing TrueNAS Scale. 

The goal was to create a modular hybrid environment that separates:
- Family services (stable + secure).
- Cybersecurity lab (isolated + flexible).
- Personal development workflows (arch+swayFX).

Primary hardware: Abyss.
Network stack: TP-Link Omada (ER605 + Managed POE switch + EAP Access Point). 

# Core infrastructure 
- Hypervisor: Proxmox VE
- Single-pane management for LXC’s and VM’s
- Snapshot based workflows
- VLAN aware networking

# Network design
- Default LAN: trusted devices + core services 
- VLAN-20 — Cyberlab
  - Isolated testing environment
  - Kali VM + vulnerable targets
- Static DHCP assignments for infrastructure nodes 
- Remote access
  - WireGuard 
  - Cloudflare tunnels

# Virtualization Layout

# Containers (LXC)

- SMB/NFS file share (Privileged LXC)
  - Shared storage
  - Woke/media separation from Nextcloud
- Nextcloud (unprivileged LXC)
  - Family cloud
  - Mobile sync + external access
- ZNC bouncer 
  - Persistent IRC sessions
  - Accessible via WireGuard 

# Virtual Machines
- Kali Linux (Cyberlab testing)
- Future SOC/SIEM + ( maybe Azure lab integration)
- Additional isolated lab targets (planned)

# Storage architecture 
- External SSD used for migration staging
- SMB shares separated from application storage
- Notes synced across multiple devices 
- Focuses on 
  - Snapshots
  - Reproducibility 

# Security & Access 
- Internal-first service exposure 
- Cloudflare tunnel for selective public end points
- WireGuard for administration access
- VLAN segmentation for lateral movement

# Workstation environment 
- Arch Linux
- SwayFX (wayland)
- Waybar + pywal theming 
- ZSH shell
- Neovim used as:
  - IDE for python learning
  - Knowledge base
  - work/Personal/School Notes

# Cyberlab Direction
- Dedicated VLAN
- Offensive security practice
- Planned integrations:
  - SOC lab
  - Monitoring stack 
  - SIEM experimentation


# Planned hardware direction
- Expanded PoE capacity for: 
  - Outdoor cameras
  - Additional AP’s
- “Mad scientist lab” workspace
- Improved network visualization + documentation 

# Design goals
- Modular services (LXC first where possible)
- Strong segmentation between Cyberlab and Homelab
- Reduce single points of failure 
- Documentation first workflow (~/Notes, GitHub)

*Philosophy*: Build. Break. Learn. Repeat.





