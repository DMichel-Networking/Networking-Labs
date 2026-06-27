# 802.1Q Trunk Encapsulation Lab

## Overview

This lab demonstrates how to configure an IEEE 802.1Q trunk between two Cisco multilayer switches. The objective was to transport multiple VLANs across a single physical link while maintaining VLAN isolation.

---

## Objectives

- Verify initial Layer 2 connectivity
- Create VLAN 2
- Assign switch ports to VLAN 2
- Configure an 802.1Q trunk
- Troubleshoot trunk encapsulation errors
- Verify VLAN segmentation after trunk configuration

---

## Network Topology

![Network Topology](01-Network-Topology.png)

---

## Network Information

| Device | IP Address | VLAN |
|---------|------------|------|
| PC1 | 10.0.0.1/24 | VLAN 1 |
| PC2 | 10.0.0.2/24 | VLAN 2 |
| PC3 | 10.0.0.3/24 | VLAN 2 |

---

## Initial Connectivity Test

Before creating VLANs, all devices were members of the default VLAN.

### Results

- ✅ PC1 → PC2 Successful
- ✅ PC1 → PC3 Successful
- ✅ PC2 → PC3 Successful

Screenshot:

![Initial Ping Test](02-Initial-Ping-Test.png)

---

## VLAN Configuration

Created VLAN 2 and assigned the access ports for PC2 and PC3.

---

## Trunk Configuration

Initially attempted to configure the trunk using:

```cisco
switchport mode trunk
```

Cisco IOS returned an error because trunk encapsulation had not yet been specified.

Screenshot:

![Trunk Error](03-Trunk-Encapsulation-Error.png)

The issue was resolved using:

```cisco
switchport trunk encapsulation dot1q
switchport mode trunk
```

These commands were configured on both switches.

Screenshot:

![Trunk Configuration](04-8021Q-Trunk-Configuration.png)

---

## Verification

After the trunk was established:

- ✅ PC2 communicated with PC3
- ❌ PC1 could not communicate with PC2
- ❌ PC1 could not communicate with PC3

This confirmed that:

- IEEE 802.1Q trunking was functioning correctly.
- VLAN 2 traffic successfully traversed the trunk.
- Devices in different VLANs remained isolated without inter-VLAN routing.

Screenshot:

![Successful VLAN Segmentation](05-Successful-VLAN-Segmentation-8021Q-Trunk.png)

---

## Skills Demonstrated

- IEEE 802.1Q Trunking
- VLAN Configuration
- Access Port Configuration
- Cisco IOS Troubleshooting
- Layer 2 Switching
- Network Verification
- Connectivity Testing

---

## Commands Used

```cisco
vlan 2

interface FastEthernet0/x
 switchport mode access
 switchport access vlan 2

interface FastEthernet0/3
 switchport trunk encapsulation dot1q
 switchport mode trunk
```

---

## Lessons Learned

This lab demonstrated that some Cisco switch models require trunk encapsulation to be configured before trunk mode can be enabled. Once the trunk was established using IEEE 802.1Q, VLAN traffic successfully traversed the trunk while maintaining proper VLAN isolation. Communication between different VLANs requires inter-VLAN routing, which was intentionally not configured in this lab.
