---
title: Work with Customer Insights - Data APIs
description: Use APIs and understand limitations.
ms.date: 07/06/2023
ms.reviewer: wimohabb
ms.topic: how-to
author: m-hartmann
ms.author: wimohabb
ms.custom: baptemplate
searchScope: 
  - ci-system-api-usage
  - customerInsights
---

# Work with Customer Insights - Data APIs

[!INCLUDE [consolidated-sku](./includes/consolidated-sku.md)]

[!INCLUDE [api-deprecate](./includes/api-deprecate.md)]

Dynamics 365 Customer Insights - Data provides APIs to build your own applications based on your data in Customer Insights. Details of these APIs are listed on the [API reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). They include additional information about operations, parameters, and responses.

## Get started trying the APIs

An admin must enable API access to your data. Once access is enabled, any user can use API with the subscription key.

1. [Sign in](https://home.ci.ai.dynamics.com) to Customer Insights - Data or [sign up for a trial of Customer Insights](https://aka.ms/tryci).

1. Go to **Settings** > **Permissions** and select the **APIs** tab.

1. If API access to the environment has not been set up, select **Enable**.

   Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests. To regenerate the keys, select the **Regenerate primary** or **Regenerate secondary** on the **APIs** tab.

1. Select [**Explore our APIs**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) to try out the APIs.

1. Search for and select an API operation and select **Try it**.

   :::image type="content" source="media/try-api.png" alt-text="How to test the APIs.":::

1. In the side pane, set the value in the **Authorization** dropdown menu to **implicit**. The `Authorization` header gets added with a bearer token. Your subscription key is automatically populated.
  
1. Optionally, add all necessary query parameters.

1. Scroll to the bottom of the side pane and select **Send**.

   The HTTP response displays at the bottom of the pane.

## Create a new app registration in the Azure portal

Create a new [app registration](/graph/auth-register-app-v2) to use the APIs in an Azure application using delegated permissions.

1. Complete the [Getting started section](#get-started-trying-the-apis).

1. Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.

1. Search for and then select **App registrations**.

1. Select **New registration**, provide an application name and choose the account type.

   Optionally, add a redirect URL. http://localhost is sufficient for developing an application on your local computer.

1. Select **Register**.

1. On your new App registration, go to **API permissions**.

1. Select **Add a permission** and select **Dynamics 365 AI for Customer Insights** in the side pane.

1. For **Permission type**, select **Delegated permissions** and then select the **user_impersonation** permission.

1. Select **Add permissions**.

1. Select **Grant admin consent for...** to complete the app registration.

1. To access the API without a user signing in, go to [Set server-to-server application permissions](#set-server-to-server-application-permissions).

You can use the Application/Client ID for this app registration with the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to obtain a bearer token to send with your request to the API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

For information on using the APIs in our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).

### Set server-to-server application permissions

Create an app registration that doesn't need user interaction and can be run on a server.

1. On your App registration in the Azure portal, go to **API permissions**.

1. Select **Add a permission**.

1. Select the **APIs my organization uses** tab and choose **Dynamics 365 AI for Customer Insights** from the list.

1. For **Permission type**, select **Application permissions** and then select the **api.access** permission.

1. Select **Add permissions**.

1. Go back to **API permissions** for your app registration.

1. Select **Grant admin consent for...** to complete the app registration.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Add the name of the app registration as a user in Customer Insights - Data.

   1. Open Customer Insights - Data, go to **Settings** > **Permissions** and select **Add users**.

   1. Search for the name of your app registration, select it from the search results, and select **Save**.

## Sample queries

For a short list of OData sample queries to work with the APIs, see [OData query examples](odata-examples.md).

## Customer Insights client libraries

Get started using the client libraries available for the Customer Insights - Data APIs. All library source code and sample applications can be found on a [GitHub repo](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).

### C# NuGet

Use the C# client libraries from NuGet.org. Currently, the package targets the netstandard2.0 and netcoreapp2.0 frameworks. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).

#### Add the C# client library to a C# project

1. In Visual Studio, open the **NuGet Package Manager** for your project.

1. Search for **Microsoft.Dynamics.CustomerInsights.Api**.

1. Select **Install** to add the package to the project.

   Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### Use the C# client library

1. Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).

1. After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the **DefaultRequestHeaders "Authorization"** set to **Bearer "access token"** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-apis).

   Reset the **Authorization** header when appropriate. For example, when the token expired.

1. Pass this `HttpClient` into the construction of the `CustomerInsights` client.

   <!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`. If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example, `GetAllInstancesWithHttpMessagesAsync`.

1. The response is likely `object` type because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`). To check the return type, use the objects in the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.

   If more information on the request is needed, use the **http message methods** to access the raw response object.

### NodeJS package

Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### Python package

Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
