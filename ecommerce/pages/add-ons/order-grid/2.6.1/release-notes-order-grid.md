Add-on for eConnect for M3
==========================

Configurable Order Grid
=======================

Version 2.6.1
-------------

**Table of Contents**

-   [Overview](#overview)

-   [Environment Details](#environment-details)

-   [Standard Features](#standard-features)

-   [Highlight](#highlight)

-   [Limitations](#limitations)

-   [Bug Fixes](#bug-fixes)

Overview
========

**LeanSwift eConnect for Infor M3** is a Magento extension that provides simple
yet powerful integration between Magento eCommerce platform and Infor M3.

Extends standard Magento functionality and offers several transactions to ensure
your eCommerce websites contain up-to-date information from your M3 ERP.

**LeanSwift eConnect for Infor M3** is available for Magento Open Source and
Magento Commerce and for Infor M3 version 7.x and above. It is also compatible
with multi-tenant cloud editions of Infor M3 (Cloudsuite).

**Add-on Configurable Order Grid** for eConnect extends the standard Magento
functionality and provides quick and easy Matrix Ordering capability to product
pages with synchronization from M3.

Environment Details
===================

| **Environment**     | **Version** |
|---------------------|-------------|
| Magento Open source | 2.4.6       |
| Magento Commerce    | 2.4.6       |
| eConnect Community  | 23.2.0      |
| eConnect Commerce   | 23.2.0      |
| eConnect Base       | 6.3.0       |
| Rabbitmq            | 3.7.28      |
| Infor M3            | 16.1        |
| PHP                 | 8.1         |
| ION Package Version | 3.2.1       |

Standard Features
=================

Functionality remains the same as in the previous version.

The module extends the standard Magento functionality for displaying products
based on selected attributes along with stock and price details.

• Displays real-time stock and price details of each product variant

• Can add different product variants of a Magento Configurable Product to cart
instantly

• X and Y axis attributes are configurable by administrator

Highlight
=========

- Order grid is made compatible with Magento v2.4.6 and PHP v8.1(Supports v8.2 too)

- Tested on eConnect-base v6.3.0 and eConnect v23.2.0

Limitations
===========

• Grid is available only for Configurable products

• Up to 3 attributes can be configured to display in the frontend

• eConnect and hence the Order Grid add-on, can be set to work with only ONE of
the two options, exclusively

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
(1) LeanSwift eLink or 

(2) ION Document Flows and ION APIs
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Bug Fixes
=========

- Resolved the exception thrown while adding the out of stock product with backorder to cart

- Resolved the exception thrown while opening the configurable product once the customer has logged into the site

Point of Contacts
-----------------

-   <prabhu.mano@leanswift.com>

-   [deepthi.tadikamalla\@leanswift.com](mailto:deepthi@leanswift.com)

-   <narayanan.gurusamy@leanswift.com>
