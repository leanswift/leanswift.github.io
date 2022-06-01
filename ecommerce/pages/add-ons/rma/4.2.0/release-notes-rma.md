# Add-on for eConnect for M3

# **RMA**

## **Version 4.2.0**


**Table of Contents**


- [**Overview**](#overview)
- [**Environment Details**](#environment-details)
- [**Standard Features**](#standard-features)
- [**Highlight**](#highlight)
- [**Known Issues**](#known-issues)


# **Overview**

 **LeanSwift eConnect for Infor M3** is a Magento extension that provides simple yet powerful integration between Magento eCommerce platform and Infor M3.

Extends standard Magento functionality and offers several transactions to ensure your eCommerce websites contain up-to-date information from your M3 ERP.

 **LeanSwift eConnect for Infor M3** is available for Magento Open Source and Magento Commerce and for Infor M3 version 7.x and above. It is also compatible with multi-tenant cloud editions of Infor M3 (Cloudsuite).

 **Add-on RMA** for eConnect leverages built-in functionality for returns management in Magento Commerce and provides integration with M3.

# **Environment Details**

| **Environment** | **Version** |
| --- | --- |
| Magento Community | 2.4.3 |
| eConnect | 22.2.0 |
| eConnect Base | 6.1.1 |
| Rabbitmq | 3.7.28 |
| Infor M3 | 16.1 |
| PHP | 7.4 |
| ION package version |3.2.0 |

# **Standard Features**

Functionality remains the same as in the previous version. 

Leverages Return Merchandise Authorization in Magento Commerce and synchronizes Customer Returns with M3.

  ●	Initiate RMA transactions from Magento and complete processing them in M3

  ●	Manage Returns, Claims, and Exchanges

  ●	Generate Credit Memos within Magento based on credit invoices issued in M3

The M3 OIS390 functionality is not used as it does not automatically provide for 
Return header creation (or) the association of header and line charges.


# **Highlight**

- RMA is made compatible to the eConnect-base v6.1.1 & eConnect v22.2.0


_Note: This version is tested only on M3-Multi-tenant_

# **Known Issues**

- ERP Final Order number will not be updated in Magento when different Order Type is configured in Global and Website level. Order BOD's are validated against global settings so order from website level are ignored.


Point of Contacts
-----------------

-   <prabhu.mano@leanswift.com>

-   <nanthini.muralidaran@leanswift.com>

-   [deepthi.tadikamalla\@leanswift.com](mailto:deepthi@leanswift.com)

-   <narayanan.gurusamy@leanswift.com>


