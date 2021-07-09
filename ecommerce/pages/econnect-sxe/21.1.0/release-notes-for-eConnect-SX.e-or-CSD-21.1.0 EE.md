![eConnect for Infor SX.e / Infor CloudSuite Distribution](../../../../images/banner-econnect-sxe.jpg)

# **eConnect for SX.e/CSD** 
# **21.1.0 - Enterprise Edition** 


## **Release Notes**


## Environment Details

| Software Name | Version | 
| --- | --- |
| Magento Commerce| 2.4.2-p1 |
| Infor SX.e  | 6.1.091 |
| Infor Cloudsuite Distribution | 11.20.1 |
| PHP | 7.4.21 |


## Bug Fixes

- Selected shipping address will now be seen in the ShipTo section on the checkout page

- Stock is updated and reflected on Stock sync from the frontend via Product View page

- Salable quantity is updated and reflected on Stock sync from the frontend

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

## Note

- This is a bug fix release with the latest Magento version 2.4.2-p1, so only the minimal testing is done 

## Points of Contact

- nanthini.muralidaran@leanswift.com
- deepthi.tadikamalla@leanswift.com

