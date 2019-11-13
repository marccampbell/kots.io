---
date: 2019-10-23
linktitle: "Customers And Licenses"
title: Customers And Licenses
weight: 20030
---

Each end customer who needs to install the application will need a separate license file for their installation. This license file identifies the customer and application during the installation and update processes. A customer license is created in the Customers section of the [vendor portal](https://vendor.replicated.com). The values and properties of that customer and license and be managed on the Vendor portal, including custom license fields, by selecting an individual customer.

To create or manage custom license fields you can do so in the License Fields section of the vendor portal or via the Vendor License API. License values are used by Replicated to enable/disable various functionality.


### Name (Required)
The name of the customer to whom this license is assigned.

### Channel (Required)
When creating a license, it will need to be assigned to at least one release channel. The Stable channel is intended to be used for production installations. Unstable and Beta channels are intended for internal testing. 

When a license is assigned to multiple channels, the customer will be able to select the channel at install time and later change the release channel in the management console. For airgapped installs, the channel can be selected at download time only.

### Expiration Date
License have expiration dates that can optionally be used to control when the application no longer will be able to receive updates or be supported. On expiration, the end customer's environment will no longer be able to pull images and manifests, and will need to have the license updated to continue using it.

### Airgap Download Enabled
By default, licenses will be set to disable airgap installations. By enabling this feature, the actual .YAML file will have license metadata embedded in it and must be re-downloaded.

### License Type (Required)
It is important to identify the type of license that is being created, development, trial, paid or community. Development licenses are designed to be used internally by the development team for testing and integration. Trial licenses should be provided to customers who are on 2-4 week trials of your software. Paid licenses identify the end customer as a paying customer (for which additional information can be provided). Community licenses are not supported by Replicated, but can be a convenient way to distribute community-supported versions that can be upgraded to paid versions over time.

### Custom License Fields
Custom license fields can be set for all licenses. This is useful if specific customer information might change from customer to customer. These fields can be read from both the template functions as well as from the Integration API. Examples of custom license fields are “seats” to limit the number of active users or “hostname” in order to specify the domain that the application can be run on.

### Archiving Licenses
When a license is archived in the vendor portal, it will be hidden in the default license search and become read-only. Archival does not affect the utility of license files downloaded before the change. If you wish for them to expire, set an expiration date and policy before archiving. This is a convenience feature for how licenses are displayed in the vendor portal.

