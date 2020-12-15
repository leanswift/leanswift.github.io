




# **eConnect for SX.e** 
# **20.3.0** 
# **Community Edition**





# **Internal Release Notes**

























- Table of Contents
- Environment Details	
- Enhancements	
- JIRA References
- GitHub Link
- Documentation
- Points of Contact
























## Environment Details

Software Name
Version
Magento Open Source
2.3.5
Infor SX.e 
6.1.091
Infor Cloudsuite Distribution
11.20.1
Php version
7.2.24



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





## Metrics

The metrics taken for 50k products and its response to update in magento in the local system for  Batch Size - 50.


Type
Time taken(Minutes)
Stock(3 sources)
3.3
Stock with indexer(3 sources)
6.8
Products
20.98
Products with indexer
25.30
Stock and products with indexer
29



For updating 2L products with sending products request in batches takes below time


Type
Time taken(Minutes)
Stock with indexer
60
Product with indexer
80


## Product Generation

https://docs.google.com/document/d/1UVBOFmWBvb7gjMYaM1kCoSiXysMILLVxTwWy8Wmvj14/edit#heading=h.d3mplszcczxv


## Bulk update magento

https://docs.google.com/document/d/1q6F9qDYb6NQ3SD7_atTA6AeGYoBQjKAz6f5ExAiKACo/edit


## JIRA References

All
User Stories/Tasks
Bugs Identified/Fixed/Closed 

## GitHub Link

https://github.com/leanswift/eConnect-SXe/releases/tag/20.2.0

## Documentation

All relevant documentation regarding release 20.3.0 are available on LeanSwift’s Intranet 



## Points of Contact

- nanthini.muralidaran@leanswift.com
- srinidhi.narayanan@leanswift.com
- nrithya.rajagopalan@leanswift.com






