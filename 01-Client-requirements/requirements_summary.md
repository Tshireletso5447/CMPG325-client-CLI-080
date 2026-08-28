# Client Requirements Summary

## Core Networking Requirements

### a) Connectivity Requirements
- Provide reliable wired connectivity for all staff workstations
- Provide wireless connectivity for staff laptops and mobile devices
- Enable seamless internal communication for file sharing and collaboration
- Provide internet access for legal research, email, and court submissions

### b) Addressing Requirements
- **Assigned addressing block:** `10.33.0.0/16`
- All IP addresses must be derived from this block
- Efficient subnetting must minimize wasted addresses
- Subnets must accommodate current and future needs

### c) Network Services Requirements
- **DHCP** must be implemented (Scoped multi-VLAN address assignment)
- Automatic IP address assignment simplifies network management
- Different DHCP scopes must serve different VLANs

### d) Security Requirements
- Sensitive client data must be protected at all times
- Network segmentation to separate different types of traffic
- Guest users must not have access to internal resources
- Management traffic must be isolated from user traffic

### e) Staff Requirements

| **Staff Category** | **Access Needs** | **Priority** |
|-------------------|------------------|--------------|
| Lawyers | Legal databases, case management, email | Critical |
| Paralegals | Research tools, document management | High |
| Administrative Staff | Scheduling, billing, office apps | Medium |
| Support Staff | Reception, filing, email | Medium |
| Visitors/Clients | Internet access only (Guest Wi-Fi) | Low |

## Design Constraint

| **Constraint** | **Implication** |
|----------------|-----------------|
| An additional floor may be occupied next financial year | Network must be scalable for future expansion |

## Change Request (CR3)

| **Requirement** | **Details** |
|-----------------|-------------|
| Guest Wi-Fi must be added for visitors | Visitors need internet access while waiting |
| Isolation from internal resources | Guest Wi-Fi must be completely separate from internal network |
| Implementation method | VLAN segmentation and Access Control Lists (ACLs) |

## Requirements Priority Summary

| # | Requirement | Priority |
|---|-------------|----------|
| 1 | Use assigned addressing block 10.33.0.0/16 | Critical |
| 2 | Provide connectivity for all staff members | Critical |
| 3 | Implement DHCP for automatic IP assignment | Critical |
| 4 | Support multiple VLANs with separate DHCP scopes | Critical |
| 5 | Be scalable for future expansion (additional floor) | High |
| 6 | Provide guest Wi-Fi isolated from internal resources (CR3) | High |
| 7 | Be implemented in Cisco Packet Tracer | Required |
| 8 | Be documented in a GitHub portfolio | Required |
