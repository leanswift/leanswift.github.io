# **eConnect 20.3.1-p1**

# Table of contents

- [**Environment Details**](#environment-details)
- [**Standard Features**](#standard-features)
- [**Bug Fixes**](#bug-fixes)
- [**Point of Contact**](#point-of-contact)


# **Environment Details**

| **Software Name** | **Version** |
| --- | --- |
| Magento version | 2.4.2 |
| PHP version | 7.4.16 |
| RabbitMQ | 3.8.3 |
| Infor M3 (MT) | 16.1 |

# **Standard Features**

All the standard functionalities of core eConnect are supported in v20.3.1-p1, which includes the following:

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


# **Bug Fixes**
- Variation ID has been handled to check and update empty variation id when show bods(currently sync bods) are triggered
- Resolved the case where SalesOrder BOD is getting skipped due to Shipment BODs variation Id got saved to the SalesOrder table

_Note: This version is tested on Magento 2.4.2 and this patch release includes only the above fix. Only basic testing has been covered._


# **Point of Contact**

- [prabhu.mano@leanswift.com](mailto:prabhu.mano@leanswift.com)
- [niranjan.b@leanswift.com](mailto:niranjan.b@leanswift.com)
- [deepthi.tadikamalla@leanswift.com](mailto:deepthi.tadikamalla@leanswift.com)
- [srinidhi.narayanan@leanswift.com](mailto:prabhu.mano@leanswift.com)
- [nrithya.rajagopalan@leanswift.com](mailto:prabhu.mano@leanswift.com)


