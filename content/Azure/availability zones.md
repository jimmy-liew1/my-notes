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

The following diagram demonstrates several example Azure regions. Regions 1 and 2 support availability zones, and regions 3 and 4 don't have availability zones.
![image](https://learn.microsoft.com/en-us/azure/reliability/media/regions-availability-zones.png)