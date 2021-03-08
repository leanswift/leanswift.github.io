# **eConnect 20.3.1**

# Table of contents

- [**Environment Details**](#environment-details)
- [**Standard Features**](#standard-features)
- [**Enhancements**](#enhancements)
- [**Bug Fixes**](#bug-fixes)
- [**Point of Contact**](#point-of-contact)


# **Environment Details**

| **Software Name** | **Version** |
| --- | --- |
| Magento version | 2.4.1 |
| PHP version | 7.4.12 |
| RabbitMQ | 3.8.3 |
| Infor M3 (MT) | 16.1 |

# **Standard Features**

All the standard functionalities of core eConnect are supported in v20.3.1, which includes the following:

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

# **Enhancements**

- IMS architecure updated to support econnect 20.3.0 architecture where BODs from ION are now configured to be sent to a REST API in Magento, which in turn sends them to RabbitMQ for storage and processing by eConnect. In the previous versions, ION sends BODs to RabbitMQ directly.

 _Note: This version is tested only on M3-Multi-tenant._

# **Bug Fixes**

- Order total was not saved in order history table
- Duplicate customers getting created via IMS
- Product detail page goes to 404 due to MWH
- Emtpy table validation during Customer price call 
- Shipment bod update when status is 'Shipped'
- Errors on running "setup:di:compile"
- Issue in Max records set during API call for econnect
- Issue while saving product in admin


# **Point of Contact**

- [prabhu.mano@leanswift.com](mailto:prabhu.mano@leanswift.com)
- [niranjan.b@leanswift.com](mailto:prabhu.mano@leanswift.com)
- [deepthi.tadikamalla@leanswift.com](mailto:prabhu.mano@leanswift.com)
- [srinidhi.narayanan@leanswift.com](mailto:prabhu.mano@leanswift.com)
- [nrithya.rajagopalan@leanswift.com](mailto:prabhu.mano@leanswift.com)


