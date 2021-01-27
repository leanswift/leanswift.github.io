# **Eonnect User Manual – Material Plan**
![econnect_banner](../../../../images/banner-econnect-m3.jpg)
## **LeanSwift eConnect for Infor M3 &amp; Magento** 


**Product Version**  **4.1.0**

** eConnect version 20.3.0**


**TABLE OF CONTENTS**

- [GENERAL INFORMATION](#general-information)
  - [1.1 System Overview](#11-system-overview)
  - [Architecture](#architecture)
    - [eConnect-base v5.0.0](#econnect-base-v500)
    - [Architecture with LeanSwift eLink](#architecture-with-leanswift-elink)
    - [Architecture with ION for multi-tenant Cloud M3](#architecture-with-ion-for-multi-tenant-cloud-m3)
  - [1.2 Points of Contact](#12-points-of-contact)
    - [1.2.1 Information](#121-information)
  - [1.3 Organization of the Manual](#13-organization-of-the-manual)
  - [1.4 Acronyms and Abbreviations](#14-acronyms-and-abbreviations)
  - [MATERIAL PLAN ADD-ON](#material-plan-add-on)
    - [2.0.1 Summary](#201-summary)
    - [2.0.2 Assumptions/Limitations](#202-assumptionslimitations)
  - [2.1 CONFIGURATION](#21-configuration)
    - [2.1.1 Magento Configuration-ION](#211-magento-configuration-ion)
    - [2.1.2 M3 Configuration](#212-m3-configuration)
  - [2.2 PROCESS](#22-process)
    - [2.2.1 ATP in Detail page](#221-atp-in-detail-page)
    - [2.2.2 ATP in Cart page](#222-atp-in-cart-page)




# GENERAL INFORMATION

## 1.1 System Overview

 **LeanSwift eConnect for Infor M3**  provides a powerful, seamless integration between Magento and Infor M3 ERP. The product consists of a base Magento extension that extends standard Magento functionality and offers several transactions to ensure your eCommerce websites contain up-to-date information from your M3 ERP. There exist a number of optional add-on extensions too for additional functionality

 **LeanSwift eConnect for Infor M3**  is available for Magento Open Source and Magento Commerce and for Infor M3 version 7.x and above. It is also compatible with multi-tenant cloud editions of Infor M3 (Cloudsuite).

 **LeanSwift eConnect for Infor M3** employs a layered architecture to allow flexibility in supporting different versions of Magento and Infor M3 and to allow independent upgrades.
 
 [Go to Top](#table-of-contents)

## Architecture


With 20.3.0, there is a major technical architectural change in the solution. BODs from ION are now configured to be sent to a REST API in Magento, which in turn sends them to RabbitMQ for storage and processing by eConnect. In the previous versions, ION sends BODs to RabbitMQ directly.

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


### Architecture with LeanSwift eLink



![elink Architecture](https://github.com/leanswift/leanswift.github.io/blob/ECNT-1734/ecommerce/images/add-ons/material-plan/architecture-with-leanSwift-eLink.jpg)



### Architecture with ION for multi-tenant Cloud M3



![ION Architecture](https://github.com/leanswift/leanswift.github.io/blob/ECNT-1734/ecommerce/images/add-ons/material-plan/architecture-with-ION-for-multi-tenant-cloud-M3.jpg)

The add-ons for LeanSwift eConnect provide extended functionality over the standard features available on eConnect Core.

These add-ons can, if necessary, be modified, and new add-ons can be added to fulfill specific customer requirements.

[Go to Top](#table-of-contents)

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

[Go to Top](#table-of-contents)


## MATERIAL PLAN ADD-ON

### 2.0.1 Summary

The _MP_ module extends the standard Magento functionality for displaying stock based on warehouse and stock zone by providing full integration to Infor M3 ERP.

Material Plan helps us discover the stock on next available date. Within eConnect the following terms have been applied:

- **ATP** – Available to promise. This defines the stock availability on the available to promise date

Depending on the Stock availability, ATP gets updated and is displayed in frontend



### 2.0.2 Assumptions/Limitations

ATP details are supported only in the cart page for configurable and grouped products.

[Go to Top](#table-of-contents)

## 2.1 CONFIGURATION

    
### 2.1.1 Magento Configuration-ION

The Material Plan setting can be found under LEANSWIFT SOLUTIONS menu

![MagentoConfig](https://github.com/leanswift/leanswift.github.io/blob/ECNT-1734/ecommerce/images/add-ons/material-plan/material-plan-configuration.png)

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

![Import_ATP](https://github.com/leanswift/leanswift.github.io/blob/ECNT-1734/ecommerce/images/add-ons/material-plan/import-ATP.png)


Number of Actions: This restricts the number of ATP records imported from M3.
Query: Any conditions can be entered here in the form of query (IES format)
Once user clicks on Import button, ATP configuration will be imported from M3.

[Go to Top](#table-of-contents)
    
### 2.1.2 M3 Configuration

Here in M3, Purchase order is being created in PPS200.

![M3_PurchaseOrder](https://github.com/leanswift/leanswift.github.io/blob/ECNT-1734/ecommerce/images/add-ons/material-plan/pps200.png)

To confirm the created Purchase order, Go to PPS250 and filter by your Po no. Then Confirm your order where the status moves from &#39;15&#39; to &#39;35&#39;.

![M3_ConfirmOrder](https://github.com/leanswift/leanswift.github.io/blob/ECNT-1734/ecommerce/images/add-ons/material-plan/pps250.png)

Once order is created and Confirmed, ATP is recalculated. This can be found in MMS080. Enter the item number and press enter. Look for the order whose status is 35 and latest Next available date( **PI dt** ) and its corresponding stock. **AvailableToPromiseCumulative** field from the BOD will be displayed as ATP value in the frontend.

Note: Stock available at date =\&gt; current date only gets displayed in Magento frontend

![ATP_BOD](https://github.com/leanswift/leanswift.github.io/blob/ECNT-1734/ecommerce/images/add-ons/material-plan/atp-bod.png)

![M3_MP](https://github.com/leanswift/leanswift.github.io/blob/ECNT-1734/ecommerce/images/add-ons/material-plan/mms080.png)

[Go to Top](#table-of-contents)

## 2.2 PROCESS

Once the setup described in the previous section has been completed, the MP functionality is ready to use from within Magento.

The following sections cover Material plan display in both detail page and cart page.

### 2.2.1 ATP in Detail page

In Detail page setting: Set Display in Product Detail Page to &#39;Yes&#39;.

Now when the product for which order is created in PPS 200 is browsed in the frontend, ATP details along with date and stock is displayed when the quantity box is hovered with the mouse.

![ATP_DetailPAGE](https://github.com/leanswift/leanswift.github.io/blob/ECNT-1734/ecommerce/images/add-ons/material-plan/atp-in-detail-page.png)

If there is no ATP available for that product, this is how it appears:

![NoATP_DetailPage](https://github.com/leanswift/leanswift.github.io/blob/ECNT-1734/ecommerce/images/add-ons/material-plan/no-atp-in-detail-page.png)

[Go to Top](#table-of-contents)

### 2.2.2 ATP in Cart page

In Cart page setting: Set Display in Cart Page to &#39;Yes&#39;.

Now when the product for which order is created in PPS200 is added to cart in the frontend, ATP details along with date and stock is displayed in the cart page.

![ATP_CartPage](https://github.com/leanswift/leanswift.github.io/blob/ECNT-1734/ecommerce/images/add-ons/material-plan/atp-in-cart-page.png)

[Go to Top](#table-of-contents)

