Add-on for eConnect for M3
==========================

Sales Representative
====================

Version 4.1.0
-------------

**Table of Contents**

-   [Overview](#overview)

-   [Environment Details](#environment-details)

-   [Standard Features](#standard-features)

-   [Highlight](#highlight)

-   [Pre-requisites](#pre-requisites)

-   [Limitations](#limitations)

Overview
========

**LeanSwift eConnect for Infor M3** is a Magento extension that provides simple
yet powerful integration between Magento eCommerce platform and Infor M3.

Extends standard Magento functionality and offers several transactions to ensure
your eCommerce websites contain up-to-date information from your M3 ERP.

**LeanSwift eConnect for Infor M3** is available for Magento Open Source and
Magento Commerce and for Infor M3 version 7.x and above. It is also compatible
with multi-tenant cloud editions of Infor M3 (Cloudsuite).

**Add-on Sales Representative** for eConnect provides the ability to leverage
Magento to manage customers and customer sales orders in M3.

Environment Details
===================

| **Environment**     | **Version** |
|---------------------|-------------|
| Magento Open source | 2.4.3       |
| Magento Commerce    | 2.4.3       |
| eConnect Community  | 22.2.0      |
| eConnect Commerce   | 22.2.0      |
| eConnect Base       | 6.1.1       |
| Rabbitmq            | 3.7.28      |
| Infor M3            | 16.1        |
| PHP                 | 7.4         |
| ION Package Version | 3.2.0       |

Standard Features
=================

All the standard functionalities remain the same as in the previous version.

Every Sales Representative can, for their respective customers,

-   Review customer information

-   Review existing sales orders, shipments & invoices

-   Create sales orders on behalf of a customer

Highlight
=========

-   Earlier current Xpath value for SMCD, RESP, was interchanged,
    Responsible(RESP) in M3 was mapped to SMCD_SalesPerson value in
    eConnect(Attribute mapping section) and Salesperson(SMCD) in M3 to
    RESP_Responsible in eConnect(Attribute mapping section)

-   Now  
    Responsible(RESP) in M3 is mapped to RESP_Responsible in eConnect.  
    Salesperson(SMCD) in M3 is be mapped to SMCD_SalesPerson in eConnect

-   SalesRep made compatible to the eConnect-base v6.1.1 & eConnect v22.2.0

*Note : This code change is part of econnect code and not salesrep*

Pre-requisites
==============

-   If "ION" is selected as M3 Connection protocol must ensure that Salesrep
    data for customers from CustomerPartyMaster BOD is imported before using the
    add-on

-   Save field mappings for "SalesPersonReference/ID",
    "SalesPersonReference/Name" and "SalesPersonReference/SalesPersonRole

-   Execute "Initial Load" to fetch Customer Data from M3 to Magento

Limitations
===========

-   For Shipment and Invoice tabs to be visible for an order in order detail
    page, extra permissions to 'Archive' section has to be provided. *Note: This
    is applicable only for Magento Commerce.*

-   Orders associated to multiple customers may get displayed in the Sales Rep
    Login. If Multiwarehouse and Order Edit Add-ons are also installed along
    with Salesrep To overcome this, We need to disable those Add-ons.

-   Clicking on Shipment tab may throw an error. This will happen if Salesrep is
    used along with Multiwarehouse Add-on. To overcome this, we need to install
    v7.7.6 version of Wyomind_AdvancedInventory in Multiwarehouse.

Point of Contacts
-----------------

-   <prabhu.mano@leanswift.com>

-   <nanthini.muralidaran@leanswift.com>

-   [deepthi.tadikamalla\@leanswift.com](mailto:deepthi@leanswift.com)

-   <narayanan.gurusamy@leanswift.com>
