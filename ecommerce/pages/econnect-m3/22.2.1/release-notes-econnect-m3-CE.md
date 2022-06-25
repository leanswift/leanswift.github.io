# **eConnect 22.2.1**

# Table of contents

- [**Environment Details**](#environment-details)
- [**Standard Features**](#standard-features)
- [**Enhancements**](#enhancements)
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

# **Highlight**

- eConnect module is now compatible with Magento v2.4.4 and PHP v8.1

# **Enhancements**
 
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