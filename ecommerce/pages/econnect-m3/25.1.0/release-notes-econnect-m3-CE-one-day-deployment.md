
# **eConnect 25.1.0**

# Table of contents

- [Environment Details](#environment-details)
- [Standard Features](#standard-features)
- [Prerequisites](#prerequisites)
- [Highlight](#highlight)
- [Enhancements](#enhancements)
- [Compatibility Fixes](#compatibility-fixes)
- [Point of Contact](#point-of-contact)

# Environment Details

| **Software Name**   | **Version** |
| --------------------| ----------- |
| Magento Open Source | 2.4.7      |
| eConnect Community  | 25.1.0      |
| eConnect Base       | 6.4.0       |
| PHP version         | 8.1.6       |
| RabbitMQ            | 3.7.28      |
| Infor M3 (MT)       | 16.1        |
| ION Package         | 3.2.1       |
# Standard Features

All the standard functionalities of core eConnect are supported in v25.1.0, which includes the following:

- Customer Registration
- Customer Addition
- Customer Synchronization
- Product Addition
- Product Synchronization
- Inventory Synchronization
- Customer Price Synchronization
- Order Creation
- Order Synchronization
- Shipment Synchronization
- Invoice History
- Order History
- Initial Load

## Prerequisites

- From Magento v2.4.4 with PHP v8.1, the following setting must be set to 'Yes' to make a successful connection with the Infor ION API.

	![oAuth Access Token](../../../../ecommerce/images/econnect-user-manual-ion-part1/access_token_setting.png)

## Highlight

- eConnect module is now compatible with Magento v2.4.7 and tested on PHP v8.1(but supports PHP v8.2,PHP v8.3 too).

## **Enhancements**

- To set default configurations with one click and make eConnect Portal ready to use in one day.
- The Connection Point, Data Flow, and Work Flow can be imported from the eConnect Portal admin.

## **Compatibility Fixes**

- Addressed the issue to ensure the correct invoice amount is displayed. 

- Fixed the problem of updating salable quantity when it is zero and synchronized with M3.

- Improved visibility for the synchronization of configurable simple items. 

- Resolved the issue with order synchronization across multiple stores on the website. 

- Fixed the problem of partial shipment with zero quantity across multiple order lines.

- Implemented the OIS100MI GetOrderHead transaction to enhance performance.

## Point of Contact

- [prabhu.manoharan3@wipro.com](mailto:prabhu.manoharan3@wipro.com)
- [deepthi.tadikamalla@wipro.com](mailto:deepthi.tadikamalla@wipro.com)
- [ketankumar.zanzarukiya@wipro.com](mailto:ketankumar.zanzarukiya@wipro.com)
- [silambarasan.kj3@wipro.com](mailto:silambarasan.kj3@wipro.com)
- [saurabh.gupta77@wipro.com](mailto:saurabh.gupta77@wipro.com)
- [kalaivani.nagarajan1@wipro.com](mailto:kalaivani.nagarajan1@wipro.com)


