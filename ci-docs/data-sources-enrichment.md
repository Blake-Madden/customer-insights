---
title: "Enrichment for data sources (preview)"
description: "Enrich data sources before going through the data unification process."
ms.date: 03/20/2023
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
ms.custom: bap-template
---

# Enrichment for data sources (preview)

Use data from sources like Microsoft and other partners to enrich your customer data before data unification. Data source enrichments help produce higher data completeness and quality that can help achieve better results once you unify your data. For example, using a normalized and standardized format for addresses increases the quality of the match results. For a list of supported enrichments, see [supported data source enrichment options](#supported-data-source-enrichments).

## Enrich a data source

You must have Contributor or Administrator [permissions](permissions.md) to create or edit enrichments.  

1. Go to **Data** > **Unify**. Select the entity you want to enrich and select one attribute as a [primary key](map-entities.md#select-primary-key-and-semantic-type-for-attributes) for the entity.

1. Go to **Data** > **Data sources**.

1. Select the vertical ellipsis (&vellip;) next to the data source you want to enrich and select **Enrich**.

   :::image type="content" source="media/data_sources_enrich.png" alt-text="Data sources page with Enrich highlighted":::

   The **Discover** tab displays the [supported data source enrichment options](#supported-data-source-enrichments).

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Data sources enrichment page.":::

1. Select **Enrich my data** to configure a data source enrichment. The output entity name is automatically populated.

## Supported data source enrichments

The following enrichments are currently available for data sources. Review the detailed steps for the enrichment to learn how to configure it.

- [Enhanced addresses](enrichment-enhanced-addresses.md)
- [Enhanced company data](enrichment-enhanced-company-data.md)
- [Identity data from LiveRamp](enrichment-liveramp.md)

## Manage existing data source enrichments

Go to **Data** > **Enrichment**. On the **My enrichments** tab, view the configured enrichments, their status, number of enriched customers, and the last time the data was refreshed. You can sort the list of enrichments by any column or use the search box to find the enrichment you want to manage.

Select the enrichment to see the available options. You can also select the vertical ellipsis (&vellip;) on a list item to see the options.

You can view, edit, run, or delete a data source enrichment. For more information, see [Manage existing enrichments](enrichment-hub.md#manage-existing-enrichments).
