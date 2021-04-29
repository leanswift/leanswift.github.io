# **eConnect 21.1.0**

# Table of contents

- [**Environment Details**](#environment-details)
- [**Standard Features**](#standard-features)
- [**Enhancements**](#enhancements)
- [**Bug Fixes**](#bug-fixes)
- [**Point of Contact**](#point-of-contact)


# **Environment Details**

| **Software Name** | **Version** |
| --- | --- |
| Magento version | 2.4.2 |
| PHP version | 7.4.16 |
| RabbitMQ | 3.8.3 |
| Infor M3 (MT) | 16.1 |
| ION package | |
| eConnect Base | |

# **Standard Features**

All the standard functionalities of core eConnect are supported in v21.1.0, which includes the following:

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


 - Re-engineered Order, Shipment, Invoice, and Tracking to improve performance


# **Bug Fixes**


- Wrong status update when websites are configured with different company has been fixed

- Cron jobs for API are added at Crontab.xml in Commerce version

- Scope of Shipping method configuration changed to Website-only scope.

- MITBAL and MITFAC values are getting updated in Magento during Product Sync

- Validation done to handle empty Customer price in backend 

- Indexer now runs for product id that receives stock update instead of full re-indexing of catalog

# **Point of Contact**

- [prabhu.mano@leanswift.com](mailto:prabhu.mano@leanswift.com)
- [niranjan.b@leanswift.com](mailto:niranjan.b@leanswift.com)
- [deepthi.tadikamalla@leanswift.com](mailto:deepthi.tadikamalla@leanswift.com)
- [srinidhi.narayanan@leanswift.com](mailto:srinidhi.narayanan@leanswift.com)
- [nrithya.rajagopalan@leanswift.com](mailto:nrithya.rajagopalan@leanswift.com)



