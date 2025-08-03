---
date: 2025-06-07
created: 2025-06-07 11:06
title: Managed identities
aliases:
  - MI
tags:
  - azure
link:
---
**Managed Identities (MI)** are identities that managed by Azure which provide an easy way for Azure services to authenticate to other Azure Services that support [[Azure AD|Azure Active Directory (AD)]] authentication.  **With managed identities, you don't need to manage or store credentials (like passwords or certificates) in your code or configuration. Azure automatically generates and manages the credentials, making authentication more secure.**

### Key Characteristics
Key characteristics of Managed Identities include but not limited to:
- Managed identities are meant only for **authentication with services that support Azure AD as an identity provider**.
- They come in **two flavors**:
    - **System-assigned managed identities:** These are tied directly to an Azure resource (e.g., a virtual machine, an App Service, an Azure Function) and have the same lifecycle as that resource. When the resource is deleted, the system-assigned managed identity is also deleted.
    - **User-assigned managed identities:** These are created as standalone Azure resources and can be assigned to multiple Azure services. Their lifecycle is independent of the resources they are assigned to.
- In the background, managed identities also **create a [[service principal]] along with a password**. However, you don't directly interact with these credentials.
- An Azure resource with a managed identity can request a token from the **[[Instance Metadata Service|Instance Metadata Service (IMDS)]]**, which is only accessible to that resource. The IMDS then obtains a token from Azure AD using a certificate known only to the IMDS, and returns it to the application. This token can then be used to authenticate to other Azure services.
- Managed identities should be **preferred over storing credentials** or using other authentication mechanisms for Azure-to-Azure communication.

The following video provides a deep dive into using managed identities and understanding what makes them tick.
<iframe width="560" height="315" src="https://www.youtube.com/embed/rC1TV0_sIrM?si=aEk5RnBhjwsxZjzu" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

In this video, Matt shows you explain about [what is managed identity?](https://www.youtube.com/watch?v=nIoqw4zBqIM&t=27s) and show you side-by-side comparison.
<iframe width="560" height="315" src="https://www.youtube.com/embed/nIoqw4zBqIM?si=FmRYo7QnaDCdr-CB" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

The following video shows how you can use managed identities:
<iframe width="560" height="315" src="https://learn-video.azurefd.net/vod/player?show=on-net&ep=using-azure-managed-identities" title="Using Azure Managed Identities" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

### Read More
* [Overview about managed identities for Azure resources](https://learn.microsoft.com/en-us/entra/identity/managed-identities-azure-resources/overview)