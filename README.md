# Data Center Colocation: What 250 kW Racks Change, How Retail vs Wholesale Billing Works, and When Renting a Server Beats Renting Space (With Current Plan Prices)

Data center colocation is a lease on space, power, cooling and connectivity inside someone else's building, with the servers staying yours. The evaluation criteria have shifted. AI racks now draw more than 250 kW each, and conventional in-rack power delivery starts to give out somewhere between 350 kW and 400 kW, so a shortlist built around "how many megawatts does the site advertise" misses the question that actually decides whether your deployment fits.

What follows covers how colo is billed from a single cabinet up to a multi-megawatt hall, the density figures worth putting in your RFP, the contract items that determine what an outage costs you, and where SpinServers fits: managed colocation priced by quote, plus published VPS and dedicated plans for anyone who does not need a cabinet at all.

> **Quick version**
> - Rent colo space if you own hardware you need to control, want carrier and cloud density in one building, or need capacity sooner than a build allows.
> - Build your own only if you need full visibility into the facility's risk profile, or regulation keeps the workload out of shared infrastructure.
> - Check three numbers before anything else: kW per rack you need today and in 24 months, the cooling method that reaches it, and the date the provider can hand that capacity over.
> - 👉 [See SpinServers' colocation setup and current plans](https://bit.ly/Spinservers)

## What SpinServers publishes, and what arrives as a quote

SpinServers runs managed colocation in the US and publishes the process rather than a price list. Their colocation page lays out three steps and asks for your hardware, power and bandwidth requirements before quoting, which is normal for colo and also means you cannot comparison-shop them on a $/kW basis without a conversation.

Two details on that page carry more weight than the rest. Standard colocation is built around servers purchased from The Server Store, so the provider can keep onsite spares and support hardware it already knows. Gear bought elsewhere is not automatically excluded, but you have to talk to sales first, and that conversation should happen before you crate anything. Remote management runs through the client portal: OS installs, power controls, remote console access, plus IPv6, private networking between your own servers, and announcement of your own IP space if you bring address space with you.

👉 [Start a colocation quote with your hardware and power numbers](https://bit.ly/Spinservers)

## The published plans, in one table

Where SpinServers does publish prices is one layer down, in KVM VPS and dedicated servers, all billed monthly. These matter for this decision because a fair number of people searching for colocation are one or two servers short of needing it.

| Plan | Core configuration | Price (USD/mo) | Billing | Order |
| --- | --- | --- | --- | --- |
| KVM 2 vCPU 2 GB | 2 vCPU, 2 GB DDR4, 40 GB RAID-10 SSD, 4 TB transfer, 1 Gbps | $12.00 | Monthly | [Order](https://bit.ly/Spinservers) |
| KVM 4 vCPU 4 GB | 4 vCPU, 4 GB DDR4, 80 GB RAID-10 SSD, 8 TB transfer, 1 Gbps | $29.00 | Monthly | [Order](https://bit.ly/Spinservers) |
| KVM 6 vCPU 8 GB | 6 vCPU, 8 GB DDR4, 120 GB RAID-10 SSD, 8 TB transfer, 1 Gbps | $39.00 | Monthly | [Order](https://bit.ly/Spinservers) |
| KVM 8 vCPU 8 GB | 8 vCPU, 8 GB DDR4, 160 GB RAID-10 SSD, 10 TB transfer, 1 Gbps | $45.00 | Monthly | [Order](https://bit.ly/Spinservers) |
| KVM 12 vCPU 12 GB | 12 vCPU, 12 GB DDR4, 160 GB RAID-10 SSD, 10 TB transfer, 1 Gbps | $62.00 | Monthly | [Order](https://bit.ly/Spinservers) |
| KVM 16 vCPU 16 GB | Intel Xeon, 16 vCPU, 16 GB DDR4, 320 GB RAID-10 SSD, 15 TB transfer, 1 Gbps | $74.00 | Monthly | [Order](https://bit.ly/Spinservers) |
| Hybrid KVM 32 vCPU 32 GB | Intel Xeon, 32 vCPU, 32 GB RAM, 500 GB SSD, 20 TB transfer, 1 Gbps | $89.00 | Monthly | [Order](https://bit.ly/Spinservers) |
| Intel Xeon E3-1280 v5 (Dallas) | 4 vCPU, 32 GB RAM, 1 TB NVMe, 30 TB transfer | $79.00 | Monthly | [Order](https://bit.ly/Spinservers) |
| Intel Xeon E3-1280 v5 (San Jose) | 4 vCPU, 32 GB RAM, 1 TB NVMe, 30 TB transfer | $79.00 | Monthly | [Order](https://bit.ly/Spinservers) |
| Dual Intel Xeon Gold 6148 (Dallas) | 40 vCPU, 256 GB RAM, 3.84 TB SSD, 30 TB transfer | $235.00 | Monthly | [Order](https://bit.ly/Spinservers) |
| Dual Intel Xeon Platinum 8173M (Dallas) | 56 vCPU, 512 GB RAM, 7.68 TB SSD, 30 TB transfer | $390.00 | Monthly | [Order](https://bit.ly/Spinservers) |

One limitation applies across every VPS plan above: port 25 is closed by default to limit IP abuse. If you need SMTP, you file a ticket with a justification and the provider reserves the right to refuse. Plan for that before migrating a mail server.

## Four power tiers, and one term that does not belong in that list

Colocation gets segmented by facility power draw, and the boundaries are worth knowing because they predict the contract you will be offered.

**Retail colocation, under 250 kW.** You lease a rack, a caged area, or part of a rack. Hundreds of customers share cooling and the interconnection ecosystem. Billing often runs on square footage plus actual power drawn, and some providers sell lockable cabinets in fixed power increments instead.

**Wholesale colocation, 250 kW to 15 MW.** A cage, a data hall, or a large share of a facility, at a lower unit rate. This is where enterprises with real infrastructure land, and where large cloud providers lease space to add capacity faster than they can build.

**Hyperscale leased, 15 MW to 1 GW.** The Amazon, Google and Microsoft tier.

**AI-specific leased data centers, 15 MW to 1 GW.** Same scale band, built with the power and cooling profile for AI networking.

"Hybrid" is not a fifth power tier, even though it appears in the same lists. The common definition is colocation plus cloud integration: some workloads in the cage, some in a public cloud, connected. Splunk treats hybrid as a deployment model alongside retail and wholesale; Corning describes the same pattern as Hybrid IT, with an MTDC or cloud service acting as a safety net if one part of the system fails. Keep it out of your power comparison or you will end up comparing square feet to megawatts.

Granularity varies by provider more than the tier names suggest. NTT DATA, for example, describes renting a single rack, a cage inside shared open colo space, a private suite, a floor, or a whole building, with the ability to scale up or down while in service, and a carrier meet-me room for external network and cloud access.

## The density numbers worth putting in your RFP

This is the part that most colocation explainers skip, and it is the part that decides whether a facility signed in 2023 can host the hardware you buy in 2027.

| Metric | Verified figure | What it changes for you |
| --- | --- | --- |
| Current AI rack draw | More than 250 kW per rack | A single rack can now exceed the entire footprint limit of a retail colo deal |
| Where conventional rack power delivery fails | 350 kW to 400 kW per rack | Connector sizes, busbars, copper volume and in-rack conversion compete for the same space |
| Density trend | Approaching 1 MW per rack | Ask for a 24-month kW roadmap per zone, not a current capacity number |
| Distribution path in use today | Medium-voltage AC to 480V or 415V facility distribution, then often 54 VDC at the rack | Legacy low-voltage designs lose efficiency at these densities |
| Direction of travel | 800 VDC | Fewer conversion stages, less copper, conversion centralized at room level |
| Direct-to-chip liquid cooling | Removes up to 75% of rack heat load | The primary option above roughly 80 kW per rack |
| Rear-door heat exchangers | Effective up to about 80 kW, depending on unit configuration | A practical complement to direct-to-chip in hybrid air/liquid designs |
| GB200 NVL72 reference architecture (Vertiv with NVIDIA) | Up to 132 kW per rack | A benchmark for what a production AI rack actually needs |
| OCP-aligned rack concepts (Vertiv) | Up to 142 kW | The upper edge of current productized designs |
| NTT DATA, April 2024 | Direct liquid cooling designed for up to 200 kW per rack | An older ceiling on the cooling design, not a delivered rack figure; pair it with the 2026 numbers above rather than substituting it |

Two operational facts follow from that table. Racks draw roughly ten times the power they did a decade ago, and cooling has moved from air to a mix of air and liquid. Vertiv's CoolPhase Flex, developed with Compass Data Centers, integrates both into one system that can convert from traditional workloads to liquid-cooled AI loads in under a day, which is the kind of conversion speed to ask about when a facility was designed for 8 kW racks and you are bringing 130 kW ones. At the campus level, Vertiv OneCore targets facilities from 10 MW to 250 MW and above, because speed to power, meaning grid capacity and interconnection queue time, has become the binding constraint on expansion.

## Contract and site checks that decide your real uptime

Downtime across Global 2000 companies runs to about $400 billion a year, an average of roughly $9,000 per minute. That number is the reason to read the SLA line by line instead of skimming for a percentage.

The SLA needs specific indicators: availability, response times, uptime commitments, and whether 7×24 support is included or billed separately. Have legal and IT read it together, since one cares about remedies and the other about escalation paths. Tier III or Tier IV certification is a useful reference for redundancy in cooling, power and network; SOC 2 and ISO 27001 speak to security and compliance controls.

Redundancy has a physical meaning worth verifying on a tour. Multiple separate redundant pathways for power and internet, plus duplicate components for servers and cooling, let maintenance happen without interrupting service. Fire suppression, redundant air conditioning and UPS are standard. Ask how the UPS behaves under step loads, not just what its nameplate rating is. EdgeConneX and Vertiv tested exactly that scenario, cycling between high-compute draw and idle, transferring between utility and generator, and pushing overload conditions, and concluded that AI-ready colo means power infrastructure validated against real load swings rather than megawatts for sale.

Operationally, confirm what "remote hands" covers. At NTT DATA it means technicians handling routine or ad hoc tasks such as replacing equipment, checking status or adjusting cabling. Broader managed services can include system administration, proactive monitoring, hardware assistance, backups and network equipment management. For monitoring, environmental sensors catch heat and humidity problems before hardware does, and DCIM should be reachable through a web interface and export in standard formats so it feeds your own systems.

Unless the SLA explicitly includes network security, you build the virtual layer yourself. Physical access control, surveillance and on-site staff do not cover a compromised OS.

## Who should not colocate

Colocation costs you control of the facility. You stop setting the maintenance windows, the cooling design and the physical security posture, and you inherit neighbors. For government, healthcare and financial workloads under strict data sovereignty or privacy rules, shared infrastructure may be off the table regardless of certifications. Uptime Institute makes the counterargument for self-build: owning the facility gives complete visibility and lets you tune the risk profile per workload.

The middle path is where most teams end up. Put stable, predictable core workloads in colo, keep elastic or fast-changing workloads in a public cloud, and connect the two. Corning notes many enterprises run this Hybrid IT model specifically because it functions as a fault-tolerance safety net.

## Picking a route: three rules and two confirmations

**One to a handful of servers, no cage ambition.** Skip colocation. You would be buying rack space, a power commitment, bandwidth and remote-hands time on top of hardware you have to purchase and license. A single Xeon E3-1280 v5 box with 32 GB RAM and 1 TB NVMe is listed at $79/mo, or a 32 vCPU / 32 GB VPS at $89/mo, both monthly with no hardware to amortize.

👉 [Compare the dedicated and VPS configurations against your current server](https://bit.ly/Spinservers)

**A cage or a hall, 250 kW or more.** Go wholesale and negotiate on committed kW, not on a $/kW rate quoted at full fill. Ask what the facility can deliver in 12 and 24 months inside the same contract.

**Loads that swing hard.** Training and inference clusters spend time near idle and then pull everything the circuit allows. Ask whether the provider has tested its UPS against that pattern, and how quickly a zone can be converted from air to liquid cooling.

Before you sign anything, two items deserve a written answer: whether your specific hardware qualifies for standard colocation service or needs a sales conversation first, and the exact SLA text covering availability, response time and support hours. Everything else on this list you can renegotiate later. Those two are hard to fix after your equipment is racked.

👉 [See SpinServers' colocation quote process and published plans](https://bit.ly/Spinservers)
