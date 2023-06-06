# **eConnect User Manual – Material Plan**
 
![econnect_banner](../../../../../images/banner-econnect-m3.jpg)

**Product Version** **4.1.0**

**eConnect version 20.3.1**

# Table of contents

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
 - [2.0 MATERIAL PLAN ADD-ON](#20-material-plan-add-on)
      - [2.0.1 Summary](#201-summary)
      - [2.0.2 Assumptions/Limitations](#202-assumptionslimitations)
  - [2.1 CONFIGURATION](#21-configuration)
    - [2.1.2 M3 Configuration](#212-m3-configuration)
  - [2.2 PROCESS](#22-process)
    - [2.2.1 ATP in Detail page](#221-atp-in-detail-page)
    - [2.2.2 ATP in Cart page](#222-atp-in-cart-page)
    - [2.2.3 Import ATP](#223-import-atp)


# GENERAL INFORMATION

## 1.1 System Overview
LeanSwift eConnect for Infor M3 provides a seamless integration between Magento and Infor M3 ERP. The product consists of a Magento extension, and a Tomcat based server application that manages the communication with the M3 ERP system.
LeanSwift eConnect for Infor M3 employs a layered architecture to allow more flexibility in supporting different versions of Magento and Infor M3, and to allow independent upgrades. The two components are versioned individually to more easily adapt to different M3- &amp; Magento versions.

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

<kbd><img alt="eLink Architecture" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/elink_Architecture.jpg"></kbd>

### Architecture with ION for multi-tenant Cloud M3

<kbd><img alt="ION Architecture" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/ION_Architecture.jpg"></kbd>

The add-ons for LeanSwift eConnect provide extended functionality over the standard features available on eConnect Core.
These add-ons can, if necessary, be modified, and new add-ons can be added to fulfill specific customer requirements.

[Go to Top](#table-of-contents)

**Transactions**

With eConnect 17.2, the following add-ons are available:
- Sales Rep
- RMA
- Gift Card
- Material Plan
- Multi Warehouse
- Order Grid

These add-ons can if necessary be modified, and new add-ons can be added to fulfill specific customer requirements.

**User interface**

During setup, the Magento Admin panel is used to configure which transactions that should be used and how they should function. There is also additional configuration within the Connector to support the transactions.

**Validated versions**

Magento Community 2.0.0 and up

Magento Enterprise 2.0.0 and up

Infor M3 13.x

## 1.2 Points of Contact

### 1.2.1 Information
This document and the software it describes are provided by LeanSwift Solutions Inc. For additional information regarding support, licensing, functionality etc. please contact LeanSwift Solutions Inc via contact form at http://www.leanswift.com.

## 1.3 Organization of the Manual
This manual is not intended to cover any standard Magento functionality or user experience. The Magento user experience is customized and slightly different in each eCommerce implementation – though the general workflow is similar.

## 1.4 Acronyms and Abbreviations
ERP – Enterprise Resource Planning

B2B – Business to business

B2C – Business to consumer

MP – Material Plan

[Go to Top](#table-of-contents)

# MATERIAL PLAN ADD-ON

### 2.0.1 Summary
The _MP_ module extends the standard Magento Enterprise functionality for displaying stock based on warehouse and stock zone by providing full integration to Infor&#39;s M3 ERP.
Material Plan helps us discover the stock on the next available date. Within eConnect, the following terms have been applied:
- **ATP** – Available to promise. This defines the stock availability on the available to promise date
Depending on the Stock availability, ATP gets updated and is displayed in the frontend

### 2.0.2 Assumptions/Limitations

ATP details are supported only on the cart page for configurable and grouped products. This limitation exists from the beginning.

## 2.1 CONFIGURATION
The configuration for MP is as below

<kbd><img alt ="material plan configuration" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/material-plan/material-plan-configuration.png"></kbd>

**2.1.1 Magento configuration**

The Material Plan setting can be found under LEANSWIFT SOLUTIONS menu
The options enable us to control MP visibility in the frontend. We can either display only on the Detail page or Cart page or both. Users can also control the interval at which real-time calls to M3 can be made.

**General Configuration:** This section includes:

**Order Category:** The order category is usually 251 as that&#39;s the category of a Confirmed PO order.

**Cache hours:** This refers to intervals of hours, the real-time calls must be made to M3

**Detail page:** This section includes:

**Display in Product Detail Page:** This setting lets user choose whether ATP details are to be displayed on the product detail page or not.

**Sync Real Time:** If the user wants real-time calls to be made to M3 every time we browse the product detail page, then we set this to Yes.

**Cart page:** This section includes:

**Display in Cart Page:** This setting lets the user choose whether ATP details are to be displayed in the cart page or not.

**Sync Real Time** : If the user wants real-time calls to be made to M3 every time we browse the product detail page, then we set this to Yes.

**Cron:**

**Cron settings for receiving ATP details from ERP:** Based on the expression, Magento gets updated with ATP from M3.

[Go to Top](#table-of-contents)

### 2.1.2 M3 Configuration
Here in M3, Purchase order is being in created in PPS200.

<kbd><img alt ="m3 order" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/material-plan/pps200.png"></kbd>

Once an order is created, ATP is recalculated. This can be found in MMS080. Enter the item number and press enter. Look for the Next available date and its corresponding stock.

Note: Stock available at date and current date only gets displayed in Magento frontend

<kbd><img alt ="m3 orderline" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/material-plan/pps250.png "></kbd>

## 2.2 PROCESS

Once the setup described in the previous section has been completed, the MP functionality is ready to use from within Magento.
The following sections cover the Material plan displayed on both the detail page and cart page.

### 2.2.1 ATP in Detail page
In Detail page setting: Set Display in Product Detail Page to &#39;Yes&#39; and Sync Real-Time to &#39;Yes&#39;
Now when the product for which order is created in PPS 200 is browsed in the frontend, ATP details along with the date and stock is displayed when the quantity box has hovered with the mouse.

<kbd><img alt ="atp in detail" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/material-plan/atp-in-detail-page.png "></kbd>

If there is no ATP available for that product, this is how it appears:

<kbd><img alt ="atp in detail" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/material-plan/no-atp-in-detail-page.png "></kbd>

### 2.2.2 ATP in Cart page

In Cart page setting: Set Display in Cart Page to &#39;Yes&#39; and Sync Real-Time to &#39;Yes&#39;
Now when the product for which order is created in PPS200 is added to cart in the frontend, ATP details along with the date and stock is displayed when the quantity box is hovered with the mouse in the cart page.

<kbd><img alt ="atp in cart" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/material-plan/atp-in-cart-page.png "></kbd>

ATP BOD looks like this

<kbd><img alt ="atp bod" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/material-plan/atp-bod.png"></kbd>

### 2.2.3 Import ATP

Import ATP option allows to import atp details for existing products.
Fill in the fields and save config, click on Import to import the data

<kbd><img alt ="atp import" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/material-plan/import-ATP.png"></kbd>

**Cache:**

When the cache is set to 0, Real-time calls is made to M3 every time the product is browsed and ATP details are updated.
When the cache is set to a particular number, A call to M3 is made only after the specified number of hours.

[Go to Top](#table-of-contents)
