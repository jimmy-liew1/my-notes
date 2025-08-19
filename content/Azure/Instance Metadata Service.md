---
date: 2025-07-11
created: 2025-07-11 10:07
title: Instance Metadata Service
aliases:
  - IMDS
tags:
  - azure
  - networking
link:
---
The **Instance Metadata Service (IMDS)** is a service provided by Azure that allows running virtual machine (VM) instances to access information about themselves. This information is crucial for various tasks, including configuration, security, and monitoring.

### Accessing IMDS
IMDS is accessed from within the VM using the well-known, [[About the IP address 169.254.169.254|link-local IP address]]  `169.254.169.254`. VMs use this IP address to make requests to the IMDS and retrieve their metadata. The service typically uses a REST API for communication.

### Information Provided by IMDS
IMDS provides a range of information about the VM, including:
* **VM Details:** Name, size, and other configuration details.
* **Network Configuration:** IP addresses, DNS settings, and other network-related information.
* **Storage Configuration:** Information about attached disks.
* **Identity:** Information about the VM's [[managed identity]], if enabled.

### Use Cases
The information provided by IMDS is valuable for several purposes:
* **Configuration:** Applications can use the metadata to configure themselves based on the VM's environment.
* **Security:** Retrieving security-related information, such as managed identity tokens, for secure access to other Azure resources.
* **Monitoring:** Gathering information for monitoring and logging purposes, allowing for better insights into the VM's performance and health.