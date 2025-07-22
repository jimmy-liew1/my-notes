---
date: 2025-07-20
created: 2025-07-20 15:07
tags:
  - azure
  - type/literature-note
link:
---
## Understanding Update Domains
An **update domain** is a logical group of VMs within an Availability Set that can be updated or rebooted at the same time during planned maintenance by Azure. Azure ensures that only one update domain is updated at any given time. This guarantees that at least one instance of your application remains running during planned maintenance events.

## Maximum Number of Update Domains 
The maximum number of **update domains** you can configure in an Azure Availability Set is **20**.

While the default or commonly recommended number for high availability against planned maintenance is **5**, Azure allows for up to 20 update domains.2 This higher limit can be useful in specific scenarios, particularly for very large deployments where minimizing the number of instances down during a rolling update is critical.

## Availability Domains in Azure Availability Sets
When configuring virtual machines (VMs) for high availability within an Azure Availability Set, aim for a maximum of **5 update domains**.

### Understanding Update Domains
An **update domain** is a logical grouping of VMs within an Availability Set that are updated or rebooted together during planned Azure maintenance. Azure ensures only one update domain is updated at a time, minimizing downtime.

### Why 5 Update Domains?
Azure's recommended maximum for update domains in an Availability Set is **5**. This configuration strikes a balance between high availability and resource efficiency.
* **Spreading the Risk:** With 5 update domains, VMs are distributed across different logical groups. During maintenance, only a portion of your application instances (at most 1/5th) are unavailable.
* **Balancing Availability and Resource Consumption:** While more update domains could theoretically spread the risk further, the benefits diminish quickly beyond 5.
* **Indirect Hardware Failure Mitigation:** Update domains, combined with **fault domains**, indirectly contribute to high availability during hardware failures. Fault domains are physical groupings of hardware (e.g., power, cooling, network). Azure automatically spreads VMs across multiple fault domains (typically 2 or 3) and update domains.

### Key Considerations
* **Minimum Instances:** To effectively utilize update domains, have at least **two or more VM instances** in your Availability Set.
* **Application Design:** Your application should be designed to handle instance failures gracefully (stateless or with failover capabilities).
* **Planned vs. Unplanned Events:**
    * **Update Domains:** Protect against **planned maintenance**.
    * **Fault Domains:** Protect against **unplanned hardware failures**.
    * **Availability Sets:** Combine both update and fault domains for comprehensive high availability within a single Azure region.

Configuring your Availability Set with 5 update domains and deploying multiple VM instances significantly increases application resilience against both planned maintenance and unexpected hardware failures.

### Related
*   [[202507201402 - availability sets]]
*   [[202507201406 - availability zones]]