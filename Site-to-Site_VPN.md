# Site-to-Site VPN Lab

## Overview
This lab demonstrates a **site-to-site IPSec VPN** between two Cisco routers, connecting two separate LANs securely over an untrusted network.

---

## Topology

| Device | Interface        | IP Address       | Description                  |
|--------|------------------|------------------|------------------------------|
| R1     | FastEthernet0/1  | 10.0.0.1         | WAN interface to R2          |
| R1     | LAN (VLAN1)      | 192.168.1.1/24   | Local LAN subnet             |
| R2     | FastEthernet0/1  | 10.0.0.2         | WAN interface to R1          |
| R2     | LAN (VLAN1)      | 192.168.2.1/24   | Local LAN subnet             |

---

## Lab Goals
- Configure IP routing on both routers.
- Establish ISAKMP (IKE Phase 1) with AES and SHA authentication using a pre-shared key.
- Configure IPSec transform set (Phase 2) with AES and SHA.
- Apply crypto ACLs to define interesting traffic (LAN-to-LAN).
- Create and apply crypto maps to the WAN interfaces.
- Verify encrypted tunnel establishment and ping connectivity between LANs.

---

## IP Addressing and Routing

- LAN Subnet R1: `192.168.1.0/24`
- LAN Subnet R2: `192.168.2.0/24`
- WAN IPs: `10.0.0.1` (R1), `10.0.0.2` (R2)
- Static routes configured on both routers for LAN subnets via the WAN interfaces.

---

## Key Configuration Steps

### ISAKMP Policy (Phase 1)

```plaintext
crypto isakmp policy 10
 encryption aes
 hash sha
 authentication pre-share
 group 2
 lifetime 86400

crypto isakmp key VPN123 address <peer-ip>

crypto ipsec transform-set VPN-TRANSFORM esp-aes esp-sha-hmac

crypto map VPNMAP 10 ipsec-isakmp
 set peer <peer-ip>
 set transform-set VPN-TRANSFORM
 match address 100

interface FastEthernet0/1
 crypto map VPNMAP

Verification Commands
show crypto isakmp sa — Check IKE Phase 1 status.

show crypto ipsec sa — Check IPSec SA and encrypted traffic.

show access-lists 100 — Verify crypto ACLs.

ping <remote LAN IP> — Test encrypted connectivity.

Results
Tunnel State: QM_IDLE (Phase 2 complete)

Packets encrypted and decrypted confirm active VPN tunnel.

Ping tests from hosts behind each router to the other LAN successful.

Files Included
Packet Tracer file: Site-to-Site_VPN.pkt

This documentation file.

Summary
This lab illustrates how to set up a secure site-to-site VPN, enabling encrypted communication between two distinct networks. It highlights core VPN concepts and Cisco configuration best practices, ideal for CCNP-level studies or professional portfolio showcase.

```

📦 Download
[⬇️ Download the Site-to-Site VPN Lab Packet Tracer File](https://github.com/codeemployee/network-labs/raw/main/Site-to-Site_VPN.pkt)


