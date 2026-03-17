# home-network-lab
# Home Network & Cybersecurity Lab

## Overview

This repository documents my hands-on experience designing, building, troubleshooting, and securing a segmented home network environment. The lab simulates real-world enterprise networking and cybersecurity scenarios and is continuously updated as new hardware, configurations, and troubleshooting cases are completed.

## Objectives

* Build a secure, scalable, and high-performance home network
* Implement network segmentation using VLANs
* Configure firewall rules to control and restrict traffic
* Deploy and expand network-attached storage (NAS)
* Gain hands-on experience with enterprise-grade networking hardware
* Develop virtualization skills (current focus)
* Document all work as a professional portfolio for IT and cybersecurity roles

## Lab Environment

### Core Network Hardware

* UniFi Dream Machine (UDM / UDM Pro)
* UniFi Switch Pro Max 16 PoE (upgrading from UniFi PoE Lite)
* UniFi Access Points (multiple for full wireless coverage)

### Storage & Compute

* TrueNAS-based NAS system with fully utilized onboard SATA ports
* Storage expansion planning (SATA expansion / HBA considerations)
* Upgraded NIC installed for increased throughput and connectivity

### Networking Capabilities

* 1Gb / 2.5Gb / 10Gb networking
* DAC (Direct Attach Copper) cables for high-speed interconnects
* VLAN segmentation across wired and wireless networks
* Multiple SSIDs mapped to VLANs
* Layer 2 and Layer 3 traffic management

### Devices & Segments

* Trusted devices (PCs, phones)
* IoT devices (thermostat, smart home devices)
* Guest devices
* Network infrastructure management interfaces

## Network Segmentation

The network is segmented to reflect enterprise best practices and improve security:

* Management VLAN – infrastructure and administrative access
* Trusted VLAN – secure personal devices
* IoT VLAN – restricted smart/home devices
* Guest VLAN – isolated internet-only access

Firewall rules are implemented to:

* Block IoT → Trusted networks
* Restrict Guest → Internal access
* Allow controlled management traffic where required

## Security Implementation

* UniFi IDS/IPS enabled for traffic inspection and threat detection
* Country-based traffic blocking to reduce external attack surface
* Network isolation to prevent lateral movement between VLANs
* Continuous validation of firewall rules and access controls

## Key Skills Demonstrated

* VLAN design and implementation (802.1Q)
* Firewall rule creation and traffic isolation
* Intrusion detection and prevention (IDS/IPS)
* Network security hardening (geo-blocking, segmentation)
* Layer 2 / Layer 3 networking
* High-speed networking (DAC, multi-gig, 10Gb)
* NAS deployment and storage scaling
* Hardware installation (NIC, switching infrastructure)
* Network troubleshooting and root cause analysis

## Projects

Detailed project documentation is located in the `/projects` directory:

* VLAN Segmentation Implementation
* Firewall Rules & Traffic Isolation
* NAS Setup and Storage Expansion
* NIC Installation and Network Interface Configuration
* Switch Upgrade and Port Layout Design (PoE Lite → Pro Max 16 PoE)
* AT&T Gateway Passthrough Configuration (ISP integration)
* IoT Network Troubleshooting (Thermostat connectivity issue)
* SATA Expansion Planning (storage scalability solution)
* High-Speed Networking with DAC Connections

## Network Diagram

A full network diagram is available in the `/network-diagrams` folder to visualize topology, VLAN structure, and device relationships.

## Documentation Approach

Each project is structured as a technical case study and includes:

* Objective (problem or goal)
* Tools and technologies used
* Step-by-step implementation
* Configuration details
* Validation and testing
* Screenshots as proof
* Lessons learned and troubleshooting insights

## Virtualization (Current Focus)

Actively developing skills in virtualization technologies to expand the lab environment, including:

* Evaluating platforms such as VMware vSphere and Proxmox
* Planning virtualized workloads and lab services
* Integrating virtualization with existing network segmentation and storage systems

## Real-World Troubleshooting Experience

This lab includes active troubleshooting scenarios, such as:

* Diagnosing IoT device connectivity issues across VLANs
* Resolving NIC and interface configuration issues
* Identifying storage limitations and planning expansion
* Validating firewall rules and segmentation behavior
* Managing network hardware upgrades and migrations

## Purpose

This lab is designed to demonstrate practical, hands-on experience with networking and cybersecurity concepts using enterprise-style tools. It serves as a technical portfolio to showcase system design, security implementation, and problem-solving ability to potential employers.

## Future Improvements

* Centralized logging and monitoring (SIEM-style setup)
* Expanded IDS/IPS tuning and alerting
* Virtualization lab deployment (VMware / Proxmox)
* Automated configuration backups
* Vulnerability scanning and security auditing
* Advanced network monitoring and alerting

---
