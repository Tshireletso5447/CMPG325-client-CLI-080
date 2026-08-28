# IP Addressing Plan

## Assigned Block
**10.33.0.0/16**

## Subnetting Summary
| **Aspect** | **Value** |
|------------|-----------|
| Original Block | 10.33.0.0/16 (65,536 addresses) |
| Subnet Mask Used | /24 (255.255.255.0) |
| Addresses per Subnet | 256 (254 usable) |
| Subnets Used | 5 |
| Addresses Used | 1,280 |
| Addresses Reserved | 64,256 |

## Complete IP Addressing Plan
| **VLAN** | **Subnet** | **Network** | **Usable Range** | **Broadcast** | **Gateway** |
|----------|------------|-------------|------------------|---------------|-------------|
| VLAN 10 | 10.33.10.0/24 | 10.33.10.0 | 10.33.10.1 - 254 | 10.33.10.255 | 10.33.10.1 |
| VLAN 20 | 10.33.20.0/24 | 10.33.20.0 | 10.33.20.1 - 254 | 10.33.20.255 | 10.33.20.1 |
| VLAN 30 | 10.33.30.0/24 | 10.33.30.0 | 10.33.30.1 - 254 | 10.33.30.255 | 10.33.30.1 |
| VLAN 99 | 10.33.99.0/24 | 10.33.99.0 | 10.33.99.1 - 254 | 10.33.99.255 | 10.33.99.1 |
| VLAN 100 | 10.33.100.0/24 | 10.33.100.0 | 10.33.100.1 - 254 | 10.33.100.255 | 10.33.100.1 |

## Static Device Assignments
| **Device** | **Interface** | **IP Address** | **VLAN** |
|------------|---------------|----------------|----------|
| R1 (Core Router) | G0/0 | 10.33.100.254 | VLAN 100 |
| R1 (Core Router) | S0/0/0 | 203.0.113.2 | N/A |
| D1 (Distribution) | SVI VLAN 10 | 10.33.10.1 | VLAN 10 |
| D1 (Distribution) | SVI VLAN 20 | 10.33.20.1 | VLAN 20 |
| D1 (Distribution) | SVI VLAN 30 | 10.33.30.1 | VLAN 30 |
| D1 (Distribution) | SVI VLAN 99 | 10.33.99.1 | VLAN 99 |
| D1 (Distribution) | SVI VLAN 100 | 10.33.100.1 | VLAN 100 |
| DHCP Server | FastEthernet0 | 10.33.100.10 | VLAN 100 |
| AS-1 | VLAN 99 | 10.33.99.10 | VLAN 99 |
| AS-2 | VLAN 99 | 10.33.99.11 | VLAN 99 |
| AP-1 (Internal) | FastEthernet0 | 10.33.99.20 | VLAN 99 |
| AP-2 (Guest) | FastEthernet0 | 10.33.99.21 | VLAN 99 |
| ISP Router | S0/0/0 | 203.0.113.1 | N/A |

## DHCP Configuration (3 Scopes)
| **Scope Name** | **VLAN** | **Pool Network** | **Gateway** | **DNS** | **Lease** |
|----------------|----------|------------------|-------------|---------|-----------|
| DHCP_STAFF_DATA | VLAN 10 | 10.33.10.0/24 | 10.33.10.1 | 8.8.8.8 | 24h |
| DHCP_STAFF_WIFI | VLAN 20 | 10.33.20.0/24 | 10.33.20.1 | 8.8.8.8 | 24h |
| DHCP_GUEST_WIFI | VLAN 30 | 10.33.30.0/24 | 10.33.30.1 | 8.8.8.8 | 8h |

## DHCP Exclusions
| **VLAN** | **Exclusion Range** | **Purpose** |
|----------|--------------------|-------------|
| VLAN 10 | 10.33.10.1 - 10.33.10.10 | Gateways, static devices |
| VLAN 20 | 10.33.20.1 - 10.33.20.10 | Gateways, static devices |
| VLAN 30 | 10.33.30.1 - 10.33.30.10 | Gateways, static devices |

## DHCP Helper Address Configuration
