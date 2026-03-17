# Project 01 — Home Network Infrastructure Build

## Overview

This project documents the full design and installation of a new home network from the ground up — replacing an ISP-provided gateway setup with enterprise-grade UniFi hardware, running CAT6 cabling throughout the house, installing network drops, deploying wireless access points, and standing up a surveillance camera system. This infrastructure serves as the physical foundation for all subsequent lab projects.

---

## Objectives

- Replace AT&T BGW320 gateway with a managed UniFi environment
- Design and install structured CAT6 cabling throughout the home
- Deploy wired network drops for workstations and media devices
- Provide full wireless coverage across the main house, MIL suite, garage, and yard
- Install UniFi security cameras as part of the initial infrastructure build
- Document the process as a repeatable, professional-grade installation

---

## Hardware Used

| Device | Role |
|--------|------|
| AT&T BGW320 | ISP gateway (configured for IP passthrough) |
| UniFi Dream Machine Pro (UDM Pro) | Primary router, firewall, and network controller |
| UniFi Switch Pro Max 16 PoE | Core managed switch |
| UniFi U7 Lite × 2 | Wireless access points |
| UniFi G6 Turret × 2 | PoE security cameras |
| CAT6 cable | Structured wiring throughout home |

---

## Network Drop Layout

6 total wired drops installed across three locations:

| Location | Drops | Purpose |
|----------|-------|---------|
| Home Office | 2 | Primary workstation and lab equipment |
| Media Center | 2 | TV and streaming devices |
| MIL Suite | 2 | Workstation and general use |

---

## Wireless Coverage Design

AP placement was planned using the **UniFi Design Center** prior to installation to validate coverage before running any cable.

| AP | Location | Coverage Area |
|----|----------|---------------|
| U7 Lite #1 | Master bedroom closet | Centrally located — covers the majority of the main house |
| U7 Lite #2 | Laundry room | Covers MIL suite above, garage, laundry room, and partial yard coverage for outdoor use |

Both APs are wired via PoE back to the UniFi Switch Pro Max 16 PoE, eliminating any wireless backhaul dependency.

---

## Planning Phase

Before touching a single wall, the network layout was designed using the **UniFi Design Center** — a planning tool that allows you to import a floor plan, place devices, and visualize expected signal coverage. This step drove both AP placement decisions and confirmed that two APs would be sufficient to cover the full footprint including the detached MIL suite and garage.

Cable routing was mapped room by room with the goal of running all drops back to a central termination point where the UDM Pro and switch are located.

---

## Installation

### CAT6 Cabling

All drops were run using CAT6 cable and terminated with keystone jacks into wall plates. Cable runs were routed through walls and attic space back to the central equipment location.

**Total runs:** 6 network drops + 2 AP drops + 2 camera drops = 10 CAT6 runs

### Obstacle — Coax to CAT6 Conversion

The original plan was to use existing coax cable conduit paths to fish CAT6 through the walls. After opening the walls it became clear the coax was **stapled directly to the studs** and could not be used as a pull guide.

**Solution:** Rather than abandoning those wall paths, the existing coax drops were removed entirely and the same wall openings were reused to install CAT6 drops in their place. This turned a potential setback into a clean result — the coax infrastructure that was no longer needed was replaced with usable network infrastructure using the same wall penetrations.

---

## ISP Gateway Configuration

The AT&T BGW320 was configured in **IP Passthrough mode**, assigning the public IP directly to the UDM Pro. This effectively removes the BGW320 from the routing path and eliminates double-NAT, while keeping the ONT connection intact since AT&T fiber requires their gateway for authentication.

**Future plan:** Replace the BGW320 entirely using **XGS-PON** with a third-party ONT, removing the ISP gateway from the equation altogether once that path is available.

---

## Camera Installation

Two UniFi G6 Turret cameras were installed as part of this build, powered via PoE from the switch. Cameras are managed through the UniFi Protect application running on the UDM Pro.

Additional cameras are planned as the surveillance system expands.

---

## Validation & Testing

- All 6 network drops tested for connectivity and link speed post-termination
- Both U7 Lite APs adopted into UniFi controller and verified for expected coverage
- Both G6 Turret cameras adopted into UniFi Protect and confirmed live feed
- IP Passthrough confirmed — UDM Pro receiving public IP with no double-NAT
- Full device inventory visible in UniFi controller with no orphaned or unadopted devices

---

## Lessons Learned

- **Plan before you pull.** Using the UniFi Design Center before installation prevented wasted cable runs and validated AP placement before anything was mounted. The coverage maps matched real-world performance closely.
- **Survey before you commit to a routing strategy.** The coax pull plan was reasonable on paper — checking the actual cable situation before committing to that approach would have saved some time. That said, the conversion worked cleanly and the end result was better than the original coax anyway.
- **PoE simplifies everything.** Running a single CAT6 drop to each AP and camera rather than managing separate power runs kept the installation clean and reduced the number of variables during troubleshooting.
