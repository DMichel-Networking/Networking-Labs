# Cisco Packet Tracer – VLAN Segmentation and 802.1Q Trunking Lab

## Overview
This project demonstrates Layer 2 network segmentation using Virtual Local Area Networks (VLANs) and 802.1Q trunking between two Cisco switches. Devices were assigned to separate VLANs to create isolated broadcast domains while allowing VLAN traffic to traverse multiple switches over a trunk link.

## Objectives
- Configure VLANs on Cisco switches
- Assign switch ports to specific VLANs
- Configure an 802.1Q trunk between two switches
- Verify communication between devices within the same VLAN
- Verify isolation between different VLANs
- Understand Layer 2 switching and broadcast domain segmentation

## Network Topology

```text
        VLAN 1                         VLAN 1
      PC1 (10.0.0.1)               PC3 (10.0.0.3)
            |                           |
          SW1 ======================= SW2
            |        Trunk Link         |
      PC2 (10.0.0.2)               PC4 (10.0.0.4)
        VLAN 2                         VLAN 2
```

## VLAN Configuration

### VLAN 1
| Device | IP Address |
|----------|----------|
| PC1 | 10.0.0.1/24 |
| PC3 | 10.0.0.3/24 |

### VLAN 2
| Device | IP Address |
|----------|----------|
| PC2 | 10.0.0.2/24 |
| PC4 | 10.0.0.4/24 |

## Switch Configuration

### Switch 1
- Created VLAN 2
- Assigned access ports to VLAN 1 and VLAN 2
- Configured the inter-switch link as an 802.1Q trunk

### Switch 2
- Created VLAN 2
- Assigned access ports to VLAN 1 and VLAN 2
- Configured the inter-switch link as an 802.1Q trunk

## Technologies Used
- Cisco Packet Tracer
- Cisco IOS CLI
- Layer 2 Switching
- VLAN Configuration
- 802.1Q Trunking
- Access Port Configuration

## Skills Demonstrated
- VLAN creation and management
- Access port configuration
- 802.1Q trunk configuration
- Broadcast domain segmentation
- Layer 2 network troubleshooting
- Cisco IOS switch configuration
- End-to-end VLAN connectivity verification

## Verification Commands

### Display VLAN Information

```bash
show vlan brief
```

### Verify Trunk Status

```bash
show interfaces trunk
```

### Verify Switch Interfaces

```bash
show interfaces status
```

### Connectivity Testing

```bash
ping <destination-ip>
```

## Key Learning Outcomes
- Understanding how VLANs logically segment a network
- Configuring and verifying access ports
- Implementing 802.1Q trunk links between switches
- Understanding how trunk links transport multiple VLANs
- Troubleshooting VLAN and trunk configuration issues
- Understanding Layer 2 forwarding and broadcast containment

## Results
- Successfully created multiple VLANs on Cisco switches
- Configured an operational 802.1Q trunk between switches
- Verified communication between hosts in the same VLAN across separate switches
- Verified isolation between hosts in different VLANs without Layer 3 routing

## Future Enhancements
- Implement Router-on-a-Stick for Inter-VLAN Routing
- Configure Dynamic Trunking Protocol (DTP)
- Add additional VLANs and departments
- Implement Rapid Spanning Tree Protocol (RSTP)
- Configure Access Control Lists (ACLs) after enabling Inter-VLAN Routing
- Implement OSPF in a multi-router environment
