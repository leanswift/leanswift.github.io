# Add-on for eConnect for M3

# **Configurable Order Grid**

## **Version 2.5.1**


**Table of Contents**


- [**Overview**](#overview)
- [**Environment Details**](#environment-details)
- [**Standard Features**](#standard-features)
- [**Enhancements**](#enhancements)
- [**Pre-requisites**](#pre-requisites)
- [**Limitations**](#limitations)

# **Overview**

 **LeanSwift eConnect for Infor M3** is a Magento extension that provides simple yet powerful integration between Magento eCommerce platform and Infor M3.

Extends standard Magento functionality and offers several transactions to ensure your eCommerce websites contain up-to-date information from your M3 ERP.

 **LeanSwift eConnect for Infor M3** is available for Magento Open Source and Magento Commerce and for Infor M3 version 7.x and above. It is also compatible with multi-tenant cloud editions of Infor M3 (Cloudsuite).

 **Add-on Configurable Order Grid** for eConnect extends the standard Magento functionality and provides quick and easy Matrix Ordering capability to product pages with synchronization from M3. 

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

Functionality remains the same as in the previous version. 

The module extends the standard Magento functionality for displaying products based on selected attributes along with stock and price details.

•	Displays real-time stock and price details of each product variant

•	Can add different product variants of a Magento Configurable Product to cart instantly

•	X and Y axis attributes are configurable by administrator


# **Enhancements**

- With 20.3.0, there is a major technical architectural change in the solution. BODs from ION are now configured to be sent to a REST API in Magento, which in turn     sends them to RabbitMQ for storage and processing by eConnect. In the previous versions, ION sends BODs to RabbitMQ directly.

_Note: This version is tested only on M3-Multi-tenant_

# **Bug Fixes**

- Based on Price Sync(Yes/No), customer specific price gets updated in frontend.
- Order sync with M3 for configurable products is  fixed ( Issue only in CE).

# **Pre-requisites**

•	LeanSwift eConnect 20.3.0 must be installed on Magento 2.4.1 or greater

# **Limitations**

•	Grid is available only for Configurable products

•	Up to 3 attributes can be configured to display in the frontend

•	eConnect and hence the Order Grid add-on, can be set to work with only ONE of the two options, exclusively 

    (1) LeanSwift eLink or 
  
    (2) ION Document Flows and ION APIs


