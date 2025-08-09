# OSPF Lab Description

## Topology

- R1 connected to R2 via Fa0/0 (10.1.12.0/24)  
- R1 connected to R3 via Fa0/1 (10.1.13.0/24)  
- R2 connected to R3 via Fa0/1 (10.1.23.0/24)  

## Objectives

- Configure OSPF routing on all routers  
- Establish OSPF neighbor relationships  
- Verify routing tables include OSPF-learned routes  

## Router Configurations

### R1

```bash
interface FastEthernet0/0
 ip address 10.1.12.1 255.255.255.0
 no shutdown

interface FastEthernet0/1
 ip address 10.1.13.1 255.255.255.0
 no shutdown

router ospf 1
 router-id 1.1.1.1
 network 10.1.12.0 0.0.0.255 area 0
 network 10.1.13.0 0.0.0.255 area 0

```

### R2
```bash
interface FastEthernet0/0
 ip address 10.1.12.2 255.255.255.0
 no shutdown

interface FastEthernet0/1
 ip address 10.1.23.2 255.255.255.0
 no shutdown

router ospf 1
 router-id 2.2.2.2
 network 10.1.12.0 0.0.0.255 area 0
 network 10.1.23.0 0.0.0.255 area 0

```

### R3
```bash
interface FastEthernet0/0
 ip address 10.1.13.3 255.255.255.0
 no shutdown

interface FastEthernet0/1
 ip address 10.1.23.3 255.255.255.0
 no shutdown

router ospf 1
 router-id 3.3.3.3
 network 10.1.13.0 0.0.0.255 area 0
 network 10.1.23.0 0.0.0.255 area 0

```

### Verification Commands

```bash
show ip ospf neighbor
show ip route ospf
ping [other routers' IPs]
```

📦 Download
[⬇️ Download the OSPF Lab Packet Tracer File](https://github.com/codeemployee/network-labs/raw/main/ospf_lab.pkt)
