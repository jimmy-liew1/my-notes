---
date: 2025-07-31
created: 2025-07-31 11:07
title: Azure availability set
tags:
  - type/literature-note
  - azure
link:
---
An **Azure Availability Set** is a logical grouping of virtual machines (VMs) that helps ensure your application remains available if a hardware failure occurs within an Azure datacenter. It provides redundancy and fault tolerance for your VMs.

## Key Concepts:
* **Fault Domains:** Azure places VMs in an Availability Set across different fault domains. A fault domain represents a group of VMs that share a common power source and network switch. If a hardware failure occurs, only one fault domain is affected, ensuring your application remains available. By default, there are 3 fault domains.
* **Update Domains:** Update domains determine the order in which VMs are updated during planned maintenance. Azure updates one update domain at a time, ensuring that your application remains available during updates. By default, there are 5 update domains.

## Benefits:
* **High Availability:** Provides redundancy and fault tolerance for your VMs.
* **Planned Maintenance:** Azure updates VMs in update domains, minimizing downtime during planned maintenance.
* **Service Level Agreement (SLA):** Using Availability Sets can help you achieve a higher SLA for your application.

## How it Works:
1. When you create an Availability Set, you specify the number of fault and update domains.
2. Azure automatically distributes your VMs across the fault domains.
3. During planned maintenance, Azure updates VMs in one update domain at a time.
4. If a hardware failure occurs, only VMs in one fault domain are affected.

## Considerations:
* **Placement:** All VMs in an Availability Set must be in the same region.
* **Configuration:** You can't change the fault domain or update domain count after the Availability Set is created.
* **Cost:** There is no additional cost for using Availability Sets.