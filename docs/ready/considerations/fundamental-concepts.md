---
title: Azure fundamental concepts
description: Use the Cloud Adoption Framework for Azure to learn fundamental concepts and terms used in Azure and how the concepts relate to one another.
author: alexbuckgit
ms.author: abuck
ms.date: 05/20/2019
ms.topic: conceptual
ms.service: cloud-adoption-framework
ms.subservice: ready
ms.custom: internal
---

# Azure fundamental concepts

Learn fundamental concepts and terms that are used in Azure, and how the concepts relate to one another.

## Azure terminology

It's helpful to know the following definitions as you begin your Azure cloud adoption efforts:

- **Resource:** An entity that's managed by Azure. Examples include Azure Virtual Machines, virtual networks, and storage accounts.
- **Subscription:** A logical container for your resources. Each Azure resource is associated with only one subscription. Creating a subscription is the first step in adopting Azure.
- **Azure account:** The email address that you provide when you create an Azure subscription is the Azure account for the subscription. The party that's associated with the email account is responsible for the monthly costs that are incurred by the resources in the subscription. When you create an Azure account, you provide contact information and billing details, like a credit card. You can use the same Azure account (email address) for multiple subscriptions. Each subscription is associated with only one Azure account.
- **Account administrator:** The party associated with the email address that's used to create an Azure subscription. The account administrator is responsible for paying for all costs that are incurred by the subscription's resources.
- **Azure Active Directory (Azure AD):** The Microsoft cloud-based identity and access management service. Azure AD allows your employees to sign in and access resources.
- **Azure AD tenant:** A dedicated and trusted instance of Azure AD. An Azure AD tenant is automatically created when your organization first signs up for a Microsoft cloud service subscription like Microsoft Azure, Intune, or Microsoft 365. An Azure tenant represents a single organization.
- **Azure AD directory:** Each Azure AD tenant has a single, dedicated, and trusted directory. The directory includes the tenant's users, groups, and applications. The directory is used to perform identity and access management functions for tenant resources. A directory can be associated with multiple subscriptions, but each subscription is associated with only one directory.
- **Resource groups:** Logical containers that you use to group related resources in a subscription. Each resource can exist in only one resource group. Resource groups allow for more granular grouping within a subscription, and are commonly used to represent a collection of assets required to support a workload, application, or specific function within a subscription.
- **Management groups:** Logical containers that you use for one or more subscriptions. You can define a hierarchy of management groups, subscriptions, resource groups, and resources to efficiently manage access, policies, and compliance through inheritance.
- **Region:** A set of Azure datacenters that are deployed inside a latency-defined perimeter. The datacenters are connected through a dedicated, regional, low-latency network. Most Azure resources run in a specific Azure region.

## Azure subscription purposes

An Azure subscription serves several purposes. An Azure subscription is:

- **A legal agreement.** Each subscription is associated with an [Azure offer](https://azure.microsoft.com/support/legal/offer-details), such as a free trial or pay-as-you-go. Each offer has a specific rate plan, benefits, and associated terms and conditions. You choose an Azure offer when you create a subscription.
- **A payment agreement.** When you create a subscription, you provide payment information for that subscription, such as a credit card number. Each month, the costs incurred by the resources deployed to that subscription are calculated and billed via that payment method.
- **A boundary of scale.** Scale limits are defined for a subscription. The subscription's resources can't exceed the set scale limits. For example, there's a limit on the number of virtual machines that you can create in a single subscription.
- **An administrative boundary.** A subscription can act as a boundary for administration, security, and policy. Azure also provides other mechanisms to meet these needs, such as management groups, resource groups, and Azure role-based access control.

## Azure subscription considerations

When you create an Azure subscription, you make several key choices about the subscription:

- **Who is responsible for paying for the subscription?** The party associated with the email address that you provide when you create a subscription by default is the subscription's account administrator. The party associated with this email address is responsible for paying for all costs that are incurred by the subscription's resources.
- **Which Azure offer am I interested in?** Each subscription is associated with a specific [Azure offer](https://azure.microsoft.com/support/legal/offer-details). You can choose the Azure offer that best meets your needs. For example, if you intend to use a subscription to run nonproduction workloads, you might choose the Pay-As-You-Go Dev/Test offer or the Enterprise Dev/Test offer.

> [!NOTE]
> When you sign up for Azure, you might see the phrase *create an Azure account*. You create an Azure account when you create an Azure subscription and associate the subscription with an email account.

## Azure administrative roles

Azure defines three types of roles for administering subscriptions, identities, and resources:

- Classic subscription administrator roles
- Azure roles
- Azure Active Directory (Azure AD) roles

The account administrator role for an Azure subscription is assigned to the email account that's used to create the Azure subscription. The account administrator is the billing owner of the subscription. The account administrator can [manage subscription administrators](/azure/cost-management-billing/manage/add-change-subscription-administrator) via the Azure portal.

By default, the Service Administrator role for a subscription also is assigned to the email account that's used to create the Azure subscription. The Service Administrator has permissions to the subscription equivalent to the Azure RBAC-based Owner role. The Service Administrator also has full access to the Azure portal. The account administrator can change the Service Administrator to a different email account.

When you create an Azure subscription, you can associate it with an existing Azure AD tenant. Otherwise, a new Azure AD tenant with an associated directory is created. The role of global administrator in the Azure AD directory is assigned to the email account that's used to create the Azure AD subscription.

An email account can be associated with multiple Azure subscriptions. The account administrator can transfer a subscription to another account.

For a detailed description of the roles defined in Azure, see [Classic subscription administrator roles, Azure roles, and Azure AD roles](/azure/role-based-access-control/rbac-and-directory-admin-roles).

## Subscriptions and regions

Every Azure resource is logically associated with only one subscription. When you create a resource, you choose which Azure subscription to deploy that resource to. You can move a resource to another subscription later.

While a subscription isn't tied to a specific Azure region, each Azure resource is deployed to only one region. You can have resources in multiple regions that are associated with the same subscription.

> [!NOTE]
> Most Azure resources are deployed to a specific region. Certain resource types are considered global resources, such as policies that you set by using the Azure Policy services.

## Related resources

The following resources provide detailed information about the concepts discussed in this article:

- [How does Azure work?](../../get-started/what-is-azure.md)
- [Resource access management in Azure](../../govern/resource-consistency/resource-access-management.md)
- [Azure Resource Manager overview](/azure/azure-resource-manager/management/overview)
- [Azure role-based access control (Azure RBAC)](/azure/role-based-access-control/overview)
- [What is Azure Active Directory?](/azure/active-directory/fundamentals/active-directory-whatis)
- [Associate or add an Azure subscription to your Azure Active Directory tenant](/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory)
- [Topologies for Azure AD Connect](/azure/active-directory/hybrid/plan-connect-topologies)
- [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](/microsoft-365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings)

## Next steps

Now that you understand fundamental Azure concepts, learn how to scale with multiple Azure subscriptions.

> [!div class="nextstepaction"]
> [Scale with multiple Azure subscriptions](../azure-best-practices/scale-subscriptions.md)
