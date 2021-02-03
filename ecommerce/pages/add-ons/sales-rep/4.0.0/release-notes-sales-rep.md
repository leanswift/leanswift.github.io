# Add-on for eConnect for M3

# **Sales Representative**

## **Version 4.0.0**


**Table of Contents**

- [**Sales Representative**](#sales-representative)
- [Add-on for eConnect for M3](#add-on-for-econnect-for-m3)
  - [**Version 4.0.0**](#version-400)
- [**Release Notes**](#release-notes)
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

- Sales rep roles will be automatically assigned during Sales rep installation

-

# **Bug Fixes**

-

# **Pre-requisites**

- LeanSwift eConnect 19.1.0 must be installed on Magento 2.3.1 or greater
- If &quot;ION&quot; is selected as M3 Connection protocol must ensure that Salesrep data for customers from CustomerPartyMaster BOD is imported before using the add-on
  - Save field mappings for &quot;SalesPersonReference/ID&quot;, &quot;SalesPersonReference/Name&quot; and &quot;SalesPersonReference/SalesPersonRole
  - Execute &quot;Initial Load&quot; to fetch Customer Data from M3 to Magento

# **Limitations**

1. eConnect and hence the Sales Rep add-on, can be set to work with only ONE of the two options, exclusively

(1) LeanSwift eLink or


