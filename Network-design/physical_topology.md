# Physical Topology Design

## Topology Type
**Hierarchical Star Topology**

## Why This Topology Was Chosen

| **Reason** | **Explanation** |
|------------|-----------------|
| Scalability | Easy to add new devices, switches, and floors without redesign |
| Centralized Management | All network traffic flows through core/distribution devices |
| Fault Isolation | If one device fails, others remain operational |
| Performance | Hierarchical design optimizes traffic flow |
| Professional Appearance | Suitable for a professional law practice environment |
| Reliability | Redundancy can be added if required in future |

## Three-Tier Hierarchical Design

| **Layer** | **Function** | **Device** |
|-----------|--------------|------------|
| Core Layer | WAN connection, internet gateway | R1 (Cisco 1941) |
| Distribution Layer | Inter-VLAN routing, policy enforcement | D1 (Cisco 3560-24PS) |
| Access Layer | End-user device connectivity | AS-1, AS-2 (Cisco 2960-24TT) |

## Network Device Inventory

| **Device** | **Model** | **Quantity** | **Purpose** |
|------------|-----------|--------------|-------------|
| Core Router | Cisco 1941 | 1 | Gateway to internet, WAN connection |
| Distribution Switch | Cisco 3560-24PS (Layer 3) | 1 | Backbone routing between VLANs |
| Access Switch | Cisco 2960-24TT (Layer 2) | 2 | Connect end devices on current floor |
| Wireless AP (Internal) | Cisco WAP121 | 1 | Provide internal staff Wi-Fi |
| Wireless AP (Guest) | Cisco WAP121 | 1 | Provide guest Wi-Fi (CR3) |
| DHCP Server | Generic Server (PT) | 1 | Dynamic IP assignment for all VLANs |
| Desktop PC | Generic PC-PT | 4 | Staff workstations |
| Staff Laptop | Generic Laptop | 1 | Staff wireless device |
| Guest Laptop | Generic Laptop | 1 | Guest wireless device (testing) |
| ISP Router | Cisco 1941 | 1 | Simulate internet connection for testing |

## Physical Diagram

## Physical Connections

| **Connection** | **From Port** | **To Port** | **Cable Type** | **Speed** |
|----------------|---------------|-------------|----------------|-----------|
| ISP to R1 | ISP-Router S0/0/0 | R1 S0/0/0 | Serial DCE | 64 Kbps |
| R1 to D1 | R1 G0/0 | D1 G0/1 | Copper Straight-Through | 1000 Mbps |
| D1 to AS-1 | D1 G0/2 | AS-1 G0/1 | Copper Straight-Through | 1000 Mbps |
| D1 to AS-2 | D1 G0/3 | AS-2 G0/1 | Copper Straight-Through | 1000 Mbps |
| D1 to AP-1 (Staff) | D1 G0/4 | AP-1 Ethernet | Copper Straight-Through | 100 Mbps |
| D1 to AP-2 (Guest) | D1 G0/5 | AP-2 Ethernet | Copper Straight-Through | 100 Mbps |
| D1 to DHCP Server | D1 G0/6 | Server FastEthernet0 | Copper Straight-Through | 100 Mbps |
| AS-1 to PC1 | AS-1 F0/1 | PC1 FastEthernet0 | Copper Straight-Through | 100 Mbps |
| AS-1 to PC2 | AS-1 F0/2 | PC2 FastEthernet0 | Copper Straight-Through | 100 Mbps |
| AS-2 to PC3 | AS-2 F0/3 | PC3 FastEthernet0 | Copper Straight-Through | 100 Mbps |
| AS-2 to PC4 | AS-2 F0/4 | PC4 FastEthernet0 | Copper Straight-Through | 100 Mbps |
| AP-1 to Laptop1 | Wireless | Wireless | Wi-Fi | 54 Mbps |
| AP-2 to Laptop2 | Wireless | Wireless | Wi-Fi | 54 Mbps |

## Scalability for Future Floor

| **Scalability Feature** | **Implementation** |
|-------------------------|-------------------|
| Available Ports on D1 | D1 has 24 ports; only 6 used |
| Additional VLANs | New floor can use VLAN 40, 50, 60, 70 |
| Additional DHCP Scopes | DHCP server can be configured with new scopes |
| Core Router Capacity | R1 has sufficient processing power |
| IP Addressing | 10.33.0.0/16 has 65,536 addresses available |

## Physical Topology Justification

| **Design Decision** | **Reason** |
|---------------------|------------|
| Hierarchical Star Topology | Scalable, easy to manage, fault-tolerant |
| Layer 3 Distribution Switch | Enables high-speed inter-VLAN routing |
| Separate Access Switches | Reduces single points of failure |
| Dedicated APs for Staff and Guest | Separate internal and guest Wi-Fi for security (CR3) |
| Dedicated Management VLAN | Secure, out-of-band management |
| Dedicated Server VLAN | Protects infrastructure servers |
| Gigabit Uplinks | High-speed connections between switches |
