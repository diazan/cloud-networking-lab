# Diazan's Cloud Networking Lab

## Overview

Cloud Networking Lab is an engineering-focused project that documents the design, implementation, validation, and troubleshooting of modern network architectures using **Containerlab**, **FRRouting (FRR)**, **Docker**, and eventually **AWS**, **Azure**, and **GCP**.

Rather than collecting isolated configuration examples, this project follows an incremental learning approach where each phase builds upon the previous one, introducing new technologies while maintaining a reproducible and fully documented environment.

The project serves both as a technical portfolio and as a continuous learning platform, allowing me to maintain and expand my networking knowledge while exploring modern cloud networking technologies through reproducible, hands-on labs.

---

## Project Roadmap

| Phase | Topic | Status |
|---------|------------------------------|:------:|
| Phase 1 | BGP Fundamentals | ✅ Completed |
| Phase 2 | OSPF & BGP Redistribution | ✅ Completed |
| Phase 3 | iBGP & Multi-Homing | 🚧 Planned |
| Phase 4 | BGP Best Path Selection | ⏳ Planned |
| Phase 5 | Route Policies & Communities | ⏳ Planned |
| Phase 6 | Internet Edge Services | ⏳ Planned |
| Phase 7 | High Availability | ⏳ Planned |
| Phase 8 | Hybrid Cloud Connectivity | ⏳ Planned |

---

## Published Labs

| Phase | Description |
|---------|-------------|
| **Phase 1 – BGP Fundamentals** | Build a simple eBGP peering between two autonomous systems and exchange routes using the `network` statement. |
| **Phase 2 – OSPF & BGP Redistribution** | Introduce an internal OSPF domain, selectively redistribute routes into BGP, and validate end-to-end forwarding. |

---

## Skills Demonstrated

### Routing

- eBGP
- OSPFv2
- Route Redistribution
- Default Route Origination
- Route Filtering
- Prefix Lists
- Route Maps

### Infrastructure

- Containerlab
- FRRouting (FRR)
- Docker
- Linux Networking

### Engineering Practices

- Incremental Lab Design
- Architecture Design
- Control Plane Validation
- Data Plane Validation
- Root Cause Analysis
- Technical Documentation
- Troubleshooting
- Reproducible Network Labs

---

## Repository Structure

```text
cloud-networking-lab/
│
├── labs/
│   ├── phase-01-bgp/
│   └── phase-02-ospf-redistribution/
│
├── docs/
│
└── README.md
```

---

## Project Status

| Published Labs | Current Topic | Next Phase | Last Update |
|----------------|---------------|------------|-------------|
| **2** | OSPF & BGP Redistribution | iBGP & Multi-Homing | July 2026 |

---

## Design Philosophy

This project is guided by a few engineering principles:

- Build progressively instead of creating isolated labs.
- Understand the reasoning behind every design decision.
- Validate both the control plane and the data plane.
- Document troubleshooting, not only successful configurations.
- Keep every lab reproducible and easy to rebuild.
- Prioritize understanding over memorization.

---

## Lab Environment

| Component | Technology |
|------------|------------|
| Network Emulator | Containerlab |
| Routing Stack | FRRouting (FRR) |
| Container Runtime | Docker |
| Host OS | Ubuntu 24.04 LTS |

---

## Future Direction

Future phases will gradually expand the lab toward production-oriented enterprise and cloud networking scenarios, including:

- iBGP
- Multi-Homing
- BGP Best Path Selection
- Route Policies
- BGP Communities
- High Availability
- Hybrid Cloud Connectivity
- Terraform Automation

The long-term goal is to build a comprehensive cloud networking engineering portfolio that demonstrates practical skills through reproducible labs, technical documentation, and systematic troubleshooting.
