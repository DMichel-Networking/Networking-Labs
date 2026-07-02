# Cisco Packet Tracer – Inter-VLAN Routing with Router-on-a-Stick

## Overview
This project demonstrates Inter-VLAN Routing using the Router-on-a-Stick method in Cisco Packet Tracer. Multiple VLANs were configured on Cisco switches, connected using an 802.1Q trunk, and routed through a Cisco router using subinterfaces. The lab verifies successful communication both within VLANs and between VLANs while reinforcing Layer 2 and Layer 3 networking concepts.

## Objectives
- Configure multiple VLANs on Cisco switches
- Configure 802.1Q trunk links between switches
- Configure Router-on-a-Stick using router subinterfaces
- Enable communication between different VLANs
- Verify end-to-end connectivity between all hosts
- Troubleshoot VLAN, trunk, and routing configurations

## Network Topology

```text
                 Router0
                    |
          (802.1Q Trunk Link)
                    |
               +-----------+
               |  Switch1  |
               +-----------+
                    |
          =====================
          || 802.1Q Trunk ||
          =====================
                    |
               +-----------+
               |  Switch2  |
               +-----------+

      VLAN 13                 VLAN 25
   PC1        PC3          PC2        PC4
```

## IP Addressing Scheme

### VLAN 13

| Device | IP Address | Subnet Mask | Default Gateway |
|----------|------------|-------------|-----------------|
| PC1 | 10.0.0.1 | 255.255.255.128 | 10.0.0.126 |
| PC3 | 10.0.0.3 | 255.255.255.128 | 10.0.0.126 |

### VLAN 25

| Device | IP Address | Subnet Mask | Default Gateway |
|----------|------------|-------------|-----------------|
| PC2 | 10.0.0.2 | 255.255.255.128 | 10.0.0.254 |
| PC4 | 10.0.0.4 | 255.255.255.128 | 10.0.0.254 |

## Technologies Used
- Cisco Packet Tracer
- Cisco IOS CLI
- Layer 2 Switching
- VLAN Configuration
- 802.1Q Trunking
- Router-on-a-Stick
- Router Subinterfaces
- Inter-VLAN Routing
- IPv4 Addressing

## Skills Demonstrated
- VLAN creation and management
- Access port configuration
- 802.1Q trunk configuration
- Router subinterface configuration
- Inter-VLAN routing
- Default gateway configuration
- Layer 2 and Layer 3 troubleshooting
- Cisco IOS configuration and verification

## Key Configuration

### Router Subinterfaces

```bash
interface GigabitEthernet0/0.13
 encapsulation dot1Q 13
 ip address 10.0.0.126 255.255.255.128

interface GigabitEthernet0/0.25
 encapsulation dot1Q 25
 ip address 10.0.0.254 255.255.255.128
```

## Verification Commands

### Verify VLANs

```bash
show vlan brief
```

### Verify Trunk Status

```bash
show interfaces trunk
```

### Verify Router Interfaces

```bash
show ip interface brief
```

### Verify Routing Table

```bash
show ip route
```

### Connectivity Testing

```bash
ping <destination-ip>
```

## Key Learning Outcomes
- Understanding how VLANs segment a Layer 2 network
- Configuring and verifying 802.1Q trunk links
- Implementing Router-on-a-Stick using subinterfaces
- Enabling communication between multiple VLANs
- Understanding how routers route traffic between VLANs
- Troubleshooting VLAN, trunk, and subinterface configurations

## Results
- Successfully configured VLAN 13 and VLAN 25
- Established an operational 802.1Q trunk between switches
- Configured router subinterfaces for Inter-VLAN Routing
- Verified successful communication within and between VLANs
- Demonstrated end-to-end Layer 3 connectivity across the network

## Screenshots
- Network Topology
- VLAN Configuration (`show vlan brief`)
- Trunk Verification (`show interfaces trunk`)
- Router Interface Status (`show ip interface brief`)
- Successful End-to-End Connectivity Verification

## Future Enhancements
- Implement OSPF Dynamic Routing
- Configure Access Control Lists (ACLs)
- Add DHCP for Automatic Address Assignment
- Configure Rapid Spanning Tree Protocol (RSTP)
- Implement EtherChannel
- Expand to a Multi-Router Enterprise Network
