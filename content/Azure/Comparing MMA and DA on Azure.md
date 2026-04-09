---
date: 2024-10-21
created: 2024-10-21 17:10
tags:
  - azure
link:
title: Comparing MMA and DA on Azure
---
This note outlines the key distinctions between the [[Microsoft Monitoring Agent|Microsoft Monitoring Agent (MMA)]] and the [[Dependency Agent|Dependency Agent (DA)]] in the context of Azure. The primary difference lies in their purpose and the type of data they collect.

The **Microsoft Monitoring Agent (MMA)** is designed for broad data collection, gathering a wide array of performance and operational data from machines. It pulls information from various sources, including performance counters, event logs, and custom logs. MMA is typically used for general IT infrastructure monitoring and management, integrating with Azure Monitor to offer comprehensive monitoring and analytics capabilities.

In contrast, the **Dependency Agent (DA)** has a more specific focus: collecting data related to process dependencies and their interactions. It gathers information specifically about how processes rely on each other. DA is primarily used for mapping application dependencies and assisting with troubleshooting. It integrates with Azure Monitor for VMs to visualize these application dependency maps.

### Comparison of Differences between MMA and DA on Azure
Based on the provided note, the key differences between the Microsoft Monitoring Agent (MMA) and the Dependency Agent (DA) on Azure are:

* **Purpose:**
	* **MMA:** Collects a wide range of performance and operational data from machines.
	* **DA:** Focuses on collecting data about process dependencies and interactions.
* **Data Collection:**
	* **MMA:** Collects data from various sources, including performance counters, event logs, and custom logs.
	* **DA:** Collects data specifically about process dependencies and their interactions.
* **Usage:**
	* **MMA:** Used for general monitoring and management of IT infrastructure.
	* **DA:** Used for application dependency mapping and troubleshooting.
* **Integration:**
	* **MMA**: Integrates with Azure Monitor to provide comprehensives monitoring and analytics.
	* **DA:** Integrates with Azure Monitor for VMs to provide application dependency maps.

In essence, MMA is a general-purpose monitoring agent, while DA is specialized for understanding and visualizing application dependencies.