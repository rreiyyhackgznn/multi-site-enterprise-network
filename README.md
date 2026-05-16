# Multi-Site Enterprise Network

A multi-building enterprise network simulation built in Cisco Packet Tracer,
connecting three sites over WAN links with full VLAN segmentation, dynamic
routing, centralized server infrastructure, and layered security policies.

## Overview

This project simulates a real-world multi-site enterprise environment with
three buildings: Management (Yönetim), Server Services (Sunucu Hizmet), and
Production/Marketing (Üretim/Pazarlama). Sites are interconnected via WAN
links using OSPF for dynamic routing, with VTP for centralized VLAN management.

## Technologies Used

- **Routing:** OSPF, Inter-VLAN Routing
- **Switching:** VTP (Server/Client), Trunk & Access Ports, STP
- **VLANs:** VLAN 10 (PC), VLAN 20 (NB), VLAN 30 (IP TLF), VLAN 40 (PCLER),
  VLAN 50 (NB), VLAN 60 (YAZICILAR), VLAN 70 (WEB+DNS), VLAN 99/100/101 (MGMT)
- **Security:** ACL, Port Security, DHCP Snooping, MAC Address Sticky
- **Services:** DHCP, DNS, Web Server, Syslog
- **Voice:** IP Phones (Cisco 7960)

## Network Topology

| Site | Devices | Subnet Range |
|------|---------|--------------|
| Yönetim Binası | L3 Switch, 3 Access Switches, IP Phones, PCs | 192.168.10-30.0/24 |
| Sunucu Hizmet Binası | Web+DNS Server, DHCP Server | 192.168.70-100.0/24 |
| Üretim/Pazarlama Binası | L3 Switch, Access Switches, Printers | 192.168.40-60.0/24 |

## WAN Links

| Link | Subnet |
|------|--------|
| R1 — R2 | 2.2.2.0/30 |
| R2 — R3 | 3.3.3.0/30 |

## Key Configurations

- **OSPF:** Dynamic routing across all three sites
- **VTP:** Centralized VLAN management (Server/Client mode)
- **ACL:** Admin full access; users restricted to required ports only; deny ip any any
- **DHCP Snooping:** Enabled on user VLANs (10, 20, 30)
- **Port Security:** MAC sticky with violation shutdown
- **Syslog:** Centralized logging to 192.168.70.2
- **IP Phones:** Voice VLAN configured on access switches

## Files

| File | Description |
|------|-------------|
| `vlan-inter vlan routing-vtp-dhcp-ACL-port security.pkt` | Main Packet Tracer file |

## How to Open

1. Download and install [Cisco Packet Tracer](https://www.netacad.com/courses/packet-tracer)
2. Open the `.pkt` file
3. Use Simulation Mode to test inter-site traffic and ACL policies
