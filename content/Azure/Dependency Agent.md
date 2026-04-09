---
date: 2024-10-21
created: 2024-10-21 17:10
aliases:
  - DA
tags:
  - azure
link:
title: Dependency Agent
---
The **Dependency Agent** is used in conjunction with [[azure monitor]] for VMs.[^1]  It collects data about processes running on the virtual machine and their external dependencies.[^1]  This data is used to create a map of the application's architecture, showing how different components interact with each other.[^1]

> [!IMPORTANT]- Important:
> The Dependency Agent and the Map experience in VM Insights will be retired on **30 June 2028**.
> See [the retirement guidance](https://aka.ms/DependencyAgentRetirement) for more details.

> [!INFO]- Note:
> Dependency Agent sends heartbeat data to the [InsightsMetrics](https://learn.microsoft.com/en-us/azure/azure-monitor/reference/tables/insightsmetrics) table, for which you incur data ingestion charges. This behavior is different from Azure Monitor Agent, which sends agent health data to the [Heartbeat](https://learn.microsoft.com/en-us/azure/azure-monitor/reference/tables/heartbeat) table that is free from data collection charges.

### Other Resources
* [Dependency Agent in Azure Monitor VM insights](https://learn.microsoft.com/en-us/azure/azure-monitor/vm/vminsights-dependency-agent)
* [VM Insights Map and Dependency Agent retirement guidance](https://learn.microsoft.com/en-us/azure/azure-monitor/vm/vminsights-maps-retirement)

<!-- Footnotes -->
[^1]: [VM Insights Dependency Agent - Azure Monitor | Microsoft Learn](https://learn.microsoft.com/en-us/azure/azure-monitor/vm/vminsights-dependency-agent-maintenance)