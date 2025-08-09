# BGP Lab: Basic eBGP Between Two Autonomous Systems

## 🧠 Objective

Establish eBGP peering between two routers in different ASes and enable communication between their LANs.

---

## 🔧 Topology

[PC1]--[R1]----[R2]--[PC2]
192.168.1.0/24 10.0.0.0/30 192.168.2.0/24
AS 65001 AS 65002


---

## 🛠️ Configuration Summary

### R1 (AS 65001)
- LAN: 192.168.1.0/24
- WAN: 10.0.0.1/30
- BGP neighbor: 10.0.0.2 (AS 65002)
- Advertised: `192.168.1.0/24`

### R2 (AS 65002)
- LAN: 192.168.2.0/24
- WAN: 10.0.0.2/30
- BGP neighbor: 10.0.0.1 (AS 65001)
- Advertised: `192.168.2.0/24`

---

## 🔍 Verification

- `show ip bgp summary` shows established neighbors
- `show ip route` displays BGP-learned routes
- `ping` successful between PC1 and PC2

---

## 📁 Files

- `BGP_Lab_Description.md` – This file
- `bgp_lab.pkt` – Packet Tracer topology

---

## ✅ Outcome

End-to-end communication was achieved using BGP to exchange routes between two autonomous systems.

