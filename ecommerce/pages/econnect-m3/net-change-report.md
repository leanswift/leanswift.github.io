![eConnect banner](../../../../images/banner-econnect-m3.jpg)

# eCommerce - Net Change Report 

# Table of contents

- [24.1.0](#2410)
  - [Highlight](#highlight)
  - [Enhancements](#enhancements)
  - [Compatibility Fixes](#compatibility-fixes)
  - [ION Package Update](#ion-package-update)
- [23.2.0](#2320)
  - [Highlight](#highlight)
  - [Compatibility Fixes](#compatibility-fixes)
  - [Highlight](#highlight)
- [Other Fixes](#other-fixes)
  - [ION Package Update](#ion-package-update)
- [22.2.1-p1-EE](#2221-p1-ee)
  - [Highlight](#highlight)
  - [Compatibility Fixes](#compatibility-fixes)
  - [Bug Fixes](#bug-fixes)
- [22.2.1](#2221)
  - [Highlight](#highlight)
  - [Enhancements](#enhancements)
  - [Compatibility Fixes](#compatibility-fixes)
  - [Bug Fixes](#bug-fixes)
- [22.2.0-p2](#2220-p2)
  - [Enhancements](#enhancements)
- [22.2.0-p1](#2220-p1)
  - [Enhancements](#enhancements)
  - [Bug Fixes](#bug-fixes)
- [22.2.0](#2220)
  - [Enhancements](#enhancements)
  - [eConnect Compatibility for Commerce](#econnect-compatibility-for-commerce)
  - [Bug Fixes](#bug-fixes)
- [21.4.0](#2140)
  - [Highlight](#highlight)
  - [New Features/Enhancements](#new-featuresenhancements)
  - [eConnect-base Compatibility](#econnect-base-compatibility)
  - [Bug Fixes](#bug-fixes)
- [21.1.0](#2110)
  - [Enhancements](#enhancements)
  - [Bug Fixes](#bug-fixes)
- [20.3.1-p1](#2031-p1)
  - [Bug Fixes](#bug-fixes)
- [20.3.1](#2031)
  - [Enhancements](#enhancements)
  - [Bug Fixes](#bug-fixes)
- [20.3.0-p2-CE](#2030-p2-ce)
  - [Bug Fixes](#bug-fixes)
- [20.3.0-p1-CE](#2030-p1-ce)
  - [Bug Fixes](#bug-fixes)
- [20.3.0](#2030)
  - [New Features](#new-features)
  - [Enhancements](#enhancements)
  - [Bug Fixes](#bug-fixes)
# **24.1.0**

## **Highlight**

- eConnect module is now compatible with Magento v2.4.6 and tested on PHP v8.1(but supports PHP v8.2 too).

## **Enhancements**

- Added features to skip account creation without an email address to enhance functionality.
- Added temporary and final order numbers to provide additional information on the admin order view page.

## Compatibility Fixes

- Resolved the unsupported operand type error encountered during Order Creation cron.
- Addressed the error 'Undefined array key STAT' that occurred during Order Creation.
- Updated the customer PO reference number in order history to resolve issues.
- Fixed the URL key generation for products with name, SKU, and randomNumber to ensure compatibility.
- Addressed BOD XML path changes for invoice quantity to maintain compatibility.
- Fixed issues related to invoice and shipment quantity to ensure compatibility.
- Added validation for customer numbers during order sync with M3 and displayed actual error messages.
- Implemented displaying actual errors in the admin panel when orders sync to ERP to enhance compatibility.
- Rectified the issue where CUNO was overwritten by ADID in Customer attribute mapping configuration to maintain compatibility.
- Resolved the problem where shipments were not created for configurable product variants in Magento, ensuring compatibility.

## **ION Package Update**

- Updated ION Package version to 3.2.1 with the below fix
- Show Shipment BOD is now working and getting triggered as expected after making changes in the Event Analytics Rules.



# **23.2.0**

## **Highlight**

- eConnect module is now compatible with Magento v2.4.6 and tested on PHP v8.1(but supports PHP v8.2 too)

## **Compatibility Fixes**

- Resolved the unsupported operand type error during Order Creation cron

## **Highlight**

- Zend framework dependency is completely replaced with Laminas

# **Other Fixes**

- Resolved the error 'Undefined array key STAT' thrown during Order Creation

## **ION Package Update**

- Updated ION Package version to 3.2.1 with the below fix
	- Show Shipment BOD is now working and getting triggered as expected after making changes in the Event Analytics Rules.

# **22.2.1-p1-EE**

## **Highlight**

- Product, Price, Category, AttributeSet, Customer Price, Shipment & Invoice creation(Order Module) will now get updated even when the SKU and ERP Item Number is different for a product

- eConnect will support the Open Shipments from M3 i.e. when the same shipment number is created for two different customer orders

## **Compatibility Fixes**

- Resolved the PHP warning(trying to access array on boolean) while trying to update customer price

## **Bug Fixes**

- Customer Price will get displayed in the frontend based on the currency value specified for that store in the backend

- Errors shown in the phtml files(Order History, Order View, Invoice History) related to PHP Tag are now resolved
	
# **22.2.1**

## **Highlight**

- eConnect module is now compatible with Magento v2.4.4 and PHP v8.1

- Improved the way of fetching ODSAPR to update it as Item Price

## **Enhancements**

- Improved the way of fetching ODSAPR from OPRBAS with the below things
	- ODSAPR will now be retrieved via EXPORTMI instead of using the below APIs
		- OIS017MI/LstPriceList
			- Reason:
				- LIST API will always bring the whole data including different PriceCodes & CurrencyCodes irrespective of what input data we pass. 
				- Also, eConnect was always getting the first record from the LIST APIs result without checking the PriceCode and Currency values to fetch the FVDT value which is required to call OIS017MI/GetBasePrice. 
				- Sometimes it fetches the FVDT value which doesn't matches with the PriceCode and Currency specified in the Backend 'Basic data configuration'
	
		- OIS017MI/GetBasePrice
			- Reason: 
				- Due to the reason mentioned under the LIST API, we have moved to EXPORTMI which brings all the necessary data we need

	- Added the following additional validations in the EXPORTMI while fetching the ODSAPR
		- FVDT(Valid From Date must be equal to and lesser than the current date) & LVDT(Valid To Date must be greater than the current date
	
		- If the result contains more than one entry with a valid date then the ODSAPR will choose the entry with the nearest date
	
	- Added an additional field in the Backend Configuration to choose whether the MMSAPR value can be set as an item price if the ODSAPR value is 0 for the item

		- If Item Price field is selected as 'ODSAPR' then a new setting called 'Fallback Item Price' will appear
![Fallback Item Price](../../../ecommerce/images/econnect-user-manual-ion-part1/odsapr-field.png)

			- If the above setting is set to Yes, then the item price will be updated with MMSAPR from MITMAS only if the ODSAPR from OPRBAS is 0 or there is no valid price data for the item.

			- If the above setting is set to No, then the item price will be updated with '0.00'
 
- External tracking number information will get updated via MWS410MI/GetHead API since it is not coming under the Shipment BOD

- Re-aligned the eConnect-ION backend configuration settings in a user friendly way

## **Compatibility Fixes**

- Resolved all the compilation errors thrown after running the command 'setup:di:compile'

- Unable to read messages from the queue so removed the additional and unused abstract classes with null values used in the constructors

- Resolved the SQL error thrown while reading the SalesOrder/Shipment BOD from the Queue

- JDCD value will be sent as 1 in the order creation request when the 'Ship Complete' checkbox is checked while placing the order

- Resolved the PHP error 'false to array conversion' thrown in customer module

## **Bug Fixes**

- Product's visibility will get updated even when there are multiple sites available 

- Handled the strict validations for all the PHP built-in functions used in eConnect
	- trim()
	- substr()
	- explode()
	- strtotime()
	- strpos()

# **22.2.0-p2**

## **Enhancements**
- Now customer price is supporting with multiple currency and display the store specific configurable currency prices on product view page.

# **22.2.0-p1**

## **Enhancements**
- Now customer price is applicable even sku and erp item number are different, previously sku and erpItemNumber should always same to apply the customer price.

## **Bug Fixes**

- Order view page now display with respective details.Previously order view page is blank when tracking details not available for the respective order.

# **22.2.0**

## **Enhancements**
 
- Based on the M3 release-Oct 2021, changes are done for bringing the Invoice BOD from M3

	- Earlier OINVOH table was used to bring the Customer Order Invoices from M3 but now it has changed to CINHED.
	
	- ION Package v3.2.0 must be used for this eConnect version
	
	- Provided compatibility for the changes in the structure of the Invoice Line nodes in the Invoice BOD


## **eConnect Compatibility for Commerce**

- Overall modules are now similar to the eConnect-Community code except for the Product save logic and Gift wrap related code changes in Order


## **Bug Fixes**

- Resolved the error in Order Creation flow when the shipping address does not exist for the order

- Invoice creation and update will work even when same company_division combo is configured for all the websites

- Creation of Partial shipment and Invoice will work as expected

- Reapeated status history shown in admin sales_order_view is now resolved

- Resolved the issue during order creation when the length of the city in Address exceeds the maximum character of 20

- Xpath changes are done for the SalesRep specific fields - RESP and SMCD

- Error thrown during product sync from the admin grid is now resolved

- API's configured in the 'Additional Entity Attribute Mapping' will work only when their status is Enabled


# **21.4.0**

## **Highlight**

- Customer specific price related cache issue on Product Detail Page is now resolved


## **New Features/Enhancements**
 
- 'Additional Entity Attribute Mapping' feature now comes with the support of website scope

- Delivery address chosen by the customers can be sent to M3 just by sending the Address Type and the Address ID(only if valid ID exists) via 'addBatchHead' transaction


## **eConnect-base Compatibility**

- Changes are done in the Order Creation flow to make it compatible with the eConnect-base 6.1.1.


## **Bug Fixes**

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
