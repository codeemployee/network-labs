# ACL and Router Firewall Lab

## Overview

This lab demonstrates how to configure Access Control Lists (ACLs) on a Cisco router to filter and control traffic between VLANs, providing basic firewall functionality.

- **Devices:** 1 Router, 1 Switch, 3 PCs, 1 Server  
- **VLANs:** VLAN 10 (PC1), VLAN 20 (PC2), VLAN 30 (Server)  
- **Goal:** Implement ACL rules on router subinterfaces to permit and deny specific traffic, such as allowing HTTP but blocking Telnet.

## Network Topology

- Router connected to Switch via trunk link  
- Switch ports configured as access ports assigned to VLANs 10, 20, and 30  
- PCs and Server connected to their respective VLAN access ports  

## Key Concepts Covered

- VLAN trunking and router subinterfaces configuration  
- Creating and applying extended ACLs inbound on router interfaces  
- Permitting specific TCP traffic (e.g., HTTP to server)  
- Denying unwanted traffic (e.g., Telnet from VLAN 20)  
- Testing connectivity and ACL effectiveness using ping and telnet commands  

## IP Addressing Scheme

| Device | VLAN | IP Address     | Subnet Mask     | Default Gateway  |
|--------|------|----------------|-----------------|------------------|
| PC1    | 10   | 192.168.10.10  | 255.255.255.0   | 192.168.10.1     |
| PC2    | 20   | 192.168.20.10  | 255.255.255.0   | 192.168.20.1     |
| Server | 30   | 10.0.0.10      | 255.255.255.0   | 10.0.0.1         |

## Usage

1. [⬇️ Download the ACL Router Firewall Lab](https://github.com/codeemployee/network-labs/raw/main/acl-router-firewall-lab.pkt)  
2. Review router and switch configurations in CLI and GUI tabs.  
3. Test connectivity:  
   - Ping gateways and server from PCs  
   - Use Telnet from PC2 to server on port 23 (should be blocked)  
   - Use Telnet from PC1 to server on port 80 (should be allowed)  

## Troubleshooting Tips

- Verify trunk ports on switch and router subinterfaces are properly configured.  
- Check VLAN assignments on switch access ports.  
- Confirm ACL rules and their order to ensure correct traffic filtering.  
- Use `show access-lists` and `show ip interface` on the router to monitor ACL hits and interface statuses.  

## Next Steps

- Add logging to ACL entries for better monitoring.  
- Expand ACLs to include UDP traffic controls.  
- Explore Cisco Zone-Based Firewall (ZBFW) for more advanced filtering.  
- Practice designing scalable ACLs for larger networks.  

## Author

Bob LaRocca – Network Engineer  
[LinkedIn Profile](https://www.linkedin.com/in/your-profile)  
Email: your.email@example.com

---

*This lab is part of my portfolio demonstrating practical Cisco ACL and firewall configurations.*
