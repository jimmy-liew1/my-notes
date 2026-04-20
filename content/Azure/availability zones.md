---
up: "[[Azure MOC]]"
date: 2025-07-27
created: 2025-07-27 22:07
title: Availability zones
aliases:
  - availability zone
  - availability zones
tags:
  - azure
link: https://learn.microsoft.com/en-us/azure/reliability/availability-zones-overview
---
> [!abstract] Definition 
> **Availability zones** are a high-availability offering that protects data and applications from data center failures. They are unique physical locations within an [[azure region|Azure region]], each made up of one or more datacenters equipped with independent power, cooling, and networking.

**Availability zones** are highly-availability offering that protect data and applications from data center failure.  An availability zone in an [[azure region|Azure region]] is a combination of a [[fault domain]] and [[update domain]].

Availability zones are distinct groups of data centers within a region. They feature independent power, cooling, and networking, ensuring that if one zone fails, the others maintain regional services, capacity, and high availability.

Availability zones are usually separated by several kilometers, typically within 100 kilometers. This proximity allows for low-latency connections via a high-performance network. The distance also minimizes the risk of multiple zones being impacted by local outages or weather events.

Datacenter locations are chosen based on rigorous vulnerability risk assessments. This process identifies significant datacenter-specific risks and considers shared risks across availability zones.

## Key Characteristics 
- **Composition:** A combination of a [[fault domain]] and [[update domain]]. 
- **The Rule of 3:** Any Azure region that supports availability zones must have a minimum of **three** separate availability zones to ensure regional resiliency. 
- **Infrastructure:** Each zone is a distinct group of data centers with independent power, cooling, and networking. 
- **Redundancy:** If one zone fails, the others continue to provide re`gional services. 
- **Proximity / Distance:** Zones are typically located within 100 kilometers of each other. This allows for low-latency connections via a high-performance network while remaining far enough apart to minimize the risk of a single local outage affecting multiple zones. 
- **Risk Assessment:** Datacenter locations are chosen based on rigorous vulnerability risk assessments to identify shared risks across zones.
## Service Types 
Azure services use availability zones in two primary ways: 
- **Zonal Services:** The resource is pinned to a specific zone (e.g., Virtual Machines, IP addresses). 
- **Zone-redundant Services:** The platform replicates automatically across zones (e.g., Zone-redundant storage, Virtual Machine Scale Sets).

## Visual Representation
The following diagram demonstrates several example Azure regions. Regions 1 and 2 support availability zones, and regions 3 and 4 don't have availability zones.
![image](https://learn.microsoft.com/en-us/azure/reliability/media/regions-availability-zones.png)

## Related Concepts
- [[azure region|Azure regions]] 
- [[fault domain|Fault Domain]] 
- [[update domain|Update Domain]] 
- [[disaster recovery|Disaster Recovery]]