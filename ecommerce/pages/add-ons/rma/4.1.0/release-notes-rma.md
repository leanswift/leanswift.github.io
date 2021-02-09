# Add-on for eConnect for M3

# **RMA**

## **Version 4.1.0**


**Table of Contents**


- [**Overview**](#overview)
- [**Environment Details**](#environment-details)
- [**Standard Features**](#standard-features)
- [**New Features**](#new-features)
- [**Enhancements**](#enhancements)
- [**Bug Fixes**](#bug-fixes)
- [**Pre-requisites**](#pre-requisites)
- [**Limitations**](#limitations)

# **Overview**

 **LeanSwift eConnect for Infor M3** is a Magento extension that provides simple yet powerful integration between Magento eCommerce platform and Infor M3.

Extends standard Magento functionality and offers several transactions to ensure your eCommerce websites contain up-to-date information from your M3 ERP.

 **LeanSwift eConnect for Infor M3** is available for Magento Open Source and Magento Commerce and for Infor M3 version 7.x and above. It is also compatible with multi-tenant cloud editions of Infor M3 (Cloudsuite).

 **Add-on Sales Representative** for eConnect provides the ability to leverage Magento to manage customers and customer sales orders in M3.

# **Environment Details**

| **Environment** | **Version** |
| --- | --- |
| Magento Open source | 2.4.1 |
| Magento Community | 2.4.1 |
| eConnect | 20.3.0 |
| eConnect Base | 5.0.0 |
| Rabbitmq | 3.8.3 |
| ION Desk | 12.0 |
| PHP | 7.4.12 |

# **Standard Features**



# **New Features**



# **Enhancements**

- With 20.3.0, there is a major technical architectural change in the solution. BODs from ION are now configured to be sent to a REST API in Magento, which in turn sends them to RabbitMQ for storage and processing by eConnect. In the previous versions, ION sends BODs to RabbitMQ directly.

_Note: This version is tested only on M3-Multi-tenant_

# **Bug Fixes**


# **Pre-requisites**

- LeanSwift eConnect 20.3.0 must be installed on Magento 2.4.1 or greater


# **Limitations**






