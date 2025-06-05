---
date: 2024-10-21
created: 2024-10-21 11:10
tags:
  - type/fleeting-note
  - azure
  - networking
link: https://learn.microsoft.com/en-us/azure/storage/common/storage-private-endpoints
---
A **private endpoint** is a special network interface in your VNet that connects to an Azure service.  When you create a private endpoint for a service like Azure Storage or Azure SQL Database, it provides a secure and private connection between your VNet and the service.  The private endpoint is assigned an IP address from your VNet's address range, and traffic between your VNet and Azure service stays on the Microsoft network, eliminating exposure to the public internet.

<iframe width="560" height="315" src="https://www.youtube.com/embed/57ZwdztCx2w?si=XTjqD8xlEu6aDoUv" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<iframe width="560" height="315" src="https://www.youtube.com/embed/rXbamGNz-xQ?si=__zKiIwBleoUMW8w" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
