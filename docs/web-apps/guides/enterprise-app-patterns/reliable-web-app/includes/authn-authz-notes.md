---
author: ssumner
ms.author: ssumner
ms.date: 10/15/2024
ms.topic: include
ms.service: azure-architecture-center
---
- *Prefer temporary access to storage.* Use temporary permissions to safeguard against unauthorized access and breaches, such as [shared access signatures (SASs)](/rest/api/storageservices/delegate-access-with-shared-access-signature). Use User Delegation SASs to maximize security when granting temporary access. It's the only SAS that uses Microsoft Entra ID credentials and doesn't require a permanent storage account key.

- *Enforce authorization in Azure.* Use [Azure RBAC](/azure/role-based-access-control/best-practices) to assign least privileges to user identities. Azure RBAC determines what Azure resources identities can access, what they can do with those resources, and what areas they have access to.

- *Avoid permanent elevated permissions.* Use [Microsoft Entra Privileged Identity Management](/entra/id-governance/privileged-identity-management/pim-configure) to grant just-in-time access for privileged operations. For example, developers often need administrator-level access to create/delete databases, modify table schemas, and change user permissions. With just-in-time access, user identities receive temporary permissions to perform privileged tasks.