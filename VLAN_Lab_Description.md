# VLAN and Inter-VLAN Routing Lab

## Overview

This lab demonstrates a basic VLAN setup with inter-VLAN routing using a router-on-a-stick configuration in Cisco Packet Tracer.

- **Devices:** 2 Switches, 1 Router, 3 PCs  
- **VLANs:** VLAN 10 (Sales), VLAN 20 (Engineering), VLAN 30 (IT)  
- **Goal:** Enable communication between PCs on different VLANs via router subinterfaces.

## Network Topology

- Router connected to Switch 1 (trunk link)  
- Switch 1 connected to Switch 2 (trunk link)  
- PCs assigned to access ports in their respective VLANs  

## Key Concepts Covered

- VLAN creation and assignment on switches  
- Trunk port configuration  
- Router subinterfaces with 802.1Q encapsulation  
- Inter-VLAN routing  
- IP addressing and default gateway setup  

## IP Addressing Scheme

| Device | VLAN | IP Address     | Subnet Mask     | Default Gateway  |
|--------|------|----------------|-----------------|------------------|
| PC1    | 10   | 192.168.10.10   | 255.255.255.0   | 192.168.10.1     |
| PC2    | 20   | 192.168.20.10   | 255.255.255.0   | 192.168.20.1     |
| PC3    | 30   | 192.168.30.10   | 255.255.255.0   | 192.168.30.1     |

## Usage

1. [Download the InterVLAN Packet Tracer Lab](network-labs/intervlan_lab.pkt)
2. Review the device configurations in the CLI tab.  
3. Test connectivity by pinging between PCs across VLANs.

## Next Steps

- Expand the lab by adding more VLANs and PCs.  
- Implement security features such as ACLs to control inter-VLAN traffic.  
- Practice configuring other routing protocols like OSPF on this topology.  
- Document your learning process and update this README accordingly.

## Author

Bob LaRocca – Network Engineer  
[LinkedIn Profile](https://www.linkedin.com/in/your-profile)  
Email: your.email@example.com

---

*This lab is part of my portfolio demonstrating hands-on Cisco networking skills.*
