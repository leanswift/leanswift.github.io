# Add-on for eConnect for M3

# **Sales Representative**

## **Version 4.0.0**


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
| eConnect | 2.3.0 |
| eConnect Base | 5.0.0 |
| Rabbitmq | 3.8.3 |
| ION Desk | 12.0 |
| PHP | 7.4.12 |

# **Standard Features**

All the standard functionalities remain the same as in the previous version.

Every Sales Representative can, for their respective customers,

- Review customer information
- Review existing sales orders, shipments &amp; invoices
- Create sales orders on behalf of a customer

# **New Features**

- &#39;Login as Customer&#39; now comes with Magento by default.
- For this to work, &#39;Allow remote shopping assistance&#39; must be enabled and this will happen automatically when &#39;Cron settings for import sales rep&#39; gets executed

# **Enhancements**

- With 20.3.0, there is a major technical architectural change in the solution. BODs from ION are now configured to be sent to a REST API in Magento, which in turn     sends them to RabbitMQ for storage and processing by eConnect. In the previous versions, ION sends BODs to RabbitMQ directly.
- Sales rep roles will be automatically assigned during Sales rep installation.



# **Bug Fixes**

- When no email is configured for salesrep in M3, empty response is handled to auto generate default email.

# **Pre-requisites**

- LeanSwift eConnect 20.3.0 must be installed on Magento 2.4.1 or greater
- If &quot;ION&quot; is selected as M3 Connection protocol must ensure that Salesrep data for customers from CustomerPartyMaster BOD is imported before using the add-on
  - Save field mappings for &quot;SalesPersonReference/ID&quot;, &quot;SalesPersonReference/Name&quot; and &quot;SalesPersonReference/SalesPersonRole
  - Execute &quot;Initial Load&quot; to fetch Customer Data from M3 to Magento

# **Limitations**

- For Shipment and Invoice tabs to be visible for an order in order detail page, extra permissions to 'Archive' section has to be provided.
_Note: This is applicable only for Magento Commerce._

- Orders associated to multiple customers may get displayed in the Sales Rep Login. If Multiwarehouse and Order Edit Add-ons are also installed along with Salesrep
  To overcome this, We need to disable those Add-ons.
  
- Clicking on Shipment tab may throw an error. This will happen if Salesrep is used along with Multiwarehouse Add-on.
  To overcome this, we need to install v7.7.6 version of Wyomind_AdvancedInventory in Multiwarehouse.



