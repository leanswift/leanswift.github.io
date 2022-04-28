# **eConnect 22.2.0**

# Table of contents

- [**Environment Details**](#environment-details)
- [**Standard Features**](#standard-features)
- [**Enhancements**](#enhancements)
- [**Bug Fixes**](#bug-fixes)
- [**Point of Contact**](#point-of-contact)


# **Environment Details**

| **Software Name** | **Version** |
| --- | --- |
| Magento version | 2.4.3 |
| eConnect Base | 6.1.1 |
| PHP version | 7.4.28 |
| RabbitMQ | 3.7.28 |
| Infor M3 (MT) | 16.1 |
| ION Package | 3.2.0 |

# **Standard Features**

All the standard functionalities of core eConnect are supported in v22.2.0, which includes the following:

- Product Addition
- Product Synchronization
- Customer Price Synchronization
- Inventory Synchronization
- Customer Registration
- Customer Addition
- Customer Synchronization
- Order Creation
- Order Synchronization
- Shipment Synchronization
- Invoice History
- Order History
- Initial Load


# **New Features/Enhancements**
 
- Based on the M3 release-Oct 2021, changes are done for bringing the Invoice BOD from M3

	- Earlier OINVOH table was used to bring the Customer Order Invoices from M3 but now it has changed to CINHED.
	
	- ION Package v3.2.0 must be used for this eConnect version


# **Bug Fixes**

- Resolved the error in Order Creation flow when the shipping address does not exist for the order

- Invoice creation and update will work even when same company_division combo is configured for all the websites

- Creation of Partial shipment and Invoice will work as expected

- Reapeated status history shown in admin sales_order_view is now resolved

- Resolved the issue during order creation when the length of the city in Address exceeds the maximum character of 20

- Xpath changes are done for the SalesRep specific fields - RESP and SMCD

- Error thrown during product sync from the admin grid is now resolved

- API's configured in the 'Additional Entity Attribute Mapping' will work only when their status is Enabled


# **Point of Contact**

- [nanthini.muralidaran@leanswift.com](mailto:nanthini.muralidaran@leanswift.com)
- [prabhu.mano@leanswift.com](mailto:prabhu.mano@leanswift.com)
- [deepthi.tadikamalla@leanswift.com](mailto:deepthi.tadikamalla@leanswift.com)
- [narayanan.gurusamy@leanswift.com](mailto:narayanan.gurusamy@leanswift.com)




