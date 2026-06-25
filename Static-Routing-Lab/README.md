# Cisco Packet Tracer – Multi-Site WAN Routing Lab

## Overview
This project simulates a basic WAN environment using Cisco Packet Tracer. Two separate LANs are connected through Cisco routers over a point-to-point serial connection. The project focuses on IPv4 addressing, subnetting, router configuration, static routing, and connectivity troubleshooting.

## Objectives
- Configure router and switch interfaces
- Implement IPv4 addressing and subnetting
- Establish WAN connectivity using serial interfaces
- Configure static routes for inter-network communication
- Verify end-to-end connectivity between hosts
- Troubleshoot Layer 3 routing and addressing issues

## Network Topology

```text
PC0 ─ Switch0 ─ Router1 ===== Router2 ─ Switch1 ─ PC1
```

## IP Addressing Scheme

### LAN 1

| Device | IP Address | Subnet Mask |
|----------|----------|----------|
| PC0 | 192.168.1.3 | 255.255.255.128 |
| Router1 G0/0 (Default Gateway) | 192.168.1.1 | 255.255.255.128 |

### LAN 2

| Device | IP Address | Subnet Mask |
|----------|----------|----------|
| PC1 | 192.168.2.3 | 255.255.255.128 |
| Router2 G0/0 (Default Gateway) | 192.168.2.1 | 255.255.255.128 |

### WAN Serial Connection

| Device | Interface | IP Address | Subnet Mask |
|----------|----------|----------|----------|
| Router1 | Serial0/1/0 | 192.168.3.1 | 255.255.255.128 |
| Router2 | Serial0/1/0 | 192.168.3.2 | 255.255.255.128 |

## Technologies Used
- Cisco Packet Tracer
- Cisco IOS CLI
- Static Routing
- IPv4 Addressing
- Subnetting
- Serial WAN Connections
- Layer 2 Switching
- Layer 3 Routing

## Skills Demonstrated
- Router interface configuration
- Serial interface configuration and activation
- Static route implementation
- IPv4 subnetting and address planning
- Default gateway configuration
- End-to-end connectivity testing
- Cisco IOS troubleshooting commands
- Network path verification using ICMP (ping)

## Routing Configuration

### Router1

```bash
ip route 192.168.2.0 255.255.255.128 192.168.3.2
```

### Router2

```bash
ip route 192.168.1.0 255.255.255.128 192.168.3.1
```

## Verification Commands

### Interface Verification

```bash
show ip interface brief
```

### Routing Table Verification

```bash
show ip route
```

### Connectivity Testing

```bash
ping <destination-ip>
```

## Key Learning Outcomes
- Understanding LAN and WAN network design
- Configuring point-to-point router connections
- Understanding how routers forward traffic between remote networks
- Implementing static routes using next-hop addresses
- Troubleshooting routing and addressing issues
- Verifying Layer 3 connectivity between remote hosts

## Results
- Successfully established communication between two separate LAN networks
- Configured static routing between routers
- Verified end-to-end connectivity between hosts using ICMP
- Troubleshot and resolved addressing, subnetting, and routing issues

## Future Enhancements
- Implement Dynamic Routing (RIP and OSPF)
- Configure VLANs and Trunking
- Implement Access Control Lists (ACLs)
- Add redundant WAN links
- Configure DHCP services
- Simulate enterprise branch-to-branch connectivity
