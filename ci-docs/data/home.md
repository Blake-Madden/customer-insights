---
title: Explore the user interface
description: "Start exploring the app on the Home page."
ms.date: 09/01/2023
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
---

# Explore the user interface

[!INCLUDE [consolidated-sku](./includes/consolidated-sku.md)]

You can access [Dynamics 365 Customer Insights - Data](https://home.ci.ai.dynamics.com/) on the following URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).

The **Home** page guides you through the configuration process for key features and provides an overview of segments, measures, and enrichment data. The default home page shows how to get insights in minutes by adding data in a single file.

:::image type="content" source="media/home-step-by-step.png" alt-text="Screenshot of the default Home screen showing get insights in minutes.":::

If you have multiple data sources, select **Step-by-step guide**.

:::image type="content" source="media/home-page.png" alt-text="Screenshot of the Home screen showing step-by-step cards.":::

## Left side pane

Use the left pane to navigate between different areas of Customer Insights - Data.

## Application header

The **Environment** picker shows the environment you work in and lets you create or manage environments as an administrator.

The smiley face icon is the **Feedback** control. Select it to tell us about your experience. We're actively listening to your feedback and thank you in advance for letting us know what you like and how we can improve.

The **Settings** control, represented by a gear icon, lets you gather session details and configure global settings for your Microsoft 365 profile.

**Help** options, visualized with a question mark icon, provide contextual help links and other helpful resources.

Your profile picture opens the **Account manager** for your Microsoft 365 profile. Select **My account** to manage your personal settings.

## Getting started with Customer Insights

The cards that display on the **Home** page depend on the selection: **Get insights in mins** or **Step-by-step guide**.

### Get insights in minutes

> [!NOTE]
> [!INCLUDE [single-file-us-only](includes/single-file-us-only.md)]

This section contains a card to upload a single file and receive automatic insights and then a card to add connections to activate those insights. Select **Add data** to [upload your file](data-sources-single.md). Once your data is uploaded and insights such as segments and measures generated, select **Add connections** to connect your favorite services. For example, export the data to Facebook to use in social media.

### Step-by-step guide

This section contains cards that help you walk through the process of setting up your environment.

1. The **Add data** card assists you with your data import. Customer Insights - Data supports [several options to bring in data about your customers](data-sources.md). Select **Add a data sources** to get started.
1. Once the initial data import successfully completes, you can use the **Unify data** card to harmonize the data and [create unified customer profiles](data-unification.md) from disparate sources. 
1. With unified customer profiles in place, it's time to review the **Analyze data** options and get additional insights. Give it a try to create [business measures](measures.md) to track KPIs, [define segments](segments.md) to reach specific audiences, or [configure predictions](predictions.md) with the help of AI.
1. Now that your customer data is imported, unified, and neatly structured, you use our [various export destinations](export-destinations.md) to take action on the data. Select **Add connections** to connect your favorite services. For example, export the data to Dynamics 365 Customer Insights - Journeys to create marketing campaigns and build customer journeys.

## Your customer insights section

- **Segments** shows groups of customers based on demographic, behavioral, or transactional attributes that you've defined. [Creating segments](segments.md) helps you to group your customer base and better target your business activities.

- **Business measures** shows tiles with [key performance indicators (KPIs)](measures.md) that you've defined. For example, average likelihood of a customer to churn or the average online spend per customer.

- **Enrichments** lists results of the enrichment runs that completed recently. [Enrichments](enrichment-hub.md) add information about your customer base. For example, by understanding the interests and brands that they have affinity for.


[!INCLUDE [footer-include](includes/footer-banner.md)]
