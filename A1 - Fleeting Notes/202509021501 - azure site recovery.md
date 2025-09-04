---
date: 2025-09-02
created: 2025-09-02 15:09
title: Azure Site Recovery
aliases:
  - ASR
tags:
  - type/fleeting-note
  - azure
link:
---
**Azure Site Recovery (ASR)** is a service that helps you replicate physical servers, virtual machines, and other workloads to a secondary location. This allows you to recover from outages by failing over to the secondary location.

Here's a brief overview:
*   **Replication:** ASR replicates your data and applications to a secondary region or on-premises location.
*   **Failover:** In case of an outage, you can fail over to the secondary location to keep your applications running.
*   **Failback:** Once the primary location is available again, you can fail back to it.
*   **Disaster Recovery as a Service (DRaaS):** ASR provides a DRaaS solution, meaning you don't need to manage your own secondary infrastructure.
*   **Supported Workloads:** ASR supports various workloads, including VMware, Hyper-V, Windows, Linux, and Azure VMs.