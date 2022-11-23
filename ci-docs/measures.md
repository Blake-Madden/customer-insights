---
title: "Measures overview"
description: "Learn how measures help analyze and reflect the performance of your business."
ms.date: 11/28/2022

ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope: 
  - ci-measures
  - ci-measure-builder
  - ci-measure-template
  - ci-enrichment-details
  - customerInsights
---

# Measures overview

Measures help you to better understand customer behaviors and business performance. They look at relevant values from [unified profiles](data-unification.md). For example, a business wants to see the *total spend per customer* to understand an individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business. Some [service limits](/dynamics365/customer-insights/service-limits) apply.

Create measures to plan business activities by querying customer data and extract insights. For example, create a measure of *total spend per customer* and *total return per customer* to help identify a group of customers with high spend yet high return. Then, [create a segment](segments.md) based on these measures to drive next best actions.

## Create a measure

Choose how to create a measure based on your target audience.

# [Individual consumers (B-to-C)](#tab/b2c)

- From scratch with measure builder: [Build your own](measure-builder.md).
- From commonly used measures: [Use predefined templates](measure-templates.md).

# [Business accounts (B-to-B)](#tab/b2b)

From scratch with measure builder: [Build your own](measure-builder.md).

---

## Manage existing measures

Go to the **Measures** page to view the measures you created, their status, measure type, and the last time the data was refreshed. You can sort the list of measures by any column or use the search box to find the measure you want to manage.

Select next to a measure to view available actions. Select the measure name to preview the output and download a CSV file.

:::image type="content" source="media/measures-actions.png" alt-text="Actions to manage single measures."lightbox="media/measures-actions.png":::

- **Edit** the measure to change its properties.
- **Refresh** the measure manually to include the latest data.
- **Rename** the measure.
- **Activate** or **Deactivate** the measure. Inactive measures won't get refreshed during a [scheduled refresh](measures-schedule.md) and have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.
- **Tag** to [manage tags](work-with-tags-columns.md#manage-tags) for the measure.
- **Delete** the measure.
- [**Schedule**](measures-schedule.md) to customize the schedule for the measure.
- **Columns** to [customize the columns](work-with-tags-columns.md#customize-columns) that display.
- **Filter** to [filter on tags](work-with-tags-columns.md#filter-on-tags).
- **Search name** to search by measure name.

[!INCLUDE [footer-include](includes/footer-banner.md)]
