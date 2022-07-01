# **eConnect 22.2.1**

# Table of contents

- [**Environment Details**](#environment-details)
- [**Standard Features**](#standard-features)
- [**Prerequisites**](#prerequisites)
- [**Highlight**](#highlight)
- [**Enhancements**](#enhancements)
- [**Compatibility Fixes**](#compatibility-fixes)
- [**Bug Fixes**](#bug-fixes)
- [**Point of Contact**](#point-of-contact)


# **Environment Details**

| **Software Name** | **Version** |
| --- | --- |
| Magento version | 2.4.4 |
| eConnect Base | 6.2.1 |
| PHP version | 8.1.6 |
| RabbitMQ | 3.7.28 |
| Infor M3 (MT) | 16.1 |
| ION Package | 3.2.0 |

# **Standard Features**

All the standard functionalities of core eConnect are supported in v22.2.1, which includes the following:

- Customer Registration
- Customer Addition
- Customer Synchronization
- Product Addition
- Product Synchronization
- Inventory Synchronization
- Customer Price Synchronization
- Order Creation
- Order Synchronization
- Shipment Synchronization
- Invoice History
- Order History
- Initial Load

# Prerequisites

- From Magento v2.4.4 with PHP v8.1, the following setting must be set to 'Yes' in order to make successful connection with the Infor ION API.

	![oAuth Access Token](../../../../ecommerce/images/econnect-user-manual-ion-part1/access_token_setting.png)

# **Highlight**

- eConnect module is now compatible with Magento v2.4.4 and PHP v8.1

- Improved the way of fetching ODSAPR to update it as Item Price

# **Enhancements**

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
![Fallback Item Price](../../../../ecommerce/images/econnect-user-manual-ion-part1/odsapr-field.png)

			- If the above setting is set to Yes, then the item price will be updated with MMSAPR from MITMAS only if the ODSAPR from OPRBAS is 0 or there is no valid price data for the item.

			- If the above setting is set to No, then the item price will be updated with '0.00'
 
- External tracking number information will get updated via MWS410MI/GetHead API since it is not coming under the Shipment BOD

- Re-aligned the eConnect-ION backend configuration settings in a user friendly way

# **Compatibility Fixes**

- Resolved all the compilation errors thrown after running the command 'setup:di:compile'

- Unable to read messages from the queue so removed the additional and unused abstract classes with null values used in the constructors

- Resolved the SQL error thrown while reading the SalesOrder/Shipment BOD from the Queue

- JDCD value will be sent as 1 in the order creation request when the 'Ship Complete' checkbox is checked while placing the order

- Resolved the PHP error 'false to array conversion' thrown in customer module

# **Bug Fixes**

- Product's visibility will get updated even when there are multiple sites available 

- Handled the strict validations for all the PHP built-in functions used in eConnect
	- trim()
	- substr()
	- explode()
	- strtotime()
	- strpos()

# **Point of Contact**

- [nanthini.muralidaran@leanswift.com](mailto:nanthini.muralidaran@leanswift.com)
- [prabhu.mano@leanswift.com](mailto:prabhu.mano@leanswift.com)
- [deepthi.tadikamalla@leanswift.com](mailto:deepthi.tadikamalla@leanswift.com)
- [narayanan.gurusamy@leanswift.com](mailto:narayanan.gurusamy@leanswift.com)
