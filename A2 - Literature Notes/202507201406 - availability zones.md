---
date: 2025-07-20
created: 2025-07-20 14:07
title: Availability zones
tags:
  - azure
  - type/literature-note
link: https://learn.microsoft.com/en-us/training/modules/configure-virtual-machine-availability/5-review-availability-zones
---
**Availability zones** are a highly availability offering that protect applications and data from datacenter failure.  An availability zone in an Azure region is a combination of a [[202507311128 - fault domains|fault domain]] and an [[202507311130 - update domains|update domain]].

Consider a scenario where you create three or more virtual machines across three zones in an Azure region. Your virtual machines are effectively distributed across three fault domains and update domains. The Azure platform recognizes this distribution across update domains to make sure that virtual machines in different zones aren't updated at the same time.

You can use availability zones to build high-availability into your application architecture by collocating your compute, storage, networking, and data resources within a zone and replicating in other zones.

### Things to know about availability zones
Review the following characteristics of availability zones.
- Availability zones are unique physical locations within an [[Azure region]].
- Each zone is made up of one or more datacenters that are equipped with independent power, cooling, and networking.
- To ensure resiliency, there's a minimum of three separate zones in all enabled regions.
- The physical separation of availability zones within a region protects applications and data from datacenter failures.
- Zone-redundant services replicate your applications and data across availability zones to protect against single-points-of-failure.

### Things to consider when using availability zones
Azure services that support availability zones are divided into two categories.

| Category                    | Description                                                                                         | Examples                                                                     |
| --------------------------- | --------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| **Zonal services**          | Azure _zonal_ services pin each resource to a specific zone.                                        | - Azure Virtual Machines<br>- Azure managed disks<br>- Standard IP addresses |
| **Zone-redundant services** | For Azure services that are zone-redundant, the platform replicates automatically across all zones. | - Azure Storage that's zone-redundant<br>- Azure SQL Database                |

## Related Notes
- [[availability zones]]

## Related Concepts
* [[202507201402 - availability sets]]
* [[azure region|Azure region]]
* [[202507311130 - update domains]]
* [[202507311128 - fault domains]]