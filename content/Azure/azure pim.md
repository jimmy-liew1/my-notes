---
up: "[[Azure MOC]]"
date: 2026-03-04
created: 2026-03-04 13:03
title: Azure Privileged Identity Management
aliases:
  - Azure PIM
tags:
  - azure
link:
---
**Azure Privileged Identity Management (PIM)** is a managed service within Microsoft Entra ID (formerly [[azure active directory|Azure Active Directory]]) designed to oversee, control and monitor access to important resources.  It mitigates the risks associated with "standing access" by ensuring only users have elevated permissions when necessary.

<iframe width="560" height="315" src="https://www.youtube.com/embed/f-0K7mRUPpQ?si=ikv2oXMVYF9SUNZD" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
## What is Privileged Identity Management?
Privileged Identity Management (PIM) provides **time-based** and **approval-based** role activation to mitigate the risks of excessive, unnecessary, or misused access permissions on resources.  Azure PIM allows users only have high-level permissions when they actually need them - reducing risk from standing admin access.  It enables users to elevate access **only when needed**.  Here are some of the key features of PIM.

Manage, control, and monitor access to important resources. [^1]
- Provide **just-in-time** privileged access to resources and directory.
- Assign **time-bound** access to resources using start/end dates.
- Require **approval** to activate privileged roles.
- Enforce **multi-factor authentication** to activate any role.
- Use **justification** to understand why users activate.
- Get **notifications** when privileged roles are activated.
- Conduct  **access reviews** to ensure users still need roles.

## References / Sources
- [What is Microsoft Entra PIM?](https://learn.microsoft.com/en-us/entra/id-governance/privileged-identity-management/pim-configure) | Microsoft Learn