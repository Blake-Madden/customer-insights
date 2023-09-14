---
title: Uninstall Dynamics 365 Customer Insights
description: How to remove Dynamics 365 Customer Insights.
ms.date: 09/13/2023
ms.topic: article
author: alfergus
ms.author: alfergus
search.audienceType: 
  - admin
  - customizer
  - enduser
---

# Uninstall Dynamics 365 Customer Insights

[!INCLUDE[consolidated-sku-rtm-only](./includes/consolidated-sku-rtm-only.md)]

You can remove Customer Insights from any Dynamics 365 instance where it's installed. After removing it, you'll end up with a Customer Insights license that you can use on another Dynamics 365 instance, if desired.

> [!IMPORTANT]
> The uninstall process detailed below *does not* remove all Customer Insights - Journeys-related solutions from your instance. To remove all Customer Insights - Journeys-related solutions, you must follow the process below then manually delete the solutions in the order listed in [Solution uninstall order for removing Customer Insights - Journeys](#uninstall.md#solution-uninstall-order-for-removing-customer-insights---journeys).

## Uninstall Customer Insights - Journeys services

The Customer Insights uninstall process handles most of the uninstall process. The uninstall process:

- Removes all services for Customer Insights - Journeys, event management, and Dynamics 365 Connector for LinkedIn Lead Gen Forms
- Removes the marketing insights service and its data
- Turns off user syncing from Microsoft 365 for Customer Insights - Journeys users
- Frees your Customer Insights license for use with another Dynamics 365 instance

> [!NOTE]
> If you want to release your Customer Insights entitlement to use on a different instance, you do not need to uninstall any of the Customer Insights solutions.

To run the uninstall process:

1. If you have sample data installed, remove it. More information: [Add or remove sample data](/power-platform/admin/add-remove-sample-data).

1. [Run the Customer Insights - Journeys setup wizard](re-run-setup.md) for the instance where you want to uninstall the Customer Insights - Journeys application. Make sure the correct instance is listed.

1. From the **Other actions** panel, choose **Uninstall Customer Insights - Journeys from this org**.

1. Follow the on-screen instructions to confirm and complete the uninstall.

<a name="reset-portal"></a>

## Reset any Power Apps portals connected to the uninstalled Customer Insights - Journeys app (outbound marketing only)

If the outbound environment in the Customer Insights - Journeys instance that you are uninstalling was connected to a Power Apps portal (for example to run marketing pages or the events website), then you need to reset the portal to release its license. After the reset, the portal still shows as configured in the Power Platform admin center, but you'll be able to select it when you run the Customer Insights - Journeys setup wizard to set up a new, copied, or restored instance.

Portals are optional, so you might not have one connected to your Customer Insights - Journeys instance. More information: [Integrate Customer Insights - Journeys with a CMS system or Power Apps portal](portal-optional.md)

To reset a portal:

1. Follow the instructions provided in [Reset a portal](/powerapps/maker/portals/admin/reset-portal).
1. Portal reset leaves behind its website bindings, which may prevent you from reusing your portal name. Therefore, you should always delete all website bindings that are related to the portals used by your uninstalled Customer Insights - Journeys instance. More information: [Create and manage website bindings](/powerapps/maker/portals/configure/website-bindings)

## Solution uninstall order for removing Customer Insights - Journeys

> [!NOTE]
> If you want to release your Customer Insights entitlement to use on a different instance, you **do not** need to uninstall any of the Customer Insights - Journeys solutions.

To delete Dynamics 365 from an instance, first open the Customer Insights - Journeys setup wizard and run the uninstall command. The uninstall command releases your Dynamics 365 license and disconnects the Customer Insights - Journeys services. If you'd also like to remove all of the related solutions from your instance, you must manually delete them in the order listed below. (Some of the items listed here may not be present on your instance, so just skip any missing items.) For complete instructions, see [Uninstall Customer Insights - Journeys](uninstall.md).

Solutions labelled "Used outside of Customer Insights - Journeys" are used by other Dynamics 365 apps such as Dynamics 365 Sales, Customer Service Hub, Intelligent Order Management Features, and others. It's **not safe to uninstall the shared solutions** as it can break related workloads, so it's recommended to skip those.

> [!NOTE]
> In the following tables, names of solutions used outside of Customer Insights - Journeys are struck through, indicating that you should not delete them because they affect other apps.

Moments-based marketing:

| Solution name | Used outside of Customer Insights - Journeys |
| -------------- | ------------------------------ |
| DynamicsMKT_AnchorSolution | No |
| ~~DynamicsMKT_CxpAnalytics~~ | Yes |
| DynamicsMKT_Configuration | No |
| DynamicsMKT_OcIntegration | No |
| msdyn_InsightsAnalyticsMKTConfiguration | No |
| msdyn_DataInsightsAndAnalyticsForMKT | No |
| ~~msdyn_DataInsightsAndAnalytics~~ | Yes |
| DynamicsMKT_Sitemap_RTMDefault | No |
| DynamicsMKT_StandaloneSitemap | No |
| DynamicsMKT_Sitemap | No |
| MicrosoftDynamics_EventManagementAppUser | No |
| DynamicsMKT_LandingPageFormsAppUser | No |
| DynamicsMKT_TeamsEventsIntegrationAppUser | No |
| DynamicsMKT_MarketingAppUserRealtimeLink | No |
| DynamicsMKT_CxpGoalUser | No |
| ~~DynamicsMKT_CxpExperimentationUser~~ | Yes |
| DynamicsMKT_CxpAnalyticsConfiguration | No |
| DynamicsMKT_CxpAIConfiguration | No |
| DynamicsMKT_AttachCIApplicationUser | No |
| DynamicsMKT_CxpApplicationUser | No |
| DynamicsMKT_ChannelsAppUser | No |
| DynamicsMKT_ConsentAppUser | No |
| ~~DynamicsMKT_CxpPersonalizationUIAppUser~~ | Yes |
| DynamicsMKT_CIConnection | No |
| DynamicsMKT_BURoles | No |
| DynamicsMKT_Roles | No |
| DynamicsMKT_CxpGdpr | No |
| DynamicsMKT_ConsentFormsLink | No |
| DynamicsMKT_EventManagementRealtimeLinkData | No |
| DynamicsMKT_EventManagementRealtimeLink | No |
| DynamicsMKT_Forms | No |
| DynamicsMKT_FrequencyCapping | No |
| DynamicsMKT_BrandProfiles | No |
| DynamicsMKT_TeamsVEventsApp | No |
| DynamicsMKT_TeamsVEvents | No |
| DynamicsMKT_Fragments | No |
| DynamicsMKT_DomainValidation | No |
| DynamicsMKT_CustomerJourneyManagementRealtimeLink | No |
| DynamicsMKT_FormManagementRealtimeLink | No |
| DynamicsMKT_CxpConditionalContent | No |
| DynamicsMKT_QuotaSolution | No |
| ~~DynamicsMKT_MetadataStore~~ | Yes |
| DynamicsMKT_CxpGetStartedEasyModeBaseSolution | No |
| DynamicsMKT_CxpGetStartedExperience | No |
| DynamicsMKT_PushNotification | No |
| DynamicsMKT_SharedPushChannelsUser | No |
| DynamicsMKT_SharedPushChannels | No |
| DynamicsMKT_EmailChannel | No |
| DynamicsMKT_CxpEmailEditor | No |
| DynamicsMKT_CxpEmailEditorCanvas | No |
| ~~MicrosoftDynamics_EmailEditorModule~~ | Yes |
| ~~MicrosoftDynamics_EmailEditorCanvasModule~~ | Yes |
| ~~DynamicsMKT_EmailEditorCanvasShared~~ | Yes |
| DynamicsMKT_EmailEditorShared | No |
| DynamicsMKT_OrchestrationActions | No |
| DynamicsMKT_ImageGenerator | No |
| DynamicsMKT_Tracking | No |
| ~~DynamicsMKT_PersonalizationUI~~ | Yes |
| DynamicsMKT_CxpCmsIntegration | No |
| DynamicsMKT_SmsChannel | No |
| DynamicsMKT_CustomerVoiceIntegration | No |
| ~~DynamicsMKT_SharedSmsChannelsUser~~ | Yes |
| ~~DynamicsMKT_SharedSmsChannels~~ | Yes |
| ~~DynamicsMKT_ChannelDefinitions~~ | Yes |
| ~~DynamicsMKT_SharedChannelExtensions~~ | Yes |
| ~~msdyn_D365ChannelDefinitions~~ | Yes |
| ~~msdyn_D365ChannelDefinitionsUser~~ | Yes |
| ~~msdyn_OmnichannelSharedSMS~~ | Yes |
| ~~msdyn_OmnichannelSharedCommunicationBase~~ | Yes |
| ~~msdyn_OmnichannelSharedBase~~ | Yes |
| ~~msdyn_OCModernAdminBase~~ | Yes |
| DynamicsMKT_CxpGoal | No |
| ~~DynamicsMKT_CxpExperimentation~~ | Yes |
| DynamicsMKT_CxpAI | No |
| DynamicsMKT_OrchestrationAnalyticsRealtimeLink | No |
| DynamicsMKT_OrchestrationAnalytics | No |
| DynamicsMKT_OrchestrationTriggers | No |
| DynamicsMKT_CxpOrchestrationUI | No |
| DynamicsMKT_CxpOrchestrationUIControls | No |
| DynamicsMKT_ConsentAttachCI | No |
| DynamicsMKT_Consent | No |
| DynamicsMKT_AssetControlsSolution | No |
| DynamicsMKT_CxpFormControls | No |
| DynamicsMKT_OrchestrationEngineAttachCI | No |
| DynamicsMKT_OrchestrationEngineEvents | No |
| DynamicsMKT_OrchestrationEngine | No |
| DynamicsMKT_CxpSegmentationUI | No |
| ~~DynamicsMKT_FeatureConfiguration~~ | Yes |
| MicrosoftDynamics_HealthChecker | No |
| ~~DynamicsMKT_BaseSolution~~ | Yes |
| DynamicsMKT_Segmentation | No |
| ~~DynamicsMKT_AnalyticsUx~~ | Yes |

Segment-based marketing:

| Solution name | Used outside of Customer Insights - Journeys |
| -------------- | ------------------------------ |
| MicrosoftDynamics_SegmentationDataLakeTIP | No |
| MicrosoftDynamics_SegmentationDataLake | No |
| LeadGenAppUser | No |
| MicrosoftDynamics_MarketingAppUser | No |
| MicrosoftDynamics_MarketingAppBURoles | No |
| MicrosoftDynamics_MarketingAppRoles | No |
| MicrosoftDynamics_SubscriptionList | No |
| MicrosoftDynamics_OrgCleanup | No |
| MicrosoftDynamics_PackageUpgrade | No |
| MicrosoftDynamics_PersonalizedPages | No |
| MicrosoftDynamics_MarketableContactSupport | No |
| MicrosoftDynamics_MarketingFormsProLink | No |
| MicrosoftDynamics_MktEmailEditor | No |
| MicrosoftDynamics_EvtMgmtPortalsLink | No |
| MicrosoftDynamics_MktContentSuggestions | No |
| MicrosoftDynamics_EmailEditorModule | No |
| MicrosoftDynamics_EmailEditorCanvasModule | No |
| MicrosoftDynamics_QuickSend | No |
| MicrosoftDynamics_ABTesting | No |
| MicrosoftDynamics_GwennolFeatureConfiguration | No |
| MicrosoftDynamics_GwennolSpamScore | No |
| MicrosoftDynamics_GwennolOESTPrediction | No |
| MicrosoftDynamics_GwennolOptimalEmailSendingTime | No |
| MicrosoftDynamics_MktIntegration | No |
| MicrosoftDynamics_SocialPosting | No |
| MicrosoftDynamics_LinkedInMatchedAudiences | No |
| MicrosoftDynamics_MktLeadGenLink | No |
| MicrosoftDynamics_MktConsentManagement | No |
| MicrosoftDynamics_FeatureConfiguration | No |
| MicrosoftDynamics_MktQuotaInfo | No |
| MicrosoftDynamics_MktPageTemplates | No |
| MicrosoftDynamics_MktEvtMgmtLink | No |
| MicrosoftDynamics_MktOrchestrationCompatModule | No |
| MicrosoftDynamics_MarketingOrchestrationModule | No |
| LinkedInLeadGenIntegration | No |
| MicrosoftDynamics_MktLeadManagement | No |
| MicrosoftDynamics_MktEmailTemplates | No |
| MicrosoftDynamics_Marketing | No |
| MicrosoftDynamics_EventManagement | No |
| DynamicsMKT_EmailEditorCanvasShared | No |
| DynamicsMKT_EmailEditorShared | No |
| ~~MicrosoftDynamics_ContentEditor~~ | Yes |
| MicrosoftDynamics_Orchestration | No |
| MicrosoftDynamics_ReusableBlocks | No |
| DynamicsMKT_SharedMarketingSettings | No |
| MicrosoftDynamics_DigitalAssets | No |
| ~~DynamicsMKT_SharedMarketingControls~~ | Yes |
| MicrosoftDynamics_Calendar | No |
| MicrosoftDynamics_DsfSdkAppUser | No |
| MicrosoftDynamics_ManagedIdentityTIP | No |
| MicrosoftDynamics_ManagedIdentity | No |
| MicrosoftDynamics_PreImport | No |

If you see any other "anchor" solutions that start with "MicrosoftDynamics_", you can delete those too. They are likely left over from an earlier version that you upgraded. You can remove these in any order after you've uninstalled the other solutions.

Customer Insights - Journeys application dependencies are installed alongside the Customer Insights - Journeys application. The following dependencies can only be uninstalled if they are not used by other solutions:

1. msdyn_DataInsightsAndAnalytics: Enables analytics capabilities for Dynamics 365 applications like Customer Service, Field Service, and Universal Resource Scheduling.
1. DynamicsMKT_Segmentation: Standard entity of segment representation and segment metadata.

[!INCLUDE[footer-include](./includes/footer-banner.md)]
