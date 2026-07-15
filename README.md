# Cloud Networking Lab

> A hands-on engineering project focused on building practical skills in Enterprise and Cloud Networking through reproducible labs.

---

## Overview

Cloud Networking Lab is an engineering project created to document and demonstrate practical skills in Enterprise-Cloud Networking through reproducible, hands-on labs.

Instead of simply listing technologies on a résumé, this repository provides evidence of real implementations, technical decision-making, and troubleshooting performed while building progressively more complex network architectures.

Each milestone extends the existing platform, gradually evolving it toward production-like enterprise, cloud, and hybrid networking environments.

---

## Project Philosophy

This project follows a few simple principles:

- Evidence before claims
- Engineering before presentation
- Quality over quantity
- Reproducible infrastructure
- Document real troubleshooting
- Explain design decisions

The objective is not to build dozens of isolated labs, but to create a network that continuously evolves over time.

---

## Technology Stack

### Enterprise Networking

- Containerlab
- FRRouting (FRR)
- Docker
- Linux

### Cloud Networking (Roadmap)

- AWS
- Terraform
- Hybrid Networking
- Azure

---

## Repository Structure

```text
cloud-networking-lab/
│
├── labs/
│   └── phase-01-bgp/
│       ├── configs/
│       ├── images/
│       ├── README.md
│       └── topology.clab.yml
│
├── docs/
│
├── README.md
├── LICENSE
└── .gitignore
```

---

## Milestones

| Milestone | Status | Description |
|-----------|:------:|-------------|
| Phase 01 – Understanding Why BGP Exists | ✅ Completed | Build a reproducible eBGP topology using Containerlab and FRRouting while understanding the fundamentals of BGP. |
| Phase 02 – BGP Path Selection | 🚧 Planned | Learn how BGP selects the best path when multiple routes are available. |
| Phase 03 – Multi-homed Enterprise | ⏳ Planned | Connect the enterprise to multiple ISPs and introduce redundancy. |
| Phase 04 – BGP Policies | ⏳ Planned | Route filtering, Local Preference, MED and Communities. |
| Phase 05 – Enterprise LAN Integration | ⏳ Planned | Introduce OSPF and redistribute internal routes into BGP. |
| Phase 06 – Hybrid Cloud Connectivity | ⏳ Planned | Extend the enterprise network toward AWS using Terraform. |

---

## Current Progress

✔️ Phase 01 completed

The first milestone establishes the foundation of the project by implementing an eBGP peering between two Autonomous Systems using Containerlab and FRRouting.

The lab also documents the engineering decisions and troubleshooting process required to build a fully reproducible environment.

---

## Future Roadmap

The long-term goal is to evolve this repository into a production-like networking platform covering topics such as:

- Advanced BGP
- Enterprise routing
- AWS networking
- Hybrid connectivity
- Infrastructure as Code
- Network automation
- Cloud architecture

Each new milestone will extend the existing topology instead of creating isolated labs.

---

## License

This project is released under the MIT License.