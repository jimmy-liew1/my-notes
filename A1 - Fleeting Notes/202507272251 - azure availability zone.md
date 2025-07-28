---
date: 2025-07-27
created: 2025-07-27 22:07
tags:
  - type/fleeting-note
link: https://learn.microsoft.com/en-us/azure/reliability/availability-zones-overview?tabs=azure-cli
---
Availability zones are typically separated by several kilometers, and usually are within 100 kilometers. This distance means they're close enough to have low-latency connections to other availability zones through a high-performance network. However, they're far enough apart to reduce the likelihood that more than one will be affected by local outages or weather.

Datacenter locations are selected by using rigorous vulnerability risk assessment criteria. This process identifies all significant datacenter-specific risks and considers shared risks between availability zones.

The following diagram shows several example Azure regions. Regions 1 and 2 support availability zones, and regions 3 and 4 don't have availability zones.
![image](https://learn.microsoft.com/en-us/azure/reliability/media/regions-availability-zones.png)