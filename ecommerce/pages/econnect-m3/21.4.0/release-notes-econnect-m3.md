# **eConnect 21.4.0**

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
| PHP version | 7.4.26 |
| RabbitMQ | 3.7.28 |
| Infor M3 (MT) | 16.1 |
| ION Package | 3.1.0 |

# **Standard Features**

All the standard functionalities of core eConnect are supported in v21.4.0, which includes the following:

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


# **Highlight**

- Customer price related cache issue on Product Detail Page is now resolved


# **Enhancements**

- Delivery address chosen by the customers can be sent to M3 just by sending the Address Type and the Address ID(only if valid ID exists) via 'addBatchHead' transaction
 
- 'Additional Entity Attribute Mapping' feature comes with the support of website scope


# **eConnect-base Compatibility**

- Changes are done in the Order Creation flow to make it compatible with the eConnect-base 6.1.1.


# **Bug Fixes**

- Resolved the issue of 'Duplication of Order creation in M3'

- Resolved the Performance issue for the Order caused by unoptimized Query

- Order creation/sync issue for the B2B website(except Main Website) is now resolved

- Validation added for OIS100MI: Confirm transaction. This will not be called if there is no ORNO

- Resolved the 'Incorrect shipping address fetched during addBatchAddress transaction' issue

- Order Comments passed in the 'addBatchText' transaction are now getting reflected in M3

- Order Status update issue when there are multiple stores is now resolved

- Resolved the 'Order Comments appeared twice in the Order comments Histoy page' issue

- Order API CRON Job is getting scheduled and running successfully after renamed the JobCode 'leanswift_econnect_order_api'

- Added validations for the frontend Order History page to avoid the undefined index error

- Removed the validation of Region ID during Customer Address sync

- 'Store ID not found' issues during Customer and Product Sync is now resolved

- Customer Price Issues during Order Creation from the Backend are now resolved

- Website ID level implementation is now handled for all the requests made to M3

- Refresh Token will get updated if anything got changed to the existing Authentication Details

- Resolved the 'Undefined Variable' issue during Customer Sync

- Fixed the hyperlink shown after initiated any initial load in the Backend

- Exception thrown on opening the Backend Configuration page due to the Sorting attribute in XML is now resolved

# **Point of Contact**

- [prabhu.mano@leanswift.com](mailto:prabhu.mano@leanswift.com)
- [nanthini.muralidaran@leanswift.com](mailto:nanthini.muralidaran@leanswift.com)
- [deepthi.tadikamalla@leanswift.com](mailto:deepthi.tadikamalla@leanswift.com)




