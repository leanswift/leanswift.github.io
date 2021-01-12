![](RackMultipart20201224-4-dzt8sl_html_390ba5139005650c.png)

# **eConnect 20.3.0**

# Table of contents

- [**Environment Details**](#environment-details)
- [**Standard Features**](#standard-features)
- [**New Features/Enhancements**](#new-featuresenhancements)
    - [**LeanSwift AMQP Connection**](#leanswift-amqp-connection)
    - [**Enterprise Connector Removal**](#enterprise-connector-removal)
    - [**Additional Entity Attribute Mapping**](#additional-entity-attribute-mapping)
    - [**Authentication File Upload Option**](#authentication-file-upload-option)
    - [**Update on item price**](#update-on-item-price)
- [**Highlights**](#highlights)
- [**Bug Fixes**](#bug-fixes)
- [**Note**](#note)
- [**Point of Contact**](#point-of-contact)


# **Environment Details**

| _ **Software Name** _ | _ **Version** _ |
| --- | --- |
| Magento version | 2.4.1 |
| PHP version | 7.4.12 |
| RabbitMQ | 3.8.3 |
| Infor M3 (MT) | 16.1 |

# **Standard Features**

All the standard functionalities of core eConnect are supported in v20.3.0, which includes the following:

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

### **LeanSwift AMQP Connection**

New AMQP connection to handle the eConnect related BODs in RabbitMQ.
 Provided the option in the Backend for the same to give the RabbitMQ credentials.

### **Enterprise Connector Removal**

No more Enterprise Connector. All the eConnect BODs from ION will now contact eConnect REST API directly instead of sending to rabbitmq.

### **Additional Entity Attribute Mapping**

Custom BODs created for Product, Customer and Order are replaced with API calls now. Provided the backend setting to configure APIs based on the entity type. This allows to trigger the APIs when the corresponding BOD is received.

### **Authentication File Upload Option**

Uploading the .ionapi file will automatically populate the authentication details

### **Update on item price**

Provided option to choose which field can be Item Price - MMSAPR / ODSAPR

Note : The base price that updates for an item based on odsapr setting will work on website scope by picking the price list and currency based on website scope but customer specific price will update based on latest price bod 

# **Highlights**

- _maxReturnedRecords_ option in the API request is now configurable

- Table creation and Attribute creation will be done as per Magento standard

- Usage of mixins in javascript instead of _map_

# **Bug Fixes**

- Customer Default Address from the CustomerPartyMaster BOD are now added to Magento

- Support for overriding standard Xpath from the configuration has been provided.

- Dispatching 'catalog_product_import_bunch_save_after' event for product and 'ls_catalog_product_stock_bunch_save_after' event for stock resolves synchronize problem on third-    party integration.

- Bug fixes are made to fetch only the active shipping and payment methods in econnect configuration.

- Performance improvement done for item manual sync. Added additional check before performing the shipment creation.

- Factory pattern class is used to load the object for required entities, collection factory is used whererver possible inorder to rectify memory issue in order creation via  cron.

- Sort, filter and issues in CSV file is fixed in 'My Orders' page. Fixes are also applied to properly update status, shipment and payment information on 'My Orders' page.

- Fixes done (check if Location ID is empty in Receivable transaction BOD) to update invoice amount in 'My Invoices' page.

- Removed LS extension specific attributes such as Variation ID from checkout page.

- New Configuration 'Item Price' is added in admin. Based on selection item base price will update by calling the API.

- Fixes for Undefined offset error during customer registration (when supplier portal was also installed & used in the same instance ).

- When 'M3 AttributeSet Source' is invalid , product is now mapped to 'Default/Fallback AttributeSet' configured.

- Error handling in checkout page when shipping methods are enabled.

# **Note** 

 - This version is supported only in MT.
 
 - LSItemMasterDetails , LSSalesOrderDetails and LSCustomerDetails are no more supported from 2.3.0 onwards.

# **Point of Contact**

- [prabhu.mano@leanswift.com](mailto:prabhu.mano@leanswift.com)
- [niranjan.b@leanswift.com](mailto:prabhu.mano@leanswift.com)
- [deepthi.tadikamalla@leanswift.com](mailto:prabhu.mano@leanswift.com)
- [srinidhi.narayanan@leanswift.com](mailto:prabhu.mano@leanswift.com)
- [nrithya.rajagopalan@leanswift.com](mailto:prabhu.mano@leanswift.com)


