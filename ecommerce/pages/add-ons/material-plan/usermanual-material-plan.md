
# USER MANUAL

###
_### **LeanSwift eConnect for Infor M3 &amp; Magento** _

**Material Plan Add-on**

**Product Version**  **4.1.**** 0**

_for eConnect version 20.3.0_

**ECONNECT USER MANUAL – Material Plan**

**TABLE OF CONTENTS**

Page #

[1.0GENERAL INFORMATION 3](#_Toc62629713)

[1.1System Overview 3](#_Toc62629714)

[Architecture 3](#_Toc62629715)

[eConnect-base v5.0.0 3](#_Toc62629716)

[Architecture with LeanSwift eLink 4](#_Toc62629717)

[Architecture with ION for multi-tenant Cloud M3 4](#_Toc62629718)

[1.2Points of Contact 5](#_Toc62629719)

[1.2.1Information 5](#_Toc62629720)

[1.3Organization of the Manual 5](#_Toc62629721)

[1.4Acronyms and Abbreviations 5](#_Toc62629722)

[2.0MATERIAL PLAN ADD-ON 6](#_Toc62629723)

[2.0.1Summary 6](#_Toc62629724)

[2.0.2Assumptions/Limitations 6](#_Toc62629725)

[2.1CONFIGURATION 7](#_Toc62629726)

[2.1.1 Magento Configuration-ION 7](#_Toc62629727)

[2.1.2 M3 Configuration 9](#_Toc62629728)

[2.2PROCESS 12](#_Toc62629729)

[2.2.1ATP in Detail page 12](#_Toc62629730)

[2.2.2ATP in Cart page 13](#_Toc62629731)

1.
# GENERAL INFORMATION

## 1.1 System Overview

_ **LeanSwift eConnect for Infor M3** _ provides a powerful, seamless integration between Magento and Infor M3 ERP. The product consists of a base Magento extension that extends standard Magento functionality and offers several transactions to ensure your eCommerce websites contain up-to-date information from your M3 ERP. There exist a number of optional add-on extensions too for additional functionality

_ **LeanSwift eConnect for Infor M3** _ is available for Magento Open Source and Magento Commerce and for Infor M3 version 7.x and above. It is also compatible with multi-tenant cloud editions of Infor M3 (Cloudsuite).

_ **LeanSwift eConnect for Infor M3** _ employs a layered architecture to allow flexibility in supporting different versions of Magento and Infor M3 and to allow independent upgrades.

## Architecture

#

With 20.3.0, BODs will be sent to Magento, which inturns sends them to RabbitMQ unlike the previous version which sends them to rabbitmq directly.

### eConnect-base v5.0.0

- It provides the connectivity to eLink and/or Infor systems with the use of a generic function which decides whether to call the eLink / ION APIs based on the M3 Connection Protocol chosen in the backend
- Acts as the communication layer for RabbitMQ Message consumption
- Acts as a core module for following LeanSwift Magento Extensions
  - eConnect
  - IDM
  - Supplier Portal
- eConnect add-ons depend on both eConnect-base and eConnect. eConnect and its Add-ons works only with eConnect-base configured

- IDM can now work without eConnect

The new version will coexist with the older version of eConnect which uses LeanSwift eLink and all new installations of eConnect have the ability to choose the connection protocol to M3, that is, either eLink or ION.

###

### Architecture with LeanSwift eLink

###

![](RackMultipart20210127-4-7gt9qf_html_aa3e621d5e06587e.jpg)

###

### Architecture with ION for multi-tenant Cloud M3

###

![](RackMultipart20210127-4-7gt9qf_html_9a02ad5752d954ce.jpg)

The add-ons for LeanSwift eConnect provide extended functionality over the standard features available on eConnect Core.

These add-ons can, if necessary, be modified, and new add-ons can be added to fulfill specific customer requirements.

**User interface**

During setup, the Magento Admin panel is used to configure which transactions that should be used and how they should function. There is also additional configuration within the Connector to support the transactions.

**Validated versions**

Magento Community 2.4.1

Magento Enterprise 2.4.1

Infor M3 16.x

## 1.2 Points of Contact

### 1.2.1 Information

This document and the software it describes are provided by LeanSwift Solutions Inc. For additional information regarding support, licensing, functionality etc. please contact LeanSwift Solutions Inc via contact form at [http://www.leanswift.com](http://www.leanswift.com/)or email info@leanswift.com

## 1.3 Organization of the Manual

This manual is not intended to cover any standard Magento functionality or user experience. The Magento user experience is customized and slightly different in each eCommerce implementation – though the general workflow is similar.

## 1.4 Acronyms and Abbreviations

ERP – Enterprise Resource Planning

MP – Material Plan

BOD – Business Object Document

1.
# MATERIAL PLAN ADD-ON

### 2.0.1 Summary

The _MP_ module extends the standard Magento functionality for displaying stock based on warehouse and stock zone by providing full integration to Infor M3 ERP.

Material Plan helps us discover the stock on next available date. Within eConnect the following terms have been applied:

- **ATP** – Available to promise. This defines the stock availability on the available to promise date

Depending on the Stock availability, ATP gets updated and is displayed in frontend

###


### 2.0.2 Assumptions/Limitations

ATP details are supported only in the cart page for configurable and grouped products.

## 2.1 CONFIGURATION

    1.
### 2.1.1 Magento Configuration-ION

The Material Plan setting can be found under LEANSWIFT SOLUTIONS menu

![](RackMultipart20210127-4-7gt9qf_html_65e9cf2e3107b8e4.png)

The options enables us to control MP visibility in the frontend. We can either choose to display only on Detail page or Cart page or both. User can also control the interval at which real time calls to M3 can be made.

**General Configuration:**

**Order Category:** The order category is usually 251 as that is the category of a Confirmed PO order.

**Detail page:**

**Display in Product Detail Page:** This setting lets user choose whether ATP details are to be displayed in product detail page or not.

**Cart page:**

**Display in Cart Page:** This setting lets user choose whether ATP details are to be displayed in cart page or not.

Sync Real Time and Cache hours option are removed in ION.

Once the BODs for ATP are received, the ATP will be updated and will be displayed in the frontend.

We also have an additional functionality which is importing ATP config using import option unlike the cron option in elink version

![](RackMultipart20210127-4-7gt9qf_html_73488cfad6cd04f.png)

.

Number of Actions: This restricts the number of ATP records imported from M3.

Query: Any conditions can be entered here in the form of query (IES format)

Once user clicks on Import button, ATP configuration will be imported from M3.

    1.
### 2.1.2 M3 Configuration

Here in M3, Purchase order is being created in PPS200.

![](RackMultipart20210127-4-7gt9qf_html_625921bf54c15622.png)

To confirm the created Purchase order, Go to PPS250 and filter by your Po no. Then Confirm your order where the status moves from &#39;15&#39; to &#39;35&#39;.

![](RackMultipart20210127-4-7gt9qf_html_76c8e5cb09834fb6.png)

Once order is created and Confirmed, ATP is recalculated. This can be found in MMS080. Enter the item number and press enter. Look for the order whose status is 35 and latest Next available date( **PI dt** ) and its corresponding stock. **AvailableToPromiseCumulative** field from the BOD will be displayed as ATP value in the frontend.

Note: Stock available at date =\&gt; current date only gets displayed in Magento frontend

![](RackMultipart20210127-4-7gt9qf_html_5aed36a0ef2a4cc7.png)

![](RackMultipart20210127-4-7gt9qf_html_eab60c5f4a2f5dde.png)

## 2.2 PROCESS

Once the setup described in the previous section has been completed, the MP functionality is ready to use from within Magento.

The following sections cover Material plan display in both detail page and cart page.

### 2.2.1 ATP in Detail page

In Detail page setting: Set Display in Product Detail Page to &#39;Yes&#39;.

Now when the product for which order is created in PPS 200 is browsed in the frontend, ATP details along with date and stock is displayed when the quantity box is hovered with the mouse.

![](RackMultipart20210127-4-7gt9qf_html_76bde09c2cc3c411.png)

If there is no ATP available for that product, this is how it appears:

![](RackMultipart20210127-4-7gt9qf_html_5904440dc89ba507.png)

### 2.2.2 ATP in Cart page

In Cart page setting: Set Display in Cart Page to &#39;Yes&#39;.

Now when the product for which order is created in PPS200 is added to cart in the frontend, ATP details along with date and stock is displayed in the cart page.

![](RackMultipart20210127-4-7gt9qf_html_2dd8e9f9d22279cf.png)

**User Manual Page 6**
