# Change Request CR3: Guest Wi-Fi

## Requirement
**Guest Wi-Fi must be added for visitors, isolated from internal resources.**

## Analysis

### Why This Is Required
- Visitors to the law practice (clients, couriers, consultants) need internet access while waiting
- Legal client confidentiality requires that visitors cannot access internal systems
- Professional office environment expects guest amenities

### Security Concerns
- Guests must not access internal legal documents
- Guests must not access staff systems
- Guests must not disrupt internal network operations

## Implementation Plan

### VLAN Segmentation
| **VLAN** | **Name** | **Subnet** | **Purpose** |
|----------|----------|------------|-------------|
| VLAN 30 | Guest_WiFi | 10.33.30.0/24 | Completely isolated guest network |

### Wireless Configuration
| **Setting** | **Value** |
|-------------|-----------|
| SSID | Guest-WiFi |
| Authentication | Open (no password) |
| Client Isolation | Enabled |
| VLAN | 30 |

### ACL Configuration
