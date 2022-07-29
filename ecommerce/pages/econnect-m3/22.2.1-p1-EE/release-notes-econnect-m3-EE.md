# **eConnect 22.2.1-p1**

# Table of contents

- [**Environment Details**](#environment-details)
- [**Standard Features**](#standard-features)
- [**Prerequisites**](#prerequisites)
- [**Highlight**](#highlight)
- [**Enhancements**](#enhancements)
- [**Compatibility Fixes**](#compatibility-fixes)
- [**Bug Fixes**](#bug-fixes)
- [**Point of Contact**](#point-of-contact)


# **Environment Details**

| **Software Name** | **Version** |
| --- | --- |
| Magento version | 2.4.4 |
| eConnect Base | 6.2.1 |
| PHP version | 8.1.6 |
| RabbitMQ | 3.7.28 |
| Infor M3 (MT) | 16.1 |
| ION Package | 3.2.0 |

# **Standard Features**

All the standard functionalities of core eConnect are supported in v22.2.1-p1, which includes the following:

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

# Prerequisites

- From Magento v2.4.4 with PHP v8.1, the following setting must be set to 'Yes' in order to make successful connection with the Infor ION API.

	![oAuth Access Token](../../../../ecommerce/images/econnect-user-manual-ion-part1/access_token_setting.png)

# **Highlight**

- Product, Price, Category, AttributeSet, Customer Price, Shipment & Invoice creation(Order Module) will now get updated even when the SKU and ERP Item Number is different for a product

- eConnect will support the Open Shipments from M3 i.e. when the same shipment number is created for two different customer orders

# **Compatibility Fixes**

- Resolved the PHP warning(trying to access array on boolean) while trying to update customer price

# **Bug Fixes**

- Customer Price will get displayed in the frontend based on the currency value specified for that store in the backend

- Errors shown in the phtml files(Order History, Order View, Invoice History) related to PHP Tag are now resolved

# **Point of Contact**

- [nanthini.muralidaran@leanswift.com](mailto:nanthini.muralidaran@leanswift.com)
- [prabhu.mano@leanswift.com](mailto:prabhu.mano@leanswift.com)
- [deepthi.tadikamalla@leanswift.com](mailto:deepthi.tadikamalla@leanswift.com)
- [narayanan.gurusamy@leanswift.com](mailto:narayanan.gurusamy@leanswift.com)
