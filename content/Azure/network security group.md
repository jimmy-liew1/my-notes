---
up: "[[Azure MOC]]"
date: 2025-08-03
created: 2025-08-03 13:08
title: Network Security Group
aliases:
  - NSG
  - NSGs
tags:
  - networking
  - azure
link:
---
**Network Security Groups (NSGs)** are used to control access to and from resources within a virtual network. They act as a basic, stateful firewall that allows or denies traffic based on rules defined by IP address and TCP/UDP protocols. NSGs can be applied to individual network interfaces or subnets to manage traffic flow.

You can associate zero or one network security group to each subnet in a virtual network. You can associate the same or a different network security group to each subnet. Each network security group contains rules that allow or deny traffic to and from sources and destinations.

### Related Concept
* [[Application Security Group]]