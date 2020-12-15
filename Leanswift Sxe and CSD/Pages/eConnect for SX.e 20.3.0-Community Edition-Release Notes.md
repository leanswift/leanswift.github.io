

# **eConnect for SX.e** 
# **20.3.0** 
# **Community Edition**


# **Release Notes**

- Table of Contents
- Environment Details	
- Enhancements	
- JIRA References
- GitHub Link
- Documentation
- Points of Contact


## Environment Details

| Software Name | Version | 
| --- | --- |
| Magento Open Source| 2.4.0 |
| Infor SX.e  | 6.1.091 |
| Infor Cloudsuite Distribution | 11.20.1 |
| PHP version | 7.4.12 |



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

- Reorganized the Cron section by grouping the Order, Customer and Product Cron.


## Known Issues

- Checkout sidebar is not getting updated when changing the quantity in mini cart from checkout page

- CenPOS order comments will not work

- Point to note: Customer cron will take long time to run (depending on the size of customers to be synced and the APIs configured in the Backend Mapping section).

## Metrics

- The metrics taken for Order creation and sync in CSD for 100 orders with 2 or 3 lines in cron is 407.21320414543 (in seconds)

- The metrics taken for 10k customers and its response to update in magento in the local system for Batch Size - 100.

  | Type | Time taken(Minutes) |
  | --- | --- | 
  | Customer sync | 4 to 5 minutes for each batch |

- The metrics taken for 50k products(with 14 attributes configured in the mapping section) and its response to update in magento in the local system for Batch Size - 50.

  | Type | Time taken(Minutes) |
  | --- | --- |
  | Product with Bulk API enabled (with reindex)| 7 |
  | Product with Bulk API enabled (without reindex) | 5 |
  | Product without Bulk API enabled (with reindex)| 7 |
  | Product without Bulk API enabled (without reindex) | 4 |

**Product Generation**

https://docs.google.com/document/d/1UVBOFmWBvb7gjMYaM1kCoSiXysMILLVxTwWy8Wmvj14/edit#heading=h.d3mplszcczxv


**Bulk update magento** 

https://docs.google.com/document/d/1q6F9qDYb6NQ3SD7_atTA6AeGYoBQjKAz6f5ExAiKACo/edit


## JIRA References

All
User Stories/Tasks
Bugs Identified/Fixed/Closed 

## GitHub Link


## Documentation

All relevant documentation regarding release 20.3.0 are available on LeanSwift’s Intranet 


## Points of Contact

- nanthini.muralidaran@leanswift.com
- srinidhi.narayanan@leanswift.com
- nrithya.rajagopalan@leanswift.com






