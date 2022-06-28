Add-on for eConnect for M3
==========================

IDM
===

Version 4.1.2
-------------

Table of contents
-----------------

-   [Overview](#overview)

-   [Environment Details](#environment-details)

-   [Standard Features](#standard-features)

-   [Limitations](#limitations)

-   [Bug Fix](#bug-fix)

-   [Highlight](#highlight)

-   [Point of Contacts](#point-of-contacts)

Overview
--------

**LeanSwift eConnect for Infor M3** is a Magento extension that provides simple
yet powerful integration between Magento eCommerce platform and Infor M3.

Extends standard Magento functionality and offers several transactions to ensure
your eCommerce websites contain up-to-date information from your M3 ERP.

**LeanSwift eConnect for Infor M3** is available for Magento Open Source and
Magento Commerce and for Infor M3 version 7.x and above. It is also compatible
with multi-tenant cloud editions of Infor M3 (Cloudsuite).

**Add-on IDM** for eConnect provides capability to upload, download or search
documents in Infor Document Management that can be leveraged in the web
front-end.


Environment Details
-------------------

| **Environment**     | **Version** |
|---------------------|-------------|
| Magento Open source | 2.4.4       |
| Magento Commerce    | 2.4.4       |
| eConnect Community  | 22.2.1      |
| eConnect Commerce   | 22.2.1      |
| eConnect Base       | 6.2.1       |
| Rabbitmq            | 3.7.28      |
| Infor M3            | 16.1        |
| PHP                 | 8.1.6       |

Standard Features
-----------------

Functionality remains the same as in the previous version. Provides integration
to Infor Document Management and allows access to attributes and documents in it
that can be leveraged in the web front-end. Features include functions made
available to build front-end functionality for the following operations,

-   Upload to IDM

-   Download from IDM

-   Search in IDM

Download Invoices from IDM on the "My Invoices" page. Options available for both
scheduled as well as real-time access to IDM.


Limitations
-----------

- eConnect and hence the IDM add-on, can be set to work with only ONE of the
    two options, exclusively

	- LeanSwift eLink or

	- ION Document Flows and ION APIs

- In the eLink version, everytime user clicks on download, it downloads all
    the files.
	

Bug Fix 
--------

- Resolved the exception and the errors while trying to download the documents from IDM


Highlight
---------

- IDM is made compatible to latest version of eConnect-Base 6.2.1 & eConnect v22.2.1


Point of Contacts
-----------------

-   <nanthini.muralidaran@leanswift.com>

-   <prabhu.mano@leanswift.com>

-   [deepthi.tadikamalla\@leanswift.com](mailto:deepthi@leanswift.com)

-   <narayanan.gurusamy@leanswift.com>
