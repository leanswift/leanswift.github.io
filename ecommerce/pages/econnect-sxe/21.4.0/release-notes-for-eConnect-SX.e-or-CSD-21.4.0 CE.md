![eConnect for Infor SX.e / Infor CloudSuite Distribution](../../../../images/banner-econnect-sxe.jpg)

# **eConnect for SX.e/CSD** 
# **21.4.0 - Community Edition** 


## **Release Notes**


## Environment Details

| Software Name | Version | 
| --- | --- |
| Magento Open Source| 2.4.3 |
| Infor SX.e  | 6.1.091 |
| Infor Cloudsuite Distribution | 11.20.1 |
| PHP | 7.4.25 |


## Highlights

- An exclusive Code Quality release that meets the Magento Coding Standard


## Bug Fixes

- Customer price value on the list page is showing the correct value

- Able to create Order with more than one line items without errors

- Unnecessary lines are removed from the Product sync log

- Running product cron via browser is working without throwing 500 error

- Product sync related logs will be printed only in the ProductSync.log instead of partially printing in the StockSync.log

- Batch size value for cron jobs is picking the correct values

- ShipTo value is getting synced successfully for the Shipping Addresses

- Customer price works fine in the list page even when the cache hours is set to '0'

- Warehouse information is perfectly loading for the Main and other websites

- After setting the Price to website scope, Product Price/Base Price is now getting synced without issues for the websites other than Main.

- Issues related to Price sync are now working after refactoring the code

- Stock and stock status getting reflected without issues during the first time page load

- Issues related to Order sync are working fine after refactoring the code

- Issues related to Product sync are working fine after refactoring the code

- Issues related to Stock sync are working fine after refactoring the code


### Known Issues

- Checkout sidebar is not getting updated when changing the quantity in mini cart from checkout page


## Points of Contact

- nanthini.muralidaran@leanswift.com
- deepthi.tadikamalla@leanswift.com

