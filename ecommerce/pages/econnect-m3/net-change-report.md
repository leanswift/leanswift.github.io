
# **21.`.0**

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
