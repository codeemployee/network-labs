# DHCP Configuration Lab (Packet Tracer)

This lab demonstrates how to configure a router as a DHCP server for multiple VLANs in a Cisco Packet Tracer environment.

## 🧪 Lab Objectives

- Configure VLANs on a switch
- Assign access ports to VLANs
- Use a trunk port to connect to a router
- Set up router subinterfaces (Router-on-a-Stick)
- Configure DHCP pools for each VLAN
- Verify DHCP client address assignment
- Test inter-VLAN connectivity

## 🖥️ Topology



## 🧩 IP Configuration

| VLAN | Network        | Gateway         | DHCP Pool Range       |
|------|----------------|------------------|------------------------|
| 10   | 192.168.10.0/24 | 192.168.10.1     | 192.168.10.11–.254     |
| 20   | 192.168.20.0/24 | 192.168.20.1     | 192.168.20.11–.254     |

Excluded addresses: `.1` to `.10` in each subnet

## ⚙️ Key Configurations

### Switch (VLANs + Trunk)
```bash
vlan 10
vlan 20

interface fa0/1
 switchport mode access
 switchport access vlan 10

interface fa0/2
 switchport mode access
 switchport access vlan 20

interface fa0/24
 switchport mode trunk

interface fa0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0

interface fa0/0.20
 encapsulation dot1Q 20
 ip address 192.168.20.1 255.255.255.0

ip dhcp excluded-address 192.168.10.1 192.168.10.10
ip dhcp excluded-address 192.168.20.1 192.168.20.10

ip dhcp pool VLAN10
 network 192.168.10.0 255.255.255.0
 default-router 192.168.10.1
 dns-server 8.8.8.8

ip dhcp pool VLAN20
 network 192.168.20.0 255.255.255.0
 default-router 192.168.20.1
 dns-server 8.8.8.8

✅ Verification
Use ipconfig /all on each PC to confirm dynamic addressing

Ping PC1 to PC2 — should succeed

Confirm gateway and DNS assigned correctly

📦 Download
⬇️ Download the DHCP Lab Packet Tracer File
