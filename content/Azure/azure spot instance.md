---
up: "[[Azure MOC]]"
date: 2025-07-28
title: Azure Spot Instance
created: 2025-07-28 13:07
aliases:
  - Spot Instances
  - Azure spot instances
  - spot instance
  - Azure spot instance
tags:
  - azure/compute
  - azure/cost-management
  - type/concept
link: https://learn.microsoft.com/azure/virtual-machines/spot-vms
---
Cloud providers like Microsoft Azure maintain massive amounts of hardware to ensure they can meet peak demand from customers worldwide. However, this often results in "spare" capacity that sits idle during non-peak hours. To maximize data center efficiency, Azure offers this excess capacity to users at a fraction of the normal cost. This creates a win-win scenario: Azure utilizes its hardware more effectively, and customers can run large-scale workloads at a significantly reduced price point, provided those workloads can handle occasional interruptions. 

> [!abstract] Definition 
> **Azure Spot Instances** are a cost-effective deployment option that allows you to leverage unused Azure compute capacity at a significant discount—up to **90% off** standard pay-as-you-go prices. In exchange for this discount, Azure can "evict" (reclaim) these instances whenever the capacity is needed for standard workloads.

**Azure Spot instances** allow you to provision virtual machines at a reduced cost, but these virtual machines can be stopped by Azure when Azure needs the capacity for other pay-as-you-go workloads, or when the price of the spot instance exceeds the maximum price that you have set. These virtual machines are good for dev, testing, or for workloads that do not require any specific SLA.

**Azure Spot Virtual Machines** (also called Spot Instances) are ==a cost-effective way to run stateless and interruptible workloads on Azure by leveraging unused capacity at a significant discount== (up to 90% off pay-as-you-go prices). These instances can be evicted with short notice (30 seconds) when Azure needs the capacity back. They are suitable for workloads that can tolerate interruptions, like batch processing, testing, and development environments.

## 1. The Eviction Mechanism 
The defining characteristic of a Spot Instance is its **interruptibility**. Because these virtual machines run on spare capacity, they do not have the same availability guarantees as standard VMs. 
- **Eviction Triggers:** Azure will reclaim the capacity if it is needed for pay-as-you-go customers or if the current market price for the instance exceeds the **maximum price** you have set. 
- **The 30-Second Notice:** When Azure decides to evict an instance, it provides a **30-second eviction notice** via Azure Scheduled Events. This brief window allows applications to perform a "graceful shutdown," such as saving state or draining active connections. 
- **Eviction Policy:** Users can configure the VM to either be **Deallocated** (stopped, but preserving the disk and configuration) or **Deleted** entirely upon eviction. 
## 2. Cost Strategy and FinOps 
Spot Instances are a primary tool for [[topic/finops|FinOps]] teams looking to optimize cloud spend. Unlike [[reserved instances]], which require a one- or three-year commitment, Spot Instances offer "just-in-time" savings. 
- **Dynamic Pricing:** The price of Spot Instances fluctuates based on the supply and demand of a specific VM size within a specific [[azure region|Azure region]]. 
- **No SLA:** It is critical to remember that Spot Instances carry **no Service Level Agreement (SLA)** for uptime. Their value is found in cost reduction, not in high availability. 
- **Maximum Price Setting:** You can choose to pay up to the standard pay-as-you-go price or set a specific cap. If the market price rises above your cap, the VM is evicted. ## 3. Implementation and Ideal Workloads Because Spot Instances can be interrupted at any time, they are not suitable for mission-critical databases or primary web servers. Instead, they should be used for **stateless** or **distributed** workloads. 
- **Batch Processing:** Tasks like data transformation, genomic sequencing, or media rendering that can be paused and resumed are ideal. 
- **Dev/Test Environments:** Non-production environments where a temporary shutdown won't impact customers are perfect candidates for cost-saving. 
- **Scale Sets:** Using Spot Instances within [[virtual machine scale sets]] allows you to maintain a "baseline" of standard VMs while "bursting" into Spot Instances for extra processing power at a low cost.

## 3. Implementation and Ideal Workloads 
Because Spot Instances can be interrupted at any time, they are not suitable for mission-critical databases or primary web servers. Instead, they should be used for **stateless** or **distributed** workloads. 
- **Batch Processing:** Tasks like data transformation, genomic sequencing, or media rendering that can be paused and resumed are ideal. 
- **Dev/Test Environments:** Non-production environments where a temporary shutdown won't impact customers are perfect candidates for cost-saving. 
- **Scale Sets:** Using Spot Instances within [[virtual machine scale sets]] allows you to maintain a "baseline" of standard VMs while "bursting" into Spot Instances for extra processing power at a low cost.

### Related Concepts
* [[reserved instances|Reserved Instance]]
* [[azure region|Azure regions]]
* [[virtual machine scale sets|Virtual machine scale sets]]
* [[disaster recovery|Disaster recovery]]

## References
* [Use Azure Spot Virtual Machines - Azure Virtual Machines | Microsoft Learn](https://learn.microsoft.com/azure/virtual-machines/spot-vms)
* [Configure virtual machine availability - Training | Microsoft Learn](https://learn.microsoft.com/training/modules/configure-virtual-machine-availability/)
* [Reserved Instances vs. Spot Instances: Maximize Your Savings Today](https://www.alphaus.cloud/en/blog/reserved-instances-vs-spot-instances-maximize-your-savings-today)