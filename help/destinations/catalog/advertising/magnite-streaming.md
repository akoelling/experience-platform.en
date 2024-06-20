---
title: Magnite Streaming Real-Time Destination connection
description: Magnite is a ... TODO
---

# Magnite Streaming: Real-Time Destination connection

## Overview {#overview}

The Magnite-Adobe Experience Platform integration offers Magnite Streaming clients Real-Time and Daily Destinations to map and export audiences for targeting and activation on the Magnite Streaming platform. The following document provides sample use cases to help you better understand how and when the Real time destination should be used, as well as step-by-step instructions for destination configuration for the Real-time endpoint.

Be advised that in order to properly integrate with the Magnite platform, the Magnite Batch destiniation should be used in addition to the Real-time Destination. Only setting up the Real-time Destiniation will result in a failed integration.  This document only covers the Real-time destination setup. Batch destination can be found [via this link](magnite-batch.md)

>[!IMPORTANT]
>
> TODO
>The destination connector and documentation page are created and maintained by the [!DNL Magnite] team. For any inquiries or update requests, please contact them directly at *Insert link or email address where you can be reached for updates, for example `support@magnite.com`.*

## Use cases {#use-cases}

To help you better understand how and when you should use the [!DNL Magnite Streaming: Real-Time] destination, here is a sample use case that Adobe Experience Platform customers can solve by using this destination.

### Activation and targeting {#activation-and-targeting}

This integration with Magnite allows advertisers to pass advertiser CDP audiences from Adobe Experience Platform to Magnite to create advertiser audiences for advertising targeting. Audiences may be selected within Magnite for positive targeting, as well as negative targeting (suppression).


## Prerequisites {#prerequisites}

To use the Magnite destinations in the Adobe Experience Platform, you must first have a Magnite Streaming account. If you have a [!DNT Magnite Streaming] account, please reach out to your [!DNT Magnite] account manager to be provided credentials to access [!DNT Magnite's] destinations.
If you do not have a [!DNT Magnite Streaming] account, please reach out to something@magnite.com. TODO

## Supported identities {#supported-identities}

*Add information in this section about the identities supported by your destination. We have prefilled the table with some standard values. Delete the values that don't apply to your destination and any values that are not prefilled.*

*YourDestination* supports the activation of identities described in the table below. Learn more about [identities](/help/identity-service/namespaces.md).

|Target Identity|Description|Considerations|
|---|---|---|
|GAID|Google Advertising ID|Select the GAID target identity when your source identity is a GAID namespace.|
|IDFA|Apple ID for Advertisers|Select the IDFA target identity when your source identity is an IDFA namespace.|
|ECID|Experience Cloud ID|A namespace that represents ECID. This namespace can also be referred to by the following aliases: "Adobe Marketing Cloud ID", "Adobe Experience Cloud ID", "Adobe Experience Platform ID". See the following document on [ECID](/help/identity-service/ecid.md) for more information.|
|phone_sha256|Phone numbers hashed with the SHA256 algorithm|Both plain text and SHA256 hashed phone numbers are supported by Adobe Experience Platform. When your source field contains unhashed attributes, check the **[!UICONTROL Apply transformation]** option, to have [!DNL Platform] automatically hash the data on activation.|
|email_lc_sha256|Email addresses hashed with the SHA256 algorithm|Both plain text and SHA256 hashed email addresses are supported by Adobe Experience Platform. When your source field contains unhashed attributes, check the **[!UICONTROL Apply transformation]** option, to have [!DNL Platform] automatically hash the data on activation.|
|extern_id|Custom user IDs|Select this target identity when your source identity is a custom namespace.|

{style="table-layout:auto"}

## Supported Identities

The Magnite Streaming: Real-Time Destination supports the activation of identities described in the table below. Learn more about [identities](/help/identity-service/namespaces.md).

| Target Identity   | Description                                                                                      | Considerations                                                                       |
|-------------------|--------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|
| device_id         | A unique identifier for a device. We accept any kind of device id, regardless of type.           | Device types we support include, but are not limited to: GAID, IDFA, email, etc.     | 

{style="table-layout:auto"}

## Supported audiences {#supported-audiences}

*Add information in this section about the audiences supported by your destination. We have prefilled the table with some standard values. Use the `✓` and `X` characters to mark whether your audience type is supported by this destination.*

This section describes which type of audiences you can export to this destination.

| Audience origin             | Supported | Description | 
|-----------------------------|----------|----------|
| [!DNL Segmentation Service] | ✓ | Audiences generated through the Experience Platform [Segmentation Service](../../../segmentation/home.md).|
| Custom uploads              | ✓ | Audiences [imported](../../../segmentation/ui/overview.md#import-audience) into Experience Platform from CSV files. |

{style="table-layout:auto"}

## Export type and frequency {#export-type-frequency}

*In the table, keep only the lines that correspond to your destination. You should have one line for Export type and one line for Export frequency. Delete the values that don't apply to your destination.*

Refer to the table below for information about the destination export type and frequency.

| Item             | Type                            | Notes                                                                                                                                                                                                                                                                                                                              |
|------------------|---------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Export type      | **[!UICONTROL Segment export]** | You are exporting all members of a segment (audience) with the identifiers (name, phone number, or others) used in the [!DNT Magnite Streaming: Real-Time] destination.                                                                                                                                                            |
| Export frequency | **[!UICONTROL Streaming]**      | Streaming destinations are "always on" API-based connections. As soon as a profile is updated in Experience Platform based on segment evaluation, the connector sends the update downstream to the destination platform. Read more about [streaming destinations](/help/destinations/destination-types.md#streaming-destinations). |

{style="table-layout:auto"}

## Connect to the destination {#connect}

>[!IMPORTANT]
>
>To connect to the destination, you need the **[!UICONTROL View Destinations]** and **[!UICONTROL Manage Destinations]** [access control permission](/help/access-control/home.md#permissions). Read the [access control overview](/help/access-control/ui/overview.md) or contact your product administrator to obtain the required permissions.

To connect to this destination, follow the steps described in the [destination configuration tutorial](../../ui/connect-destination.md). In the configure destination workflow, fill in the fields listed in the two sections below.

### Authenticate to destination {#authenticate}

To authenticate to the destination, fill in the required fields and select **[!UICONTROL Connect to destination]**.

![Add a link here to one or more sample screenshots that show users how to authenticate to your destination](/help/destinations/destination-sdk/docs-framework/assets/authenticate-destination.png)

* **[!UICONTROL Username]**: TODO.
* **[!UICONTROL Password]**: TODO.

### Fill in destination details {#destination-details}

*Add the fields that customers must fill in when configuring a new destination. These fields are destination-specific and depend on your configuration in Destination SDK. Your destination's fields may not be the same as the ones listed below. Please also include a screenshot similar to the sample screenshot shown below.*

To configure details for the destination, fill in the required and optional fields below. An asterisk next to a field in the UI indicates that the field is required.

![Add a link here to one or more sample screenshots that show users how to fill in details for your destination](/help/destinations/destination-sdk/docs-framework/assets/configure-destination-details.png)

*  **[!UICONTROL Name]**: A name by which you will recognize this destination in the future.
*  **[!UICONTROL Description]**: A description that will help you identify this destination in the future.
*  **[!UICONTROL Name of your source partner]**: TODO

### Enable alerts {#enable-alerts}

You can enable alerts to receive notifications on the status of the dataflow to your destination. Select an alert from the list to subscribe to receive notifications on the status of your dataflow. For more information on alerts, see the guide on [subscribing to destinations alerts using the UI](../../ui/alerts.md).

When you are finished providing details for your destination connection, select **[!UICONTROL Next]**.

## Activate segments to this destination {#activate}

>[!IMPORTANT]
>
>* To activate data, you need the **[!UICONTROL View Destinations]**, **[!UICONTROL Activate Destinations]**, **[!UICONTROL View Profiles]**, and **[!UICONTROL View Segments]** [access control permissions](/help/access-control/home.md#permissions). Read the [access control overview](/help/access-control/ui/overview.md) or contact your product administrator to obtain the required permissions.
>* To export *identities*, you need the **[!UICONTROL View Identity Graph]** [access control permission](/help/access-control/home.md#permissions). <br> ![Select identity namespace highlighted in the workflow to activate audiences to destinations.](/help/destinations/assets/overview/export-identities-to-destination.png "Select identity namespace highlighted in the workflow to activate audiences to destinations."){width="100" zoomable="yes"}

*Delete as appropriate - If you are documenting a new streaming destination, keep the first paragraph below. If you are documenting a new file-based destination, keep the second paragraph. If you are documenting a destination that exports datasets, keep the third paragraph.*

Read [Activate profiles and segments to streaming segment export destinations](/help/destinations/ui/activate-segment-streaming-destinations.md) for instructions on activating audience segments to this destination.

Read [Activate audience data to batch profile export destinations](/help/destinations/ui/activate-batch-profile-destinations.md) for instructions on activating audience segments to this destination.

Read [(Beta) Export datasets](/help/destinations/ui/export-datasets.md) for extensive instructions on exporting datasets to this destination.

### Map attributes and identities {#map}

*Add information about supported mappings between source and target fields in the Mapping step of the activation workflow. Your destination might support exporting profile attributes, identity namespaces, or both. Some fields might be mandatory. Target attributes might be predefined or custom. Call out the important caveats and use examples, preferably with screenshots. Two examples of destination pages which you can use as reference are:*

* *[Pega](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/personalization/pega.html?lang=en#mapping-example)*
* *[Medallia](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/voice/medallia-connector.html?lang=en#map)*

## Exported data / Validate data export {#exported-data}

*Add a paragraph about how data is exported to your destination. This would help the customer make sure that they have correctly integrated with your destination. For example, you could provide a sample JSON like the one below. Or, you could provide screenshots and information from your destination's interface that show how customers should expect segments to be populating in the destination platform.*

```
{
  "person": {
    "email": "yourstruly@adobe.com"
  },
  "segmentMembership": {
    "ups": {
      "7841ba61-23c1-4bb3-a495-00d3g5fe1e93": {
        "lastQualificationTime": "2020-05-25T21:24:39Z",
        "status": "exited"
      },
      "59bd2fkd-3c48-4b18-bf56-4f5c5e6967ae": {
        "lastQualificationTime": "2020-05-25T23:37:33Z",
        "status": "existing"
      }
    }
  },
  "identityMap": {
    "ecid": [
      {
        "id": "14575006536349286404619648085736425115"
      },
      {
        "id": "66478888669296734530114754794777368480"
      }
    ],
    "email_lc_sha256": [
      {
        "id": "655332b5fa2aea4498bf7a290cff017cb4"
      },
      {
        "id": "66baf76ef9de8b42df8903f00e0e3dc0b7"
      }
    ]
  }
}

```

## Data usage and governance {#data-usage-governance}

All [!DNL Adobe Experience Platform] destinations are compliant with data usage policies when handling your data. For detailed information on how [!DNL Adobe Experience Platform] enforces data governance, read the [Data Governance overview](/help/data-governance/home.md).

## Additional resources {#additional-resources}

*You can provide further links to your product documentation or any other resources that you consider important for the customer to be successful.*













# Magnite Streaming: Real-Time Destination connection

## Overview

TODO Overview of Magnite

The Magnite-Adobe Experience Platform integration offers Magnite Streaming clients Real-Time and Daily Destinations to map and export audiences for targeting and activation on the Magnite Streaming platform. The following document provides sample use cases to help you better understand how and when the Real time destination should be used, as well as step-by-step instructions for destination configuration for the Real-time endpoint.

Be advised that in order to properly integrate with the Magnite platform, the Magnite Batch destiniation should be used in addition to the Real-time Destination. Only setting up the Real-time Destiniation will result in a failed integration.  This document only covers the Real-time destination setup. Batch destination can be found [via this link](magnite-batch.md)

## Use cases

To help you better understand how and when you should use the Magnite Streaming: Real-Time destination, here are sample use cases that Adobe Experience Platform customers can solve by using this destination.

### Use case #1

TODO: Here's an example:
For mobile messaging platforms:

A home rental and sales platform wants to push mobile notifications to customers’ Android and iOS devices to let them know that there are 100 updated listings in the area where they previously searched for a rental.

### Use case #2

TODO

## Prerequisites

TODO

Add information in this section about anything that customers need to be aware of before starting to set up the destination in the Adobe Experience Platform user interface. This can be about:

- needing to be added to an allow list
- requirements for email hashing
- any account specifics on your side
- how to obtain an API key to connect to your platform

You can link out to your relevant documentation if that would be useful to customers.

## Supported Identities

TODO

| Target Identity | Description             | Considerations |
|----------------|--------------------------|----------------|
| GAID           | Google Advertising ID    | Select the GAID target identity when your source identity is a GAID namespace. |
| IDFA           | Apple ID for Advertisers | Select the IDFA target identity when your source identity is an IDFA namespace. |

## Supported audiences

This section describes which types of audiences you can export to this destination.

| Audience origin      | Supported | Description                                                                                                                                                            |
|----------------------|-----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Segmentation Service | [ ]       | Audience generated through the Experience Platform [Segmentation Service](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/home).           |
| Custom uploads       | [ ]       | Audiences [imported](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/overview#import-audience) into Experience Platform from CSV files. |

## Export type and frequency

TODO : Remove any that don't correspond to our destination

| Item | Type            | Notes                                                                                                                                                                                                                                                                                                                                                                                     |
|------|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Export type | Audience export | You are exporting all members of an audience with the identifiers (name, phone number, or others) used in the YourDestination destination.                                                                                                                                                                                                                                                |
| Export type | Profile-based   | You are exporting all members of an audience, together with the desired schema fields (for example: email address, phone number, last name), as chosen in the select profile attributes screen of the [destination activation workflow](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/activate-batch-profile-destinations#select-attributes).   |
| Export type | Dataset export  | You are exporting raw datasets, which are not grouped or structured by audience interests or qualifications.                                                                                                                                                                                                                                                                              |
| Export frequency | Streaming       | Streaming destinations are “always on” API-based connections. As soon as a profile is updated in Experience Platform based on audience evaluation, the connector sends the update downstream to the destination platform. Read more about [streaming destinations](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/destination-types#streaming-destinations). 
| Export frequency | Batch | Batch destinations export files to downstream platforms in increments of three, six, eight, twelve, or twenty-four hours. Read more about [batch file-based destinations](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/destination-types#file-based).                                                                                                      |


## Connect to the destinaton

To connect to this destination, follow the steps described in the [destination configuration tutorial](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/connect-destination). In the configure destination workflow, fill in the fields listed in the two sections below.

### Authenticate to destination

To authenticate to the destination, fill in the required fields and select Connect to destination.

TODO : Add picture

- Username: TODO
- Password: TODO

### Fill in destination details

To configure details for the destination, fill in the required and optional fields below. An asterisk next to a field in the UI indicates that the field is required.

TODO : Add screenshot

- Name: A name by which you will recognize this destination in the future.
- Description: A description that will help you identify this destination in the future.
- Name of your source partner: TODO

### Enable alerts

You can enable alerts to receive notifications on the status of the dataflow to your destination. Select an alert from the list to subscribe to receive notifications on the status of your dataflow. For more information on alerts, [read the guide on subscribing to destinations alerts using the UI](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/alerts).

When you are finished providing details for your destination connection, select Next.

## Activate audiences to this destination

TODO important info box

Read [Activate profiles and audiences to streaming audience export destinations](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/activate-segment-streaming-destinations) for instructions on activating audiences to this destination.

Read [Activate audience data to batch profile export destinations](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/activate-batch-profile-destinations) for instructions on activating audiences to this destination.

Read [(Beta) Export datasets](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets) for extensive instructions on exporting datasets to this destination.

### Map attributes and identities

TODO: Add information about supported mappings between source and target fields in the Mapping step of the activation workflow. Your destination might support exporting profile attributes, identity namespaces, or both. Some fields might be mandatory. Target attributes might be predefined or custom. Call out the important caveats and use examples, preferably with screenshots. Two examples of destination pages which you can use as reference are:

[Pega](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/personalization/pega#mapping-example)
[Medallia](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/voice/medallia-connector#map)

## Exported data / Validate data export

TODO: Add a paragraph about how data is exported to your destination. This would help the customer make sure that they have correctly integrated with your destination. For example, you could provide a sample JSON like the one below. Or, you could provide screenshots and information from your destination’s interface that show how customers should expect audiences to be populating in the destination platform.

```json
{
  "person": {
    "email": "yourstruly@adobe.com"
  },
  "segmentMembership": {
    "ups": {
      "7841ba61-23c1-4bb3-a495-00d3g5fe1e93": {
        "lastQualificationTime": "2020-05-25T21:24:39Z",
        "status": "exited"
      },
      "59bd2fkd-3c48-4b18-bf56-4f5c5e6967ae": {
        "lastQualificationTime": "2020-05-25T23:37:33Z",
        "status": "realized"
      }
    }
  },
  "identityMap": {
    "ecid": [
      {
        "id": "14575006536349286404619648085736425115"
      },
      {
        "id": "66478888669296734530114754794777368480"
      }
    ],
    "email_lc_sha256": [
      {
        "id": "655332b5fa2aea4498bf7a290cff017cb4"
      },
      {
        "id": "66baf76ef9de8b42df8903f00e0e3dc0b7"
      }
    ]
  }
}
```

## Data usage and governance

All Adobe Experience Platform destinations are compliant with data usage policies when handling your data. For detailed information on how Adobe Experience Platform enforces data governance, read the [Data Governance overview](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/home).

## Additional resources

TODO: You can provide further links to your product documentation or any other resources that you consider important for the customer to be successful.






## Overview

The Magnite-Adobe Experience Platform integration offers Magnite Streaming clients Real-Time and Daily Destinations to map and export audiences for targeting and activation on the Magnite Streaming platform. The following document provides sample use cases to help you better understand how and when the Real time destination should be used, as well as step-by-step instructions for destination configuration for the Real-time endpoint.

Be advised that in order to properly integrate with the Magnite platform, the Magnite Batch destiniation should be used in addition to the Real-time Destination. Only setting up the Real-time Destiniation will result in a failed integration.  This document only covers the Real-time destination setup. Batch destination can be found [via this link](magnite-batch.md)

### **The Magnite-Streaming: Real-Time Destination**

This destination allows Magnite clients to deliver Adobe CDP audiences in real-time to Magnite Streaming for advertising targeting. Post-processing, segments are available for targeting deals created in Magnite. **Please note:**

- The real-time destination system will attempt to send the events with a p95 of \<10 mins after a Profile segmentation/Update event. This means that 95% of the time, profile segment updates will be delivered to Magnite Streaming in under 10 min. The actual receipt and processing of the events within Magnite Streaming depends on the shared data volume.

- Post-ingest, segments are expected to appear in Magnite Streaming within a few minutes and can be applied to a deal. The ad server may take up to an hour to acknowledge targeting updates.

- Audiences shared to Magnite Streaming using the real-time destination will also need to be shared using the Magnite [Streaming Daily destination](magnite-batch.md).

For more information on whether this Real-time destination is right for you, please contact your Magnite Streaming account representative.

## Prerequisites

To use the Magnite destinations in the Adobe Experience Platform, users must first have a Magnite Streaming account. If you have a Magnite Streaming account, please reach out to your account manager to gain access to the Magnite destinations.

## Supported Identities

Magnite Streaming destinations can receive the following identifier sources from the Adobe CDP. Please note all of the following identity sources can map to the Magnite device_id target identifier:

| Identity Source             | Description                                                                                      | Consideration                                                                         |
|:--------------------------- |:------------------------------------------------------------------------------------------------ |:------------------------------------------------------------------------------------- |
| TV Device IDs               | Identifiers for advertising across Over-the-top (OTT)/ Connected TV (CTV) devices and platforms. | These IDs may be referenced as a custom identity source for the user.                 |
| MAIDs                       | Google Advertising ID (GAID) or Apple ID for Advertisers (IDFA).                                 | These IDs are generally captured in the GAID and IDFA source namespaces for the user. |
| Publisher Provided User Ids | This is generally a first-party, cross-device identifier that is included in the ad request.     | This may be referenced as a custom identity source for the user.                      |

## Setting Up The Destinations

Once your destination usage has been approved and Magnite has shared your credentials, please follow the below steps to authenticate, map, and share data.

### **Authenticate to destination**

Locate the Magnite Streaming destinations in the Adobe Experience catalog. Click the additional options button (\...) and then configure the destination.

To authenticate to the destination, fill in the required fields and select Connect to the destination.

![destination configuration auth fields unfilled](../../assets/catalog/advertising/magnite/destination-realtime-config-auth-unfilled.png)

If you have an existing account, you can locate it by changing the Account type option to Existing account.

### **Fill in destination details**

To configure details for the destination, fill in the required and optional fields below. An asterisk next to a field in the UI indicates that the field is required. You can then proceed by clicking Next.

- **Name:** A name by which you will recognize this destination in the
  future.

- **Description:** A description that will help you identify this
  destination in the future.

![destination configuration auth fields filled](../../assets/catalog/advertising/magnite/destination-realtime-config-auth-filled.png)

You can optionally select any relevant data governance policies. Data Export is generally used for the Magnite destinations.

Once done, click the Create button.

![Optional governance policy and enforcement actions](../../assets/catalog/advertising/magnite/destination-realtime-config-grouping-policy.png)

### 

### **Activate audiences to the destination**

Once the Destination has been created, you will be shown the audience activation flow. The following walks through how to activate audiences using the real-time destination.

#### Step 1: Select your new Destination and click Next.

![select the destination to activate audiences too](../../assets/catalog/advertising/magnite/destination-realtime-active-audience-select-destination.png)

#### Step 2: Select any audiences you want to activate, then click Next.

![select the audiences to activate](../../assets/catalog/advertising/magnite/destination-realtime-active-audience-select-audience.png)

#### Step 3: The next step is mapping source identifiers to the Magnite device_id identifier.

![map desired data fields to the device_id field](../../assets/catalog/advertising/magnite/destination-realtime-active-audience-field-mapping.png)

**Real-time Destination Notes**:

- You may have multiple source attributes/namespaces that could represent a Device ID, so map as many as you need.

- A new mapping can be added using the Add new mapping button.

In this example using the real-time destination, we're mapping any rows
that contain a generic deviceId source identifier to the Magnite
device_id target field. When you\'re done, click Next.

![Be sure to set mapping ids to all activated audiences, or set NONE if no mapping id is present](../../assets/catalog/advertising/magnite/destination-realtime-active-audience-mappingid.png)

You must now configure a Start date (mandatory), End date (optional),
and a Mapping ID for each audience.

**Mapping ID Notes:**

- The Mapping ID field should be used when an audience has a pre-existing Segment ID previously known to Magnite.

- To add a Mapping ID to an audience, click each audience row individually and enter data in the right-hand column (see image above). If you do not want to add a Mapping ID, please enter NONE into the Mapping ID field. This is because the Mapping ID is a mandatory field within the Adobe system, despite technically being optional for a customer.

Once these configurations are applied, click Next.

#### Step 4: Confirm the Destination activation Configuration.

![](../../assets/catalog/advertising/magnite/destination-realtime-active-audience-review.png)

In this step, confirm the Destination activation configuration and click
Finish.

## Exported data / Validate data export

Once your audiences have been uploaded, you may validate your audiences
have been created and uploaded correctly using the following steps:

- The real-time destination system will attempt to send the events with a p95 of \<10 mins after a Profile segmentation/Update event. This means that 95% of the time, profile segment updates will be delivered to Magnite Streaming in under 10 min. The actual receipt and processing of the events within Magnite Streaming depends on the shared data volume.

- Post-ingest, segments are expected to appear in Magnite Streaming within a few minutes and can be applied to a deal. You can confirm this by looking up the segment ID that was shared during the activation steps in the Adobe Experience Platform.

  - **Note:** Audiences shared with Magnite Streaming using the  real-time destination will also need to be shared using the Magnite Streaming Daily destination. When configured correctly, segment names in the Magnite Streaming UI are updated to reflect those used in the Adobe Experience Platform post-daily update.

Finally, if a Batch destination has not been configured for your integration, set it up now via [this document](magnite-batch.md)
