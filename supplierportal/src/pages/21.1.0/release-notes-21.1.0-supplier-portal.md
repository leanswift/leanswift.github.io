![Supplier portal banner](../../../../images/banner-supplier-portal.jpg)

# **Supplier Portal**

# **21.1.0**

## **Release Notes**

**Table of Contents**

- [Overview](#overview)

- [Environment Details](#environment-details)

- [Standard Features](#standard-features)

- [Validated Versions](#validated-versions)

- [Point of Contact](#point-of-contact)

## **Overview**

**LeanSwift Supplier Portal** for Infor M3 CloudSuite is a supplier self-service portal that enables efficient online communication with vendors. It is seamlessly integrated with Infor M3 Cloudsuite via ION. Supplier Portal helps automate the entire purchase-to-pay process for the customer.

## **Environment Details**

|  **Software Name**  |  **Version**  |
| --- | --- |
| Magento Open Source | 2.4.1 |
| eConnect Base Module Version | 5.0.0 |
| IDM Module version | 3.2.2 |
| ION Package | 2.0.0|
| RabbitMQ | 3.8.3 |
| ION Desk | 12.0.0 |
| Infor M3 | 16.1 |
| Infor ION Grid | 2020-10.135425.10 |



## **Standard Features**

This version includes all the standard features from 20.2.0 as mentioned below:

**Account**
  - Registration and Login
  - View Supplier Information
  - User Date Format Setting

**Purchase Orders**

Confirm / Confirm All
- This feature is to Confirm a PO on line level or header level (status 35).

Advise / Advise All
- This Add-on is used to Advise PO on line level or header level (status 40 ) and should be used along with Supplier Portal.

Notify / Notify All
- This Add-on is used to Notify PO on line level or header level (status 45 ) and should be used along with Supplier Portal.

Notify by Delivery Number
- This Add-on is used to Notify PO lines of different purchase orders based on the delivery number and should be used along with Supplier Portal.

Confirm, Advise and Notify multiple PO
- This feature is to confirm or advise or notify multiple purchase orders. Separate buttons are available at global level in My Purchase Orders page.

Bell Notification
- This feature is to notify both supplier admin and users about the new updates on purchase order lines or forecast.

Email Notifications
- Email is sent to supplier admin and the sub-accounts (based on user permissions) when a new PO / forecast is added or an existing purchase order / forecast is modified.

Refresh button on ‘My Purchase Orders’ page
- Download button on ‘My Purchase Orders’ to download purchase order information

Upload documents into IDM against Purchase Orders
  - This is available ONLY if additional functionality for IDM integration is included as part of license

View Purchase Orders ,Search/Filter/Sort on Purchase Orders and Download Purchase Orders Information


**IDM upload for suppliers**

  Upload or fetch supplier specific documents into IDM on the ‘My Documents’ section in the ‘My Accounts’ page.

**My Deliveries**

  This Add-on is used to display deliveries and corresponding invoice matching status for all the lines that are goods received.

**User Management**

  This Add-on is to manage sub-accounts (users) and their roles and permissions.

**My Invoices**

  This Add-on is used to display all the invoices associated with the supplier’s PO and also other details such as outstanding amount, due date and open/paid.

**User Tracking**
  
  This Add-on is to configure the allowed number of Registrations (supplier admin ) and allowed sub-account users per supplier admin.
  
**Purchase Proposals/Forecasts**
  - View Purchase Forecasts
  - Search/Filter/Sort on Purchase Forecasts
  
**Performance Metrics**
  - View Quality metrics based on rejected quantity
  - View Delivery Performance metrics
  - View Purchase Price Variance metrics

## **New Features**

With 21.1.0, there is a major technical architectural change in the solution. BODs from ION are now configured to be sent to a REST API in Magento, which in turn sends them to RabbitMQ for storage and processing by Supplier Portal. In the previous versions, ION sends BODs to RabbitMQ directly.

**LeanSwift AMQP Connection**
- Separate AMQP connection to handle standard M3 BODs necessary for Supplier Portal in RabbitMQ.
- Provided the RabbitMQ section in the Magento admin to configure the credentials.

## **Limitation and Known Issues**

The limitations and known issues from supplier portal 20.2.0 is applicable in this version as well. To view the release notes of 20.2.0, click [here](../20.2.0/release-notes-20.2.0-supplier-portal.md).

## **Validated Versions**

 Chrome 88.0.4324.190


## **Point of Contact**

[prabhu.mano@leanswift.com](mailto:prabhu.mano@leanswift.com)

[niranjan.b@leanswift.com](mailto:niranjan.b@leanswift.com)

[srinidhi.narayanan@leanswift.com](mailto:srinidhi.narayanan@leanswift.com)

[nrithya.rajagopalan@leanswift.com](mailto:nrithya.rajagopalan@leanswift.com)
