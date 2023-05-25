# **eConnect 23.2.0**

# Table of contents

- [**Environment Details**](#environment-details)
- [**Standard Features**](#standard-features)
- [**Prerequisites**](#prerequisites)
- [**Highlight**](#highlight)
- [**Compatibility Fixes**](#compatibility-fixes)
- [**Other Fixes**](#other-fixes)
- [**ION Package Update**](#ion-package-update)
- [**Point of Contact**](#point-of-contact)

# **Environment Details**

| **Software Name**   | **Version** |
| --------------------| ----------- |
| Magento Community   | 2.4.6       |
| eConnect Community  | 23.2.0      |
| eConnect Base       | 6.3.0       |
| PHP version         | 8.1.6       |
| RabbitMQ            | 3.7.28      |
| Infor M3 (MT)       | 16.1        |
| ION Package         | 3.2.1       |

# **Standard Features**

All the standard functionalities of core eConnect are supported in v23.2.0, which includes the following:

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

- From Magento v2.4.4 with PHP v8.1, the following setting must be set to 'Yes' in order to make successful connection with the Infor ION API.

	![oAuth Access Token](../../../../ecommerce/images/econnect-user-manual-ion-part1/access_token_setting.png)

## **Highlight**

- eConnect module is now compatible with Magento v2.4.6 and tested on PHP v8.1(but supports PHP v8.2 too)

- Zend framework dependency was completely replaced with Laminas

## **Compatibility Fixes**

- Resolved the unsupported operand type error during Order Creation cron

## **Other Fixes**

- Resolved the error 'Undefined array key STAT' thrown during Order Creation

## **ION Package Update**

- Updated ION Package version to 3.2.1 with the below fix
	- Show Shipment BOD is now working and getting triggered as expected after making changes in the Event Analytics Rules.

## **Point of Contact**

- [prabhu.manoharan3@leanswift.com](mailto:prabhu.manoharan3@wipro.com)
- [deepthi.tadikamalla@leanswift.com](mailto:deepthi.tadikamalla@wipro.com)
- [narayanan.gurusamy@leanswift.com](mailto:narayanan.gurusamy@wipro.com)
- [challa.anjana@wipro.com](mailto:challa.anjana@wipro.com)
- [kalaivani.nagarajan1@wipro.com](mailto:kalaivani.nagarajan1@wipro.com)

