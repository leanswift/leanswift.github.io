

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

Added a new section in the admin to add the extra fields to be sent while creating an order. This same section can be used for SX.e and CSD.
Added support to sync more customer fields from the following APIs
- sxapiARGetCustomerDataGeneralV2
- sxapiARGetCustomerDataGeneralRest
- sxapiARGetCustomerDataOrdering
- sxapiARGetCustomerDataOrderingRest
- sxapiARGetCustomerDataTaxing
Enhanced Product sync to support more attributes from following APIs 
- sxapiICGetWhseProductDataGeneralV3
- sxapiICGetProductDataGeneralV4
- sxapiICGetWhseProductDataTaxingv2


## Issues faced

Checkout sidebar is not getting updated when changing the quantity in mini cart from checkout page]
CenPOS order comments will not work
Point to note: Customer cron will take long time to run (depending on the size of customers to be synced )since concurrent api call could not be made.

## Metrics

The metrics taken for 50k products and its response to update in magento in the local system for  Batch Size - 50.

| Type | Time taken(Seconds) |
| --- | --- |
| Product with bulk | 462.45355701447 |
| Product without bulk | 289.18326210976|

The metrics taken for 10k customers and its response to update in magento via cron is as below 

| Type | Time taken(Seconds) |
| --- | --- | 
| Customer sync | 4minutes |

The metrics taken for Order creation and sync in CSD for a quanitiy of 100 orders in cron is 407.21320414543 (in seconds)

## Product Generation

https://docs.google.com/document/d/1UVBOFmWBvb7gjMYaM1kCoSiXysMILLVxTwWy8Wmvj14/edit#heading=h.d3mplszcczxv


## Bulk update magento

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






