---
up: "[[VMware MOC]]"
date: 2024-06-14
aliases:
  - DRS
  - vmware DRS
  - distributed resource scheduler
title: VMware Distributed Resource Scheduler
tags:
  - vmware/DRS
  - vmotion
  - interview-question
draft: true
---
## Overview
**Distributed Resource Scheduler (DRS)** designed by VMware to ensure optimal VM performance. VMware DRS achieves this by automatically **distributing VMs across vSphere hosts based on workload characteristics**. This ensures that VMs consume the host resources in an equitable manner and that a single host in a cluster isn't carrying a disproportionate share of the workload.

DRS is not typically marketed as an availability tool, but it can help admins **keep mission-critical workloads online in a failure situation**. **DRS constantly monitors the hosts within a cluster so that it can rebalance the workload if necessary**. This monitoring process enables DRS to detect when the system adds new hosts to a cluster or when existing cluster nodes go offline. If DRS detects that a node is not online -- the node has failed -- it can **use Storage vMotion to move VMs off of the failed node and onto a functional node**.

VMware Distributed Resource Scheduler (DRS) provides **scheduling and load balancing across vSphere cluster**.  VMware DRS ensure the virtual machines running inside vSphere environment are provided with the resources they need to run effectively and efficiently.  

DRS **runs every 5 minutes** to determines if there are any imbalances that exist in the cluster.  If so, a vMotion will be performed to move designed VMs from one ESXi host to another.

## DRS Automation Levels
One of the interesting features of DRS is the DRS automation levels. While DRS continues to scan the vSphere Cluster and provide recommendations every 5 minutes, you can determine whether or not DRS is able to enact its recommendations automatically or only suggest changes that should be made. DRS has three DRS automation levels. These include:

* **Fully automated** – In the fully automated approach, DRS applies both the initial placement and load balancing recommendations automatically
* **Partially Automated** – With partial automation, DRS applies recommendations only for initial placement of VMs
* **Manual** – In manual mode, you must apply the recommendations for both initial placement and load balancing recommendations
