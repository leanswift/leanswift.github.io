# Add-on for eConnect for M3

# **RMA**

## **Version 4.1.0**


**Table of Contents**


- [**Overview**](#overview)
- [**Environment Details**](#environment-details)
- [**Standard Features**](#standard-features)
- [**Enhancements**](#enhancements)
- [**Known Issues**](#known-issues)
- [**Pre-requisites**](#pre-requisites)

# **Overview**

 **LeanSwift eConnect for Infor M3** is a Magento extension that provides simple yet powerful integration between Magento eCommerce platform and Infor M3.

Extends standard Magento functionality and offers several transactions to ensure your eCommerce websites contain up-to-date information from your M3 ERP.

 **LeanSwift eConnect for Infor M3** is available for Magento Open Source and Magento Commerce and for Infor M3 version 7.x and above. It is also compatible with multi-tenant cloud editions of Infor M3 (Cloudsuite).

 **Add-on RMA** for eConnect leverages built-in functionality for returns management in Magento Commerce and provides integration with M3.

# **Environment Details**

| **Environment** | **Version** |
| --- | --- |
| Magento Community | 2.4.1 |
| eConnect | 20.3.1 |
| eConnect Base | 5.0.0 |
| Rabbitmq | 3.8.3 |
| ION Desk | 12.0 |
| PHP | 7.4.12 |
|LeanSwift ION-BOD package |3.0.0 |

# **Standard Features**

Functionality remains the same as in the previous version. 

Leverages Return Merchandise Authorization in Magento Commerce and synchronizes Customer Returns with M3.

  ●	Initiate RMA transactions from Magento and complete processing them in M3

  ●	Manage Returns, Claims, and Exchanges

  ●	Generate Credit Memos within Magento based on credit invoices issued in M3

The M3 OIS390 functionality is not used as it does not automatically provide for 
Return header creation (or) the association of header and line charges.


# **Enhancements**

- With 20.3.0, there is a major technical architectural change in the solution. BODs from ION are now configured to be sent to a REST API in Magento, which in turn sends them to RabbitMQ for storage and processing by eConnect. In the previous versions, ION sends BODs to RabbitMQ directly.

_Note: This version is tested only on M3-Multi-tenant_

# **Known Issues**

ERP Final Order number will not be updated in Magento when different Order Type is configured in Global and Website level. Order BOD's are validated against global settings so order from website level are ignored.

# **Pre-requisites**

- LeanSwift eConnect 20.3.1 must be installed on Magento 2.4.1 or greater



