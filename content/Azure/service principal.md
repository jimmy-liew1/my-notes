---
date: 2025-06-07
created: 2025-06-07 22:06
title: Service principal
aliases:
  - SPN
tags:
  - azure
link:
---
A **service principal** is an identity for an application or service within [[Azure active directory|Azure Active Directory (Azure AD)]], allowing it to authenticate and access Azure resources. Think of it as a **service account in the cloud**. Applications use service principals to authenticate to Azure AD and access resources like [[Azure Blob Storage]] or [[Azure Key Vault]], or to applications integrated with Azure AD (e.g., SaaS applications, custom applications). Service principals are assigned specific permissions to access resources.

[[Managed identity|Managed identities (MI)]], on the other hand, are identities managed by Azure, simplifying authentication for Azure services to other Azure services that support Azure AD authentication. They eliminate the need to manage or store credentials directly. Managed identities, in the background, also create a service principal.

**When to use a service principal:**
* When you need to grant an application or service access to Azure resources.
* When you need to automate tasks that require access to Azure resources.

### Related Concept
- [[Managed identity|Managed Identities]] (MI)