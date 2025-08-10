---
date: 2025-07-28
created: 2025-07-28 13:07
tags:
  - type/literature-note
  - azure
link:
---
## Persisting Data in Azure Container Instances
To persist data for Azure Container Instances (ACI), you can use **Azure Files**. Azure Files provides fully managed file shares hosted in Azure Storage, accessible via the Server Message Block (SMB) protocol. This allows your containerized applications to read and write data to a persistent storage location.

### How it Works
1. **Stateless Containers:** By default, ACI containers are stateless. Data written to the container's local filesystem is lost when the container stops or restarts.
2. **Azure Files as Persistent Storage:** To preserve data, you mount an external volume. Azure Files offers file shares that ACI can directly mount.
3. **Configuration:** To configure persistent storage, create an **Azure File Share** within an Azure Storage account. This file share can then be mounted to your container instance.

**Example:**
To persist data for a container instance named `container1`, you would:
1. Create an Azure Storage account (e.g., `vmstorageaccount1`).
2. Create an Azure File Share within `vmstorageaccount1`.
3. Mount the Azure File Share to `container1`.

### Benefits
*  **Data Persistence:** Ensures data is not lost when the container stops or restarts.
*  **Shared Storage:** Allows multiple containers to access the same data.
*  **Managed Service:** Azure Files is a fully managed service, simplifying storage management.

### References
*  [Mount Azure Files volume to container group - Azure Container Instances | Microsoft Learn](https://learn.microsoft.com/azure/container-instances/container-instances-volume-azure-files)
*  [Explore Azure Storage services - Training | Microsoft Learn](https://learn.microsoft.com/training/modules/configure-storage-accounts/3-explore-azure-storage-services?ns-enrollment-type=learningpath&ns-enrollment-id=learn.az-104-manage-storage)
*  [Persistent Docker volumes with Azure File Storage](https://azure.microsoft.com/en-us/blog/persistent-docker-volumes-with-azure-file-storage/)
*  [Configure Azure Container Instances - Training](https://learn.microsoft.com/en-us/training/modules/configure-azure-container-instances/)