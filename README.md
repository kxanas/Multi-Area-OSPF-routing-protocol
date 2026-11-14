# Multi-Area-OSPF-routing-protocol
Cisco Packet Tracer lab: multi-area OSPF design with Area 0 backbone, Areas 1, 2 and 3, ABRs, and a loopback interface.
# Multi-Area OSPF Routing with Loopback (Cisco Packet Tracer)

## Overview
This project implements OSPF across multiple areas. Area 0 is the backbone, and Areas 1, 2 and 3 connect to it. Each area has its own LANs with PCs and laptops, and all of them can reach each other through OSPF. A separate router with a loopback interface is also connected to the backbone.

## Topology
![Network Topology](topology.png)

## Network Design

| Area | Colour | Role | Devices |
|------|--------|------|---------|
| Area 0 | Dark blue | Backbone | Routers R1, R2, R3 and R7 connected by serial links |
| Area 1 | Green | Left side | 1 router, 2 switches, PCs and laptops |
| Area 3 | Yellow | Centre | Router R6, 1 switch, PC and laptop |
| Area 2 | Light blue | Right side | 1 router, 2 switches, PCs and laptops |
| Loopback | Blue oval | Loopback network | Router1 connected to the backbone (R7) |

- Every non-backbone area connects directly to Area 0, as OSPF requires.
- Routers sitting between Area 0 and another area act as **ABRs (Area Border Routers)**.
- All areas exchange routes through the backbone.

## IP Addressing
- **User LANs:** 192.168.10.0/24 to 192.168.100.0/24, from left (Area 1) to right (Area 2)
- **Router-to-router links:** serial point-to-point links `[add your subnets here]`
- **Loopback:** `[add loopback IP here]`

| LAN | Subnet | Area |
|-----|--------|------|
| LAN 1 | 192.168.10.0/24 | Area 1 |
| LAN 2 | 192.168.20.0/24 | Area 1 |
| ... | ... | ... |
| LAN 10 | 192.168.100.0/24 | Area 2 |

## Technologies Used
- OSPF multi-area design (Areas 0, 1, 2 and 3)
- ABRs and backbone area
- Loopback interface
- Serial point-to-point links
- Subnetting
- Cisco 2811 routers and 2960 switches

## Objectives
- Configure OSPF in four areas with Area 0 as the backbone
- Identify and configure the ABRs
- Advertise all LANs and link networks in the correct areas
- Use a loopback interface in the OSPF domain
- Verify end-to-end connectivity between PCs in different areas

## Verification
- `show ip ospf neighbor` to check adjacencies
- `show ip route ospf` to see intra-area (O) and inter-area (O IA) routes
- `show ip ospf database` to view the link-state database
- `show ip protocols` to check the OSPF configuration
- Ping from a PC in Area 1 to a PC in Area 2 and Area 3


## How to Open
Download the `.pkt` file (or the zip) and open it in Cisco Packet Tracer.

## Result
OSPF forms adjacencies in all areas, routes are shared through the backbone, and PCs in every area can ping each other.
