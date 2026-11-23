# Small Business Network Lab

A small-business network built in Cisco Packet Tracer with a Linux VM web server. It covers VLANs, inter-VLAN routing, NAT, ACLs and a DMZ.

**Status:** in progress

## Goal
Design, configure and test a segmented small-business network, and document each stage so it can be reproduced.

## Topology
Internet / ISP → Edge router → L3 switch → VLANs 10, 20, 30, plus a DMZ off the edge router.

![Topology](diagrams/topology.png)

## IP plan

| Segment | Subnet | Gateway | Purpose |
|---|---|---|---|
| VLAN 10 Staff | 192.168.10.0/24 | 192.168.10.1 | PCs, printer |
| VLAN 20 Guest | 192.168.20.0/24 | 192.168.20.1 | Internet only |
| VLAN 30 Servers | 192.168.30.0/24 | 192.168.30.1 | DHCP/DNS, Linux VM |
| DMZ | 172.16.0.0/24 | 172.16.0.1 | Public web server |
| Router to L3 switch | 10.0.0.0/30 | 10.0.0.1 / .2 | Routed link |
| ISP link | 203.0.113.0/24 | 203.0.113.1 | Simulated internet |

## Features
- [ ] VLANs and inter-VLAN routing
- [ ] DHCP per VLAN
- [ ] NAT/PAT to the ISP
- [ ] ACLs: guests isolated, DMZ restricted
- [ ] Linux VM web server
- [ ] Connectivity test results

## Repository layout
- `topology.pkt`: Packet Tracer file
- `configs/`: exported device configs
- `diagrams/`: topology diagrams
- `vm/`: Linux VM setup notes
- `tests/`: test plan and results

## Tools
Cisco Packet Tracer, Linux VM (Ubuntu Server), Git