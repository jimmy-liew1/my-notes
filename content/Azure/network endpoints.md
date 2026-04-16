---
up: "[[Azure MOC]]"
date: 2024-10-21
created: 2024-10-21 11:10
title: Network endpoints
tags:
  - azure
  - networking
link: https://learn.microsoft.com/en-us/azure/virtual-network/virtual-network-service-endpoints-overview
---
**Network endpoints** in Azure provide a secure and direct connection to Azure services from your virtual network (VNet). They enhance security by restricting access, allowing resources within your VNet to access specific Azure services without needing a public IP address. This reduces exposure to the public internet and can improve performance by optimizing the network path. 

Key benefits include: 
* **Enhanced Security:** Restrict access to Azure services, reducing the attack surface. 
* **Optimized Performance:** Direct connection within the Azure network. 
* **Simplified Network Architecture:** No need for public IP addresses for service access. 

Commonly used with services like Azure Storage, Azure SQL Database, and Azure Cosmos DB.