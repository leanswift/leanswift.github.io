# **21.4.0**

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


# **21.1.0**

## **Enhancements**

 - Re-engineered Order, Shipment, Invoice, and Tracking to improve performance

## **Bug Fixes**

- Wrong status update when websites are configured with different company has been fixed

- Cron jobs for API are added at Crontab.xml in Commerce version

- Scope of Shipping method configuration changed to Website-only scope.

- MITBAL and MITFAC values are getting updated in Magento during Product Sync

- Validation done to handle empty Customer price in backend 

- Indexer now runs for product id that receives stock update instead of full re-indexing of catalog


# **20.3.1-p1**

## **Bug Fixes**

- Variation ID has been handled to check and update empty variation id when show bods(currently sync bods) are triggered

# **20.3.1**

## **Enhancements**

- IMS architecure updated to support econnect 20.3.0 architecture where BODs from ION are now configured to be sent to a REST API in Magento, which in turn sends them to RabbitMQ for storage and processing by eConnect. In the previous versions, ION sends BODs to RabbitMQ directly.

## **Bug Fixes**

- Order total was not saved in order history table

- Duplicate customers getting created via IMS

- Product detail page goes to 404 due to MWH

- Emtpy table validation during Customer price call

- Shipment bod update when status is 'Shipped'

- Errors on running "setup:di:compile"

- Issue in Max records set during API call for econnect

- Issue while saving product in admin

# **20.3.0-p2-CE**

## **Bug Fixes**

- Product sync will work even if there are multiple "Item Id" nodes in the BOD

- Categories will get created successfully even if "Item Hierarchy" is given as part of catgeory source

- Instructions under 'M3 Category Source' are updated with the proper details


# **20.3.0-p1-CE**

## **Bug Fixes**

- Product detail page works properly without going 404


# **20.3.0**

## **New Features**

- Separate amqp-leanswift connection to connect RabbitMQ
- Additional-Entity API programs are more flexible and configurable to support Product, Customer, and Order.
- Adding support to import the ION authentication file in the authentication configuration section.
- Adding support to view all the eConnect custom logs from the admin log viewer.
- API maxReturnedRecords option is now configurable.
- New configuration section to provide the RabbitMQ credentials for amqp-leanswift connection.

## **Enhancements**

- Implement mixins for Javascript to prevent interference with other modules
- Implement declarative schema for the database tables.
- Now Price is more flexible to support both ODSAPR and MMSAPR
- Adding the customer default address from CustomerPartyMaster BOD


## **Bug Fixes**

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
- Error handling in checkout page when shipping methods are  enabled.
