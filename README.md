# Cloud Networking Lab

A progressive, hands-on learning project focused on networking fundamentals and cloud connectivity, built to strengthen practical skills toward a Cloud Network Engineer role.

## Goals

This project combines on-premise network simulation (Containerlab) with real cloud environments (Azure / AWS) to practice:

- BGP (multi-AS peering, route filtering, route reflectors)
- Site-to-site VPN (IPSec)
- BGP over VPN (dynamic routing between on-prem and cloud)
- Hybrid connectivity between simulated on-prem networks and real cloud VPCs/VNets

## Project structure

- `docs/` — written notes and explanations for each phase
- `labs/` — Containerlab topology definitions
- `configs/` — device configuration files (FRR, VyOS, etc.)
- `diagrams/` — network diagrams (draw.io source + exports)
- `images/` — screenshots used in documentation
- `scripts/` — automation helpers
- `templates/` — reusable templates for new labs and troubleshooting notes
- `assets/` — logos, icons, misc graphics

## Tools

- [Containerlab](https://containerlab.dev/) + FRRouting — on-premise network simulation
- Azure / AWS — cloud-native networking labs
- Temporary cloud VM (public IP) — hybrid on-prem/cloud scenarios

## Phases

| Phase | Topic | Status |
|-------|-------|--------|
| 01 | Foundation (base topology, connectivity) | In progress |
| 02 | eBGP (multi-AS peering) | Planned |
| 03 | Dual ISP / BGP path selection | Planned |
| ... | VPN, hybrid cloud connectivity | Planned |

## Video evidence

Each phase includes a short demo video, linked from its corresponding file under `docs/`.
