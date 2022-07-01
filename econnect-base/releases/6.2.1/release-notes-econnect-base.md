# **eConnectBase 6.2.1**

# Table of contents

- [**Environment Details**](#environment-details)
- [**Overview**](#overview)
- [**Prerequisites**](#prerequisites)
- [**Highlight**](#highlight)
- [**Compatibility Fixes**](#compatibility-fixes)
- [**Point of Contact**](#point-of-contact)

# **Environment Details**

| **Software Name** | **Version** |
| --- | --- |
| Magento version | 2.4.4 |
| PHP version | 8.1.6 |

# **Overview**

- Provides the connectivity to eLink and/or Infor systems with the use of a generic function which decides whether to call the eLink / ION APIs based on the M3 Connection Protocol chosen in the backend
- Acts as the communication layer for RabbitMQ Message consumption
- Acts as a core module for 
	- eConnect
	- IDM
	- Supplier Portal
- eConnect add-ons depend on both eConnect-base and eConnect likewise SupplierPortal add-ons depend on both eConnect-base and SupplierPortal

# Prerequisites

- From Magento v2.4.4 with PHP v8.1, the following setting must be set to 'Yes' in order to make successful connection with the Infor ION API.

	![oAuth Access Token](../../../econnect-base/images/access_token_setting.png)

# **Highlight**

- eConnect-base module is now compatible with Magento v2.4.4 and PHP v8.1

# **Compatibility Fixes**

- Resolved all the compilation errors thrown after running the command 'setup:di:compile'

- Unable to read messages from the queue so removed the additional and unused abstract classes with null values used in the constructors

- PHP 8.x expects the strict validation of string so handled it for all the PHP built-in functions used in eConnect-base
	- trim()
	- substr()
	- explode()
	- strtotime()
	- strpos()

# **Point of Contact**

- [nanthini.muralidaran@leanswift.com](mailto:nanthini.muralidaran@leanswift.com)
- [niranjan.b@leanswift.com](mailto:niranjan.b@leanswift.com)
- [prabhu.mano@leanswift.com](mailto:prabhu.mano@leanswift.com)
- [deepthi.tadikamalla@leanswift.com](mailto:deepthi.tadikamalla@leanswift.com)
- [vaithiyanathan.paramasivam@leanswift.com](mailto:vaithiyanathan.paramasivam@leanswift.com)
- [narayanan.gurusamy@leanswift.com](mailto:narayanan.gurusamy@leanswift.com)
