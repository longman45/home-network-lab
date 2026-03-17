# Project 01 — Home Network Infrastructure Build

## Objective

Design and build a complete home network from scratch — replacing an ISP-provided gateway with enterprise-grade UniFi equipment, running structured CAT6 cabling throughout the home, and deploying wireless access points and security cameras for full coverage. The goal was a clean, professional-grade foundation that could support advanced segmentation, security, and future expansion.

---

## Environment

| Detail | Spec |
|--------|------|
| Home Layout | Main house + attached mother-in-law suite + garage |
| Previous Setup | AT&T BGW320 gateway, no structured cabling, no managed switching |
| New Core Hardware | UniFi Dream Machine Pro (UDM Pro) |
| Switching | UniFi Switch Pro Max 16 PoE |
| Wireless | 2x UniFi U7 Lite APs |
| Cameras | 2x UniFi G6 Turret |
| Cabling | CAT6, all runs home-run to central location |
| ISP | AT&T Fiber via BGW320 (IP passthrough mode) |

---

## Planning

Before pulling a single cable, the entire network was planned using the **UniFi Network Design app**. This allowed visualization of AP placement, coverage overlap, and signal propagation across the floor plan prior to any physical work.

**AP Placement Decisions:**

- **AP 1 (Master Bedroom Closet):** Positioned near the geographic center of the main home. Provides primary coverage for living areas, bedrooms, kitchen, and home office.
- **AP 2 (Laundry Room / Garage Entry):** Positioned to cover the garage, a portion of the backyard, and — critically — the upstairs mother-in-law suite. The laundry room sits at the junction between the main home and the attached garage, making it the optimal midpoint for extended coverage.

**Drop Locations Planned:**

| Location | Drops | Purpose |
|----------|-------|---------|
| Home Office | 2 | Workstations, wired connectivity |
| Media Center | 2 | TV, streaming devices |
| Mother-in-Law Suite | 2 | Wired coverage for attached suite |

---

## The Coax Problem (and the Fix)

The original plan was to use existing coax cable runs as pull strings — a common technique for routing new cable through finished walls without opening drywall. Feed the new CAT6 alongside or in place of the coax and save significant time.

**The problem:** After investigation, the existing coax was stapled directly to studs throughout the walls. It wasn't going anywhere.

**The solution:** Rather than fishing completely new runs blind through finished walls, the decision was made to remove the existing coax drops entirely. This opened the wall penetrations and provided a usable pathway for the CAT6 runs. Every coax outlet location in the home was converted to a CAT6 network drop — 6 total.

This approach turned a frustrating obstacle into a practical win: locations that previously had coax (typically where people put TVs and desks) are exactly where you want wired network drops anyway.

---

## Physical Installation

- All 6 CAT6 runs are **home-run** back to a central termination point — no daisy-chaining or intermediate connections
- Cables terminated with keystone jacks and installed in wall plates at each drop location
- All runs punched down to a patch panel at the equipment location
- Patch panel connects to the UniFi Switch Pro Max 16 PoE
- APs and cameras are **PoE-powered** directly from the switch — no separate power adapters required
- Camera placement covers primary entry points; expansion planned for additional coverage zones

---

## ISP Integration — AT&T BGW320 Passthrough

AT&T fiber requires the BGW320 gateway to remain in line for authentication purposes. To eliminate double-NAT and allow the UDM Pro to function as the true network edge, the BGW320 was configured in **IP passthrough mode**, forwarding the public IP directly to the UDM Pro.

**Current state:** BGW320 in passthrough, UDM Pro handling all routing, firewall, and network management.

**Future state:** Transition to **XGS-PON** direct connection, removing the BGW320 entirely and connecting fiber directly to the UDM Pro. This eliminates the ISP gateway from the network path completely.

---

## UniFi Adoption & Initial Configuration

With physical infrastructure in place, all devices were adopted into the UniFi Network application running on the UDM Pro:

- Switch Pro Max 16 PoE adopted and port profiles configured
- Both U7 Lite APs adopted, radio settings tuned, and SSIDs assigned
- Both G6 Turret cameras adopted into UniFi Protect
- Default network established; VLAN segmentation built on top in a subsequent project (see Project 02)

---

## Validation & Testing

- Confirmed wired connectivity at all 6 drops via link lights and speed tests
- Verified PoE delivery to both APs and both cameras from the switch
- Walked the property to validate wireless coverage — no dead zones identified
- Confirmed BGW320 passthrough was functioning (single NAT, public IP on UDM Pro WAN interface)
- Verified camera feeds live in UniFi Protect

---

## Obstacles & Lessons Learned

**Coax stapled to studs:** The planned pull-string approach failed immediately. Removing the coax drops and using those penetrations as cable pathways was the right call — faster than fishing blind and resulted in cleaner runs.

**AP placement validation matters:** The UniFi design app predicted good coverage from the laundry room AP for the MIL suite. Real-world testing confirmed it. Pre-planning with a design tool before cutting holes saved time and guesswork.

**Home-run everything:** Running all cables back to a single patch location adds more cable but pays off immediately in manageability and troubleshooting. Every drop is independently accessible at the patch panel without touching anything else.

---

## Tools & Materials Used

- UniFi Network Design App (planning)
- CAT6 bulk cable
- Keystone jacks and wall plates
- Patch panel
- Fish tape and glow rods
- Drill and spade bits for wall penetrations
- Punch down tool
- Cable tester

---

## Next Steps

With physical infrastructure complete, the next phase focused on logical network design — implementing VLANs, firewall rules, and network segmentation to enforce security boundaries between device types.

→ See [Project 02 — VLAN Segmentation & Network Security Design](./project-02-vlan-segmentation.md)

---

*Last updated: March 2026*
