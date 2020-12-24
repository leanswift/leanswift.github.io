![eConnect for Infor SX.e / Infor CloudSuite Distribution](../../../../images/banner-econnect-sxe.jpg)

# **eConnect for SX.e/CSD** 
# **20.3.0 - Enterprise Edition** 


## **Release Notes**


## Environment Details

| Software Name | Version | 
| --- | --- |
| Magento Commerce| 2.4.1 |
| Infor SX.e  | 6.1.091 |
| Infor Cloudsuite Distribution | 11.20.1 |
| PHP | 7.4.12 |


## Highlights

- This is the first version of integration between Magento Enterprise edition and Infor SX.e/CSD.

## Enhancements

- Added a new section in the Magento Backend to add the extra fields to be sent while creating an order

- Provided option in the Magento Backend to mention the transaction type/order type value

- Order request information is shown in the backend sales order view section

- ERP order number and customer number are shown in the backend sales order view section

- Added support to show all the three lines of ShipTo address in Infor SX.e/CSD

- Added support to synchronize more customer fields

- Added support to synchronize more product fields

- Category synchronization is now supported for product

- Provided support to an upgraded version of Stock APIs

- Authentication details will now be auto-populated in the Authentication section after uploading an ionapi file

- Reorganized the Cron section by grouping the Order, Customer and Product Cron

- Sensitive information like passwords and URLs are hidden in the log

## Known Issues

- Checkout sidebar is not getting updated when changing the quantity in mini cart from checkout page

- Point to note: Customer cron will take a long time to run (depending on the size of customers to be synced and the APIs configured in the Backend Mapping section).

## Points of Contact

- nanthini.muralidaran@leanswift.com
- srinidhi.narayanan@leanswift.com
- nrithya.rajagopalan@leanswift.com

