# Phase 2 — OSPF Redistribution

## Overview

This phase extends the previous eBGP lab by replacing the static BGP network advertisement with a more realistic enterprise routing design.

Instead of originating the enterprise LAN directly in BGP, an internal router now advertises the network through OSPF. The enterprise edge router learns the route through the IGP and selectively redistributes it into BGP before advertising it to the ISP.

This mirrors a common enterprise architecture where internal routing and external routing have distinct responsibilities.

---

## Objectives

- Build a simple OSPF Area 0 between the enterprise routers.
- Advertise the internal LAN through OSPF.
- Redistribute OSPF routes into BGP.
- Filter redistributed routes using a prefix-list and route-map.
- Advertise a default route toward the OSPF domain.
- Validate both the routing control-plane and end-to-end forwarding.

---

## Topology

The lab introduces a simple enterprise architecture where an internal OSPF domain connects to an external autonomous system through an enterprise edge router.

The internal LAN is learned dynamically through OSPF and selectively redistributed into BGP before being advertised to the ISP.

![Lab Topology](./topology.jpg)

| Device | Role | Routing |
|---------|------|---------|
| **enterprise-lan1** | Internal LAN router | OSPF |
| **enterprise-r1** | Enterprise edge router | OSPF + eBGP |
| **isp-r1** | External ISP router | eBGP |

## Architecture

The internal enterprise LAN is represented by **enterprise-lan1**, which participates only in OSPF.

The enterprise edge router acts as the boundary between the IGP and the external autonomous system. It learns the internal LAN through OSPF, filters the route during redistribution, and advertises it into BGP.

A default route is injected into the OSPF domain using `default-information originate always`, allowing internal routers to reach external destinations without redistributing the entire BGP table.

The ISP remains intentionally simple and operates only as an external BGP peer.

---

## Validation

The following evidence validates both the routing control-plane and the end-to-end data-plane.

### 1. OSPF Neighbor Adjacency

![OSPF Neighbor](./evidence/sh-ip-ospf-neighbor.jpg)

*OSPF adjacency reached the **Full** state between **enterprise-r1** and **enterprise-lan1**, confirming that both routers successfully synchronized their link-state databases across the internal 192.168.12.4/30 network.*

---

### 2. OSPF Route Learned

![OSPF Route](./evidence/sh-ip-route-ospf.jpg)

*The enterprise edge router learned **10.10.0.0/24** through OSPF (route code **O**), confirming that the enterprise LAN is now dynamically learned instead of being locally originated.*

---

### 3. OSPF Redistribution into BGP

![Enterprise BGP Table](./evidence/sh-ip-bgp-enterprise-r1.jpg)

*The **10.10.0.0/24** prefix appears in the BGP table of **enterprise-r1** with origin code **? (incomplete)** and **weight 32768**, demonstrating that it entered BGP through OSPF redistribution rather than the **network** statement.*

---

### 4. Route Advertised to the ISP

![ISP BGP Table](./evidence/sh-ip-bgp-isp-r1.jpg)

*The ISP successfully received and installed **10.10.0.0/24** through its eBGP session with **enterprise-r1** (weight **0**), confirming that the redistributed route crossed the AS boundary.*

---

### 5. Default Route Propagation

![OSPF Default Route](./evidence/sh-ip-route-ospf-default.jpg)

*The internal router **enterprise-lan1** received a default route (**0.0.0.0/0**) from **enterprise-r1** via OSPF, providing a single exit point toward external networks without exposing the entire BGP routing table.*

---

### 6. End-to-End Connectivity

![End-to-End Ping](./evidence/ping-lan-to-isp.jpg)

*End-to-end connectivity successfully validated. Traffic originated from the Enterprise LAN (**10.10.0.1**) reached the ISP loopback (**172.16.0.1**) with **0% packet loss**, traversing OSPF, OSPF-to-BGP redistribution, and the eBGP peering session.*

---

## Engineering Log

This phase focused on integrating an internal OSPF domain with the existing eBGP topology while documenting the engineering decisions and troubleshooting process.

### Highlights

- Designed a simple enterprise architecture with OSPF Area 0 and eBGP.
- Implemented controlled OSPF-to-BGP redistribution using route filtering.
- Advertised a default route into the OSPF domain without exposing the BGP table.
- Validated both the routing control-plane and end-to-end forwarding.

### Troubleshooting Highlights

During implementation, several issues were investigated and resolved:

- Corrected Containerlab topology structure and YAML syntax.
- Resolved missing FRR configuration files during deployment.
- Documented FRR configuration reload limitations in this lab environment.
- Identified the OSPF behavior requiring `default-information originate always`.
- Discovered that restarting individual Docker containers breaks Containerlab virtual links.
- Diagnosed an end-to-end forwarding issue caused by Containerlab's management default route and Linux source address selection.

---

## Next Steps

The next phase will continue expanding the enterprise network by introducing additional routing scenarios while maintaining the same incremental design philosophy.

---

## Lab Environment

| Component | Technology |
|-----------|------------|
| Network Emulator | Containerlab |
| Routing Stack | FRRouting (FRR) |
| Container Runtime | Docker |
| Host OS | Ubuntu 24.04 LTS |
| Routing Protocols | OSPFv2, eBGP |
