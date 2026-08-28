# CMPG325-client-CLI-080
Network Design Project for Boitumelo Family Law Practice

---

### Student Information

| **Aspect** | **Details** |
|------------|-------------|
| Student Name | Mokoka, Judas |
| Student Number | 32917406 |
| Project ID | 32917406 |
| Client ID | CMPG325-2026-080 / CLI-080 |
| Date | 28 August 2026 |

---

### Project Overview

This project involves designing, implementing, and simulating a computer network for **Boitumelo Family Law Practice**, a legal services firm in Rustenburg. The network has been designed to meet the specific needs of the client while addressing scalability requirements and a change request for guest Wi-Fi isolation.

---

### Client Profile

| **Aspect** | **Details** |
|------------|-------------|
| Organisation | Boitumelo Family Law Practice |
| Location | Rustenburg |
| Industry | Legal Services |
| Client ID | CLI-080 |
| Addressing Block | 10.33.0.0/16 |

---

### Key Requirements Fulfilled

| # | Requirement | Status |
|---|-------------|--------|
| 1 | Use assigned addressing block (10.33.0.0/16) | ✅ Designed |
| 2 | Provide connectivity for all staff | ✅ Designed |
| 3 | DHCP for multi-VLAN address assignment | ✅ Designed |
| 4 | Design for scalability (future floor) | ✅ Designed |
| 5 | Guest Wi-Fi isolated from internal resources (CR3) | ✅ Designed (ACL) |
| 6 | Implement in Cisco Packet Tracer | 🔄 In Progress |
| 7 | Document in GitHub | ✅ This Repository |

---

### Network Design Summary

#### VLANs Implemented

| VLAN ID | Name | Subnet | Purpose |
|---------|------|--------|---------|
| 10 | Staff_Data | 10.33.10.0/24 | Staff desktops and wired devices |
| 20 | Staff_WiFi | 10.33.20.0/24 | Staff wireless devices |
| 30 | Guest_WiFi | 10.33.30.0/24 | Visitor Wi-Fi (CR3 - Isolated) |
| 99 | Management | 10.33.99.0/24 | Network device management |
| 100 | Servers | 10.33.100.0/24 | Infrastructure servers |

#### Key Technologies

- **Cisco Packet Tracer** for simulation
- **VLANs** for network segmentation
- **Inter-VLAN Routing** (Layer 3 switch)
- **DHCP Scoped Multi-VLAN** address assignment
- **ACLs** for Guest isolation (CR3)
- **Hierarchical Star** topology

---

### Repository Structure
