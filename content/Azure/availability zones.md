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

In the world of cloud computing, hardware failures and local disasters are inevitable. To mitigate these risks, Microsoft Azure provides **Availability Zones** as a high-availability solution. By distributing applications and data across physically separate locations within a single region, organizations can ensure that their services remain operational even if an entire data center experiences a power outage, cooling failure, or network disruption.

## Physical Infrastructure and Resiliency
An Availability Zone is not just a logical label; it represents a distinct physical location within an [[azure region|Azure region]].  Each zone is composed of one or more datacenters equipped with independent infrastructure.
- **Independent Power & Cooling:** Each zone operates on its own utility grid and cooling systems to prevent a single point of failure from affecting the entire region.
- **Fault and Update Domains:** At a technical level, a zone acts as a combination of a [[fault domain]] and an [[update domain]], ensuring that both unplanned hardware failures and planned maintenance do not take down all instances of a service simultaneously. 
- **The Rule of 3:** To guarantee a high level of resiliency, any Azure region that supports this feature is required to have a minimum of **three separate availability zones**.

## Geographic Strategy and Latency
The physical placement of these zones is carefully engineered to balance safety with performance. 
- **Proximity for Performance:** Zones are typically located within 100 kilometers of each other. This specific distance allows for low-latency, synchronous data replication, ensuring that data stays consistent across zones without slowing down application performance. 
- **Isolation for Safety:** While they are close enough for high-speed networking, they are far enough apart to be isolated from local disasters, such as flooding or localized fires. Microsoft performs rigorous risk assessments to ensure that zones do not share significant vulnerabilities.

## Zonal vs. Zone-Redundant 
When architecting solutions in Azure, you can choose how your resources interact with these zones based on your availability requirements: 
- **Zonal Services:** These allow you to "pin" a resource to a specific zone (e.g., a Virtual Machine in Zone 1). This is often used when you need to minimize latency between specific components. 
- **Zone-Redundant Services:** In this model, the Azure platform automatically replicates your resources across multiple zones (e.g., Zone-redundant storage or SQL databases). This provides the highest level of automated protection without requiring manual configuration.

## Visual Representation
The following diagram illustrates how Availability Zones are structured within supported regions (Regions 1 & 2) compared to regions without zone support (Regions 3 & 4).

![image](https://learn.microsoft.com/en-us/azure/reliability/media/regions-availability-zones.png)

## Related Concepts
- [[azure region|Azure region]] 
- [[fault domain|Fault Domain]] 
- [[update domain|Update Domain]] 
- [[disaster recovery|Disaster Recovery]]