

![eConnect for Infor SX.e / Infor CloudSuite Distribution](../../../images/banner-econnect-sxe.jpg)

# eConnect for SX.e/CSD - Net Change Report

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
  
