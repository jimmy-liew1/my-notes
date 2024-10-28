---
date: 2024-10-21
created: 2024-10-21 11:10
tags:
  - type/fleeting-note
  - azure
  - networking
link:
---
# Network Endpoints
**Network endpoints** in Azure are used to secure and control access to your Azure services from your virtual network (VNet).[^1]  By configuring network endpoints, you can ensure that only resources within your VNet can access specific Azure services, without needing a public IP address.[^1]  This helps improve security by reducing exposure to public internet.[^1]

# Private Endpoint 
A **private endpoint** is a special network interface in your VNet that connects to an Azure service.[^2]  When you create a private endpoint for a service like Azure Storage or Azure SQL Database, it provides a secure and private connection between your VNet and the service.[^2]  The private endpoint is assigned an IP address from your VNet's address range, and traffic between your VNet and Azure service stays on the Microsoft network, eliminiting exposure to the public internet.[^2]

# Private DNS Zone
**Azure Private DNS** is DNS service that works within your VNet.[^3]  It allows you to manage and resolve domain names without needed a custom DNS solution.[^3]  By using private DNS zones, you can use your own custom domain names instead of the default Azure-provided names.[^3]  This simplifies DNS management and ensure that your resources can be resolve domain names correctly within your VNet.[^3]


<!-- Footnotes -->
[^1]: [Azure virtual network service endpoints | Microsoft Learn](https://learn.microsoft.com/en-us/azure/virtual-network/virtual-network-service-endpoints-overview)
[^2]: [Use private endpoints - Azure Storage | Microsoft Learn](https://learn.microsoft.com/en-us/azure/storage/common/storage-private-endpoints)
[^3]: [What is Azure Private DNS? | Microsoft Learn](https://learn.microsoft.com/en-us/azure/dns/private-dns-overview)