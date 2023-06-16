---
title: Set up an Azure Private Link
description: Learn how to set up an Azure Private Link to connect your Data Lake Storage.
ms.date: 03/20/2023
ms.topic: how-to
author: AndreaAczel
ms.author: anaczel
ms.reviewer: mhart
ms.custom: bap-template
---

# Set up an Azure Private Link

[Azure Private Link](/azure/private-link/private-link-overview) lets Customer Insights connect to your Azure Data Lake Storage account over a private endpoint in your virtual network. For data in a storage account, which isn't exposed to the public internet, Private Link enables the connection to that restricted network.

> [!IMPORTANT]
> Minimum role requirement to set up a Private Link connection:
>
> - Customer Insights: Administrator
> - Azure built-in role: [Storage Account Contributor](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Permissions for custom Azure role: [Microsoft.Storage/storageAccounts/read and Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

In Customers Insights you can create private links in the following ways:

   - When creating a new Customer Insights environment for which you would like to [Use your own Azure Data Lake Storage account](own-data-lake-storage.md) that is protected by your virtual network.
   - When creating a [data source](connect-common-data-model.md) for which the data is stored in your protected account.
   - Directly from the **Settings** > **Permissions** > **Private Links** page in Customer Insights.

Regardless of the method you use to create the Private Link, it shows under the **Settings** > **Permissions** > **Private Links** tab in Customer Insights.

## Set up a Private Link when creating a Customer Insights environment

When creating a [Customer Insights environment](create-environment.md) that connects to your virtual network protected storage:

1. Select **Enable Azure Private Link**.

   :::image type="content" source="media/Private-Endpoint-Creation.png" alt-text="Private endpoint creation.":::

1. Select **Create Private Link** to initiate the creation process. 

1. [Approve the Private Link](#approve-your-private-link-in-the-azure-portal) in the Azure portal.

1. Once all links are approved, select **Validate Private Link**. Upon successful validation, you can continue configuring your new environment.

## Set up a Private Link when creating a data source

When creating an [Azure Data Lake Storage data source](connect-common-data-model.md) that needs to connect to a storage protected by a virtual network, follow the same steps as described under [Setting up a private link when creating a Customer Insights environment](#set-up-a-private-link-when-creating-a-customer-insights-environment).

## Set up a Private Link directly from the Private Links page in Customer Insights

1. In Customer Insights, go to **Settings** > **Permissions** and select the **Private Links** tab.

1. Select **Add Private Link**.

   The **Add Private Link** pane lists storage accounts in your tenant that you can see.

1. Select the subscription, resource group, and storage account.

1. Review the [data privacy and compliance](connections.md#data-privacy-and-compliance) and select **I agree**.

1. Select **Save**.

## Approve your Private Link in the Azure portal

After configuring the Private Link between Customer Insights and your virtual network protected storage, four Private Links show on the **Private Links** tab in Customer Insights with a status of **Pending**.

1. In the Azure portal, go to your Data Lake Storage account, and select **Networking** > **Private endpoints connections** to see the four new Private Links.

1. Select **Yes** to approve them.

   > [!TIP]
   > For easy identification, consider adding a description when approving the Private Links.

    :::image type="content" source="media/Private-Endpoint-Approval.png" alt-text="Description for the private endpoint approval step.":::

1. In Customer Insights, go to **Settings** > **Permissions** and select the **Private Links** tab. The Private Links in Customer Insights now show the status **Approved**. 

1. Continue to add your [data sources](connect-common-data-model.md) that are linked to your protected storage.

## Delete an Azure Private link

1. In Customer Insights, go to **Settings** > **Permissions** and select the **Private Links** tab.

1. Select the storage account name for which you would like to delete the Private Links.

1. Select **Delete**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
