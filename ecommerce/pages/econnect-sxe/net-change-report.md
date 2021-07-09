

![eConnect for Infor SX.e / Infor CloudSuite Distribution](../../../images/banner-econnect-sxe.jpg)

# eConnect for SX.e/CSD - Net Change Report

## 21.1.0


### Enhancements

- Selected shipping address will now be seen in the ShipTo section on the checkout page
- Stock is updated and refelected on Stock sync from the frontend via Product View page
- Salable quantity is updated and refelected on Stock sync from the frontend
- Re-ordering the orders with more than one quantity now adds all the items to the cart
- Category is getting mapped to the product without any error
- Order Sync, Order history and Inventory Cron issues are resolved
- Order creation is working as expected for CE after the latest code changes
- The error thrown during the initial installation's 'setup:upgrade' process is resolved
- Resolved the Exception thrown for the customers without the Sx.e/CSD Customer number during the customer login 


### Known Issues

- Checkout sidebar is not getting updated when changing the quantity in mini cart from checkout page
- CenPOS order comments won't appear in Infor SX.e/CSD.
- Point to note: Customer cron will take long time to run (depending on the size of customers to be synced and the APIs configured in the Backend Mapping section).


## 20.3.0


### Highlights

- This is the first version of integration between Magento Enterprise edition and Infor SX.e/CSD.

### Enhancements

- Added a new section in the Magento Backend to add the extra fields to be sent while creating an order(Applicable for normal and CenPOS orders)
- Provided option in the Magento Backend to mention the transaction type (or) order type value for normal orders
- Provided option in the Magento Backend to mention the transaction type and order type value for CenPOS orders
- Order request information is shown in the backend sales order view section
- ERP order number and customer number are shown in the backend sales order view section
- Added support to show all the three lines of ShipTo address in Infor SX.e/CSD
- Added support to synchronize more customer fields
- Added support to synchronize more product fields
- Category synchronization is now supported for product
- Provided support to an upgraded version of Stock APIs
- Authentication details will now be auto-populated in the Authentication section after uploading an ionapi file
- Reorganized the Cron section by grouping the Order, Customer and Product Cron.
- Sensitive information like passwords and URLs are hidden in the log


### Known Issues

- Checkout sidebar is not getting updated when changing the quantity in mini cart from checkout page
- CenPOS order comments won't appear in Infor SX.e/CSD.
- Point to note: Customer cron will take long time to run (depending on the size of customers to be synced and the APIs configured in the Backend Mapping section).
  

## 20.2.0

This is basically performance improvement

### Enhancements

- Backend configuration to Enable/Disable Bulk API to add/update products 
- A separate cron for Stock sync that works only if BULK API is disabled.
- Added concurrent request for the product sync and stock sync for V11.X.
- Added a separate logger called bulkproductSync for the bulk product sync transactions.

### Fixes

- Memory leak during stock cron sync
- Connection time out during product sync
- Customer price not getting updated due to cache tags

## 20.1.0

### Features

All features developed in 19.1.0 and 19.1.3 for integrating with SX.e version 6.x have been developed to support Cloudsuite Distribution, that is, version SX.e 11.x.

### Fixes

Other customer data does not sync when there is an exception from SX.e for one of the customers.

## 19.1.4

### Fixes

Added a fix in order creation to support cenpos payment addon.

## 19.1.3

### Features

- Fetch and display account receivable information for the customer.
- Added an option to print and download ERP order
- Include PO# in ERP Order History	
- Fetch and display tracking number for ERP order
- Changed Version handling to display the Addon’s version.

### Fixes

Issue on category listing page when no products are found in a category.

## 19.1.2

### Fixes

ERP Order Details not retrieved in Order History section in front-end.

## 19.1.1

### Features

Added support for Composer Installation

## 19.1.0

### Features
Fetches and maintains up-to-date data from SX.e to Magento for product price, inventory, customer address and order status. Creates orders in SX.e for every order created in Magento.

- Inventory Synchronization
 
  - Supports real-time inventory synchronization to ensure accurate stock display to customers.
  - Real-time synchronization can be performed multiple times through the various ordering stages such as, while viewing product details, while adding to cart and on checkout.
  - Manual synchronization from admin panel and synchronization via a scheduled background job are available.
 
- Price Synchronization
 
  - Supports List Price (Product Base Price) synchronization for all types of Products in Magento.
  - Manual synchronization from admin panel and synchronization via a scheduled background job are available for List Price.
  - Real-time fetch of Customer Specific Price & Synchronization.
  - Real-time synchronization can be performed multiple times through various stages such as while viewing product list page, viewing product details, and on editing cart.
  - If customer has tier pricing in SX.e, appropriate associated price can be viewed in cart page
  
- Customer Address Synchronization

  - Customer Billing Address & Shipping Addresses can be synchronized with customers in Magento.
  - Manual synchronization from admin panel and synchronization via a scheduled background job are available.
  - Addresses synchronization on customer login is available.
 
 
- Order Synchronization

  - Order Creation
    - Supports creation of sales orders in SX.e for every order placed via Magento webshop.
    - Add order notes from webshop checkout section to order in SX.e as well.
    - Manual synchronization from admin panel and synchronization via a scheduled background job are available.
  - Order Status 
    - Supports synchronization of the status of a customer order within SX.e with the corresponding order in Magento.
    - Shipments & Invoices in SX.e are reflected within Magento according to order status in SX.e.
    - Tracking numbers associated to an order in SX.e are also synchronized.
    - Manual synchronization from admin panel and synchronization via a scheduled background job are available.
  - Order History
    - Easy access for customers to view all orders placed through Magento as well as those placed in SX.e directly via “My Orders” page.
    - View order details and reorder.  
    - Manual synchronization from “My Orders” panel and synchronization via a scheduled background job are available.
    
- Configuration for the above
    - Highly configurable!
      - SX.e instance URL and authentication information
      - Field Mapping between Magento and SX.e
      - Synchronization options
      - Scheduling of background jobs
