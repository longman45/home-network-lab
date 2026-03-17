# home-network-lab
# Home Network & Cybersecurity Lab

## About Me

I'm Adam — an Athletic Trainer making a deliberate career transition into IT and cybersecurity. After over a decade working in some of the most high-pressure, fast-moving healthcare environments imaginable (college sports, clinical orthopedics, and Air Force Special Operations), I've decided to turn a long-time passion and hobby into a profession.

My background isn't your typical IT origin story. I started as a nursing student, realized I wanted something more dynamic, and pivoted to Athletic Training — a field where nothing is textbook and creative problem solving isn't optional, it's survival. That path took me from graduate school at Auburn University (working with the football team) to running a high-volume orthopedic clinic, coordinating what was the first FDA-observed stem cell cartilage regeneration study in the United States, and eventually doing performance rehabilitation with members of AFSOC.

Along the way I learned to manage complex systems, communicate technical information to everyone from surgeons to patients who just want to know if they can play Saturday, and adapt quickly when the plan falls apart which it sometimes does.

IT and cybersecurity aren't a departure from that. They're the same skillset in a different domain. This lab is where I'm building the technical foundation to match.

---

## Overview

This repository documents my hands-on experience designing, building, troubleshooting, and securing a segmented home network environment. The lab simulates real-world enterprise networking and cybersecurity scenarios and is continuously updated as new hardware, configurations, and troubleshooting cases are completed.

---

## Objectives

* Build a secure, scalable, and high-performance home network
* Implement network segmentation using VLANs
* Configure firewall rules to control and restrict traffic
* Deploy and expand network-attached storage (NAS)
* Implementing and running containers
* Gain hands-on experience with enterprise-grade networking hardware
* Develop virtualization skills
* Document all work as a professional portfolio for IT and cybersecurity roles

---

## Lab Environment

### Core Network Hardware

* **UniFi Dream Machine Pro (UDM Pro)** — primary router/firewall/controller
* **UniFi Switch Pro Max 16 PoE** — upgraded from UniFi Switch Lite 8 PoE
* **UniFi U6 Access Points** — multiple units for full wireless coverage

### Storage & Compute

* **TrueNAS SCALE** — NAS running on dedicated hardware with all onboard SATA ports utilized
* **Upgraded NIC** — added for increased throughput and multi-interface connectivity
* Storage expansion in planning (HBA / SATA expansion card evaluation underway)

### Networking Capabilities

* 1Gb / 2.5Gb / 10Gb networking
* DAC (Direct Attach Copper) cables for high-speed interconnects
* VLAN segmentation across wired and wireless networks
* Multiple SSIDs mapped to dedicated VLANs
* Layer 2 and Layer 3 traffic management

### Devices & Segments

* Trusted devices (workstations, phones)
* IoT devices (Thermostat, smart home devices)
* Guest devices
* Network infrastructure management interfaces

---

## Network Segmentation

The network is segmented to reflect enterprise best practices:

| VLAN | Purpose | Access Level |
|------|---------|--------------|
| Management | Infrastructure & admin interfaces | Strictly controlled |
| Trusted | Personal workstations & phones | Full internal access |
| IoT | Smart home devices | Internet only, no lateral access |
| Guest | Visitor devices | Internet only, isolated |

**Firewall rules enforce:**

* IoT → Trusted: blocked
* Guest → Internal: blocked
* Management traffic: allowed only where explicitly required

---

## Security Implementation

* **UniFi IDS/IPS** — enabled for inline traffic inspection and threat detection
* **Country-based geo-blocking** — reduces external attack surface
* **VLAN isolation** — prevents lateral movement between network segments
* **Firewall rule validation** — regularly tested to confirm intended behavior

---

## Key Skills Demonstrated

* VLAN design and implementation (802.1Q)
* Firewall rule creation and traffic isolation
* Intrusion detection and prevention (IDS/IPS)
* Network security hardening (geo-blocking, segmentation)
* Layer 2 / Layer 3 networking
* High-speed networking (DAC, multi-gig, 10Gb)
* NAS deployment and storage planning (TrueNAS SCALE)
* Hardware installation (NIC, switching infrastructure)
* Network troubleshooting and root cause analysis

---

## Projects

Detailed project documentation is located in the `/projects` directory. Each write-up follows a structured case study format (see Documentation Approach below).

| Project | Status |
|---------|--------|
| VLAN Segmentation Implementation | In progress |
| Firewall Rules & Traffic Isolation | In progress |
| TrueNAS SCALE Setup and Storage Expansion | In progress |
| NIC Installation and Network Interface Configuration | In progress |
| Switch Upgrade: PoE Lite → Switch Pro Max 16 PoE | In progress |
| AT&T Gateway Passthrough Configuration | In progress |
| IoT Network Troubleshooting (Ecobee connectivity) | In progress |
| SATA Expansion Planning | In progress |
| High-Speed Networking with DAC Connections | In progress |

---

## Network Diagram

A full network diagram is available in the `/network-diagrams` folder, illustrating topology, VLAN structure, and device relationships.

---

## Documentation Approach

Each project is structured as a technical case study and includes:

* **Objective** — the problem being solved or goal being pursued
* **Tools & Technologies** — hardware, software, and protocols involved
* **Implementation** — step-by-step walkthrough
* **Configuration Details** — relevant settings and rule logic
* **Validation & Testing** — how results were confirmed
* **Screenshots** — proof of work
* **Lessons Learned** — what broke, what I'd do differently

---

## Virtualization (Current Focus)

Currently standing up a Proxmox environment to extend the lab:

* Proxmox VE installation and initial configuration underway
* Planning virtualized workloads and lab services (pfSense, security tooling, etc.)
* Integration with existing UniFi network segmentation and TrueNAS storage

---

## Real-World Troubleshooting Experience

Active troubleshooting scenarios documented in this lab include:

* Diagnosing Ecobee thermostat connectivity failures across VLANs (mDNS/Bonjour forwarding)
* Resolving NIC and interface configuration issues on TrueNAS SCALE
* Identifying SATA port saturation and evaluating HBA expansion options
* Validating firewall rules and inter-VLAN segmentation behavior
* Managing switching infrastructure upgrades with minimal downtime

---

## Certifications & Training

* CompTIA Security+ CE (active)
* ISC2 Certified in Cybersecurity (CC)
* CompTIA Network+ (in progress)
* CompTIA CySA+ (in progress)
* UWF Cyber Defense Analyst Pathway (March 2026)

---

## Future Improvements

* Centralized logging and SIEM-style monitoring (Graylog or similar)
* Expanded IDS/IPS tuning and custom alerting
* Proxmox lab deployment with virtualized security tooling
* Automated configuration backups (UniFi + TrueNAS)
* Vulnerability scanning and internal security auditing
* Advanced network monitoring (Grafana + Prometheus or similar)

---

*Last updated: March 2026*
