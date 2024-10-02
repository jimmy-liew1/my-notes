---
aliases:
  - AMA
up: "[[Azure MOC]]"
draft: false
tags:
  - azure
---
# Overview
Azure Monitor Agent (AMA) collects monitoring data from the guest operating system of Azure and hybrid virtual machines, on-premises machines, and other cloud environments.  The data is then sent to [[Azure Monitor]] for use by features, insights, and other services such as [Microsoft Sentinel](https://learn.microsoft.com/en-us/azure/sentinel/overview) and [Microsoft Defender for Cloud](https://learn.microsoft.com/en-us/azure/defender-for-cloud/defender-for-cloud-introduction).[^1]

AMA replaces the [[Log Analytics agent]], also known as [[MMA|Microsoft Monitor Agent (MMA)]] and [[OMS]], for Windows and Linux machines, in Azure and non-Azure environments, on-premises and other clouds.

It uses [[Data Collection Rules|Data Collection Rules (DCRs)]] for flexible data management and supports centralized configuration. Unlike the older Log Analytics agent, which retired on August 31, 2024, AMA offers enhanced features and capabilities, such as centralized configuration, data collection rules, and improved security.

> [!INFO]- Note:
> Azure Monitor Agent replaces the [Legacy Agent](https://learn.microsoft.com/en-us/azure/azure-monitor/agents/log-analytics-agent) for Azure Monitor. The Log Analytics agent is on a **deprecation path** and won't be supported after **August 31, 2024**. Any new data centers brought online after January 1 2024 will not support the Log Analytics agent. If you use the Log Analytics agent to ingest data to Azure Monitor, [migrate to the new Azure Monitor agent](https://learn.microsoft.com/en-us/azure/azure-monitor/agents/azure-monitor-agent-migration) prior to that date.

## Architecture
This reference architecture shows how to use [[Azure Monitor]] to monitor the performance and availability of operating system (OS) workloads that run in virtual machines (VMs). The VMs can be in Microsoft Azure, in on-premises environments, or in non-Azure clouds.[^3]

![image](https://learn.microsoft.com/en-us/azure/architecture/hybrid/images/hybrid-perf-monitoring.png)

## Key Points
- **Installation:** AMA can be installed on individual machines or at scale using Azure Policy, VM extensions, or other tools. It can also be automatically installed when enabling certain features.[^2]
- **Data Collection Rules (DCRs):** These rules define what data to collect, how to transform it, and where to send it. DCRs allow for flexible and centralized data collection management.
- **Deprecation of Legacy Agents:** AMA replaces the older Log Analytics agent, which will be deprecated. Users are encouraged to migrate to AMA for enhanced capabilities.
- **Integration:** AMA integrates seamlessly with other Azure services, enhancing monitoring and security capabilities.
## Key Features
1. **Data Collection Rules (DCRs):** AMA uses DCRs to define what data to collect, how to transform it, and where to send it. This allows for flexible and centralized data collection management.[^1]
2. **Installation Methods:** You can install AMA on individual machines or at scale using Azure Policy, VM extensions, or other tools. It can also be automatically installed when enabling certain features.[^2]
3. **Compatibility:** AMA supports various operating systems and environments, making it versatile for different setups.[^1]

## Why Use Azure Monitor Agent?
- **Enhanced Data Collection:** Unlike the legacy Log Analytics agent, AMA provides more advanced data collection capabilities and is designed to replace the older agent, which will be deprecated.[^1]
- **Centralized Management:** With DCRs, you can manage data collection rules centrally, applying them to multiple machines as needed.[^1]
- **Integration with Azure Services:** AMA integrates seamlessly with other Azure services, enhancing your monitoring and security capabilities.[^1]


[^1]: [Azure Monitor Agent overview - Azure Monitor | Microsoft Learn](https://learn.microsoft.com/en-us/azure/azure-monitor/agents/azure-monitor-agent-overview)
[^2]: [Install and manage Azure Monitor Agent - Azure Monitor | Microsoft Learn](https://learn.microsoft.com/en-us/azure/azure-monitor/agents/azure-monitor-agent-manage?tabs=azure-portal)
[^3]: [Monitor hybrid availability, performance - Azure Architecture Center | Microsoft Learn](https://learn.microsoft.com/en-us/azure/architecture/hybrid/hybrid-perf-monitoring)