<img alt ="Supplier Portal Banner" src="../../images/pwa/SupplierPortal_Banner.png">

# Supplier Portal

# 24.2.0

# Release Notes

# Table of contents

- [Overview](#overview)
- [Environment Details](#environment-details)
- [Standard Features](#standard-features)
- [Supported Devices](#supported-devices)
- [Technical Features](#technical-features)
- [Enhancements](#enhancements)
- [Prerequisites](#prerequisites)
- [Limitations](#limitations)
- [Known Issues](#known-issues)
- [Recommendation](#recommendation)
- [Validated Versions](#validated-versions)
- [Point of Contact](#point-of-contact)

# Overview

**LeanSwift Supplier Portal** for Infor M3 CloudSuite is a supplier self-service portal that enables efficient online communication with vendors. It is seamlessly integrated with Infor M3 Cloudsuite via ION. Supplier Portal helps automate the entire purchase-to-pay process for the customer.

# Environment Details

| **Software Name** | **Version** |
| --- | --- |
| Magento version | 2.4.6 |
| eConnect Base Module Version | 6.4.0 |
| IDM Module Version | 4.3.0 |
| ION Package Version | 24.2.0 |
| PHP version | 8.1.0 |
| RabbitMQ | 3.7.28 |
| ION Desk | 2023.11.02 |
| Infor M3 | Cloudsuite |
| Supplier Portal Module | 24.2.0 |
| Advise and Notify | 24.2.0 |
| Supplier Invoices | 24.2.0 |
| Supplier Deliveries | 24.2.0 |
| Supplier User Tracking | 24.2.0 |
| User Management | 24.2.0 |
| Supplier Item Management | 24.2.0 |
| SupplierPortalGraphql | 24.2.0 |
| IDMGraphql | 24.2.0 |
| SupplierPortalInvoiceGraphql | 24.2.0 |
| PWA Build pack  | 11.4.1 | 
| Node JS |  16.19.0 | 
| Yarn | 1.22.19 | 

# Standard Features

This version includes all the standard features as mentioned below:

**Account**

- Registration and Login
- View Supplier Information
- User Date Format Setting

**Purchase Orders**

View Purchase Orders, Search/Filter/Sort on Purchase Orders and Download Purchase Orders Information

**Confirm / Confirm All**

This feature is to Confirm a PO at line level or header level (status 35).

**Advise / Advise All**

This Add-on is used to Advise PO online level or header level (status 40) and should be used along with Supplier Portal.

**Notify / Notify All**

This Add-on is used to Notify PO on line level or header level (status 45) and should be used along with Supplier Portal.

**Notify by Delivery Number**

This Add-on is used to Notify PO lines of different purchase orders based on the delivery number and should be used along with Supplier Portal.

**Confirm, Advise and Notify multiple PO**

This feature is to confirm or advise or notify multiple purchase orders. Separate buttons are available at global level in My Purchase Orders page.

**Refresh** button on 'My Purchase Orders' page

**Download** button on 'My Purchase Orders' to download purchase order information.

**Upload documents into IDM against Purchase Orders**

- This is available ONLY if additional functionality for IDM integration is included as part of license.

**Bell Notification**

This feature is to notify both supplier admin and users about the new updates on purchase order lines or forecast.

**Email Notifications**

Email is sent to supplier admin and the sub-accounts (based on user permissions) when a new PO / forecast is added, or an existing purchase order / forecast is modified.

**IDM upload for suppliers**

Upload or fetch supplier specific documents into IDM on the 'My Documents' section in the 'My Accounts' page.

**My Deliveries**

This Add-on is used to display deliveries and corresponding invoice matching status for all the lines that are goods received.

**User Management**

This Add-on is to manage sub-accounts (users) and their roles and permissions.

**My Invoices**

This Add-on is used to display all the invoices associated with the supplier's PO and other details such as outstanding amount, due date and open/paid.

**Supplier Item Management**

This will be an Add-on to Supplier Portal. With this Supplier can create a new supplier item OR M3 Item /Update item/Connect supplier item to existing M3 item. M3 Buyer decides to approve or reject the above requests from the supplier based on the real time data provided by him.

**User Tracking**

This Add-on is to configure the allowed number of Registrations (supplier admin) and allowed sub-account users per supplier admin.

**Purchase Proposals/Forecasts**

- View Purchase Forecasts
- Search/Filter/Sort on Purchase Forecasts

**Performance Metrics**

- View Quality metrics based on rejected quantity.
- View Delivery Performance metrics.
- View Purchase Price Variance metrics.

# Supported Devices 

- **Desktop**- All Browsers 
- **Android version** - 11,12,13 
- **IOS** – Test On Demand 

# Technical Features

- Magento PWA using REACT JS 
- Graphql 

# Enhancements

- To set default configurations by one click and make Supplier Portal ready to use by one day.
- The Connection Point, Data Flow, Work Flow can be imported from the Supplier Portal admin.
- Theme Configurations are enabled in PWA for better user experience.

# Prerequisites

IDM add-on should be configured for My Purchase orders data to be displayed in supplier portal.

# Limitations

- If multiple (more than 5) conditions are added or removed in a non-sequential manner, Filters may not fetch appropriate results. 
- Upload/Download Documents work only when IDM is Enabled 
- Order type ADN (Automatic Delivery note Generation) flag value saved in Magento only once during registration (assuming Order type configurations will not be changed in m3).  
- Default out of the box configuration that comes with installation cannot be deleted. 
- The buyer should unassign the task, after adding notes to supplier onboarding task. 
- Magento Admin user cannot send the invite to Supplier for onboarding. 
- IDM document notification from Infor is not triggered due to Wipro environment issue. But this works fine in LeanSwift environment.

# Known Issues

- When SHAC is kept as 2, and Automatic delivery note generation is enabled, advise and notify is done for a delivery note number PPS360 / TransNotifyHead is called. when the SHAC is disabled for the same supplier, and I advise a line with same delivery note number (line is not added in PPS360) but since the delivery note number is available in PPS360 during notify the PPS360 / TransNotifyHead is called and the PPS001MI/NotifyDelNot is not called. This causes the line to remain in processing state.
- When one line of PO is advised with a delivery note number (where Automatic delivery note generation is enabled) and Advise all / Advise multiple po's is tried for same PO with delivery note number, error message 'Shipment advice is not allowed - the order is already advised with delivery note' is displayed.

# Recommendation

- It is recommended to use eConnect and Supplier portal in separate instances.

# Validated Versions

- Chrome Version 125.0.6422.142
- Android OS 11,12,13 

# Point of Contact

- [silambarasan.kj3@wipro.com](mailto:silambarasan.kj3@wipro.com)
- [vaithiyanathan.paramasivam@wipro.com](mailto:vaithiyanathan.paramasivam@wipro.com)
- [ketankumar.zanzarukiya@wipro.com](mailto:ketankumar.zanzarukiya@wipro.com)
- [prabhu.manoharan3@wipro.com](mailto:prabhu.manoharan3@wipro.com)
- [challa.anjana@wipro.com](mailto:challa.anjana@wipro.com)
- [narayanan.gurusamy@wipro.com](mailto:narayanan.gurusamy@wipro.com)
