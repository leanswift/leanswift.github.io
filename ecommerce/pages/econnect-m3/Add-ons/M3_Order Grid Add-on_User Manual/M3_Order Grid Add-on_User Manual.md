![](RackMultipart20210127-4-1nc7bvj_html_bfb8e04537ed5a6.png)

**# USER MANUAL**

## **LeanSwift eConnect for Infor M3 &amp; Magento**

**Order Grid Add-on**

**Product Version**  **2.5.0**

for eConnect version 20.3.0

**ECONNECT USER MANUAL – ORDER GRID ADD-ON**

**TABLE OF CONTENTS**


[**GENERAL INFORMATION**]

[System Overview](#system-overview)

[Architecture](#architecture)

[Architecture with LeanSwift eLink](#architecture-with-leanSwift-eLink)

[Architecture with ION for multi-tenant Cloud M3](#architecture-with-ion-for-multi-tenant-cloud-m3)

[Points of Contact](#points-of-contact)

[Information](#information)

[Organization of the Manual](#organization-of-the-manual)

[Acronyms and Abbreviations](#acronyms-and-abbreviations)

[ORDER GRID ADD-ON](#order-grid-add-on)

[Summary](#summary)

[Assumptions/Limitations](#assumptions-limitations)

[CONFIGURATION](#configuration)

[Add-on Configuration](#add-on-configuration)

[Magento Configuration](#magento-configuration)

[PROCESS](#process)

[Grid for 2-attribute-product](#grid-for-2-attribute-product)

[Grid for 3-attribute-product](#grid-for-3-attribute-product)

[Backorder](#backorder)


# GENERAL INFORMATION

## 1.1 System Overview

_ **LeanSwift eConnect for Infor M3** _ provides a powerful, seamless integration between Magento and Infor M3 ERP. The product consists of a base Magento extension that extends standard Magento functionality and offers several transactions to ensure your eCommerce websites contain up-to-date information from your M3 ERP. There exist a number of optional add-on extensions too for additional functionality

_ **LeanSwift eConnect for Infor M3** _ is available for Magento Open Source and Magento Commerce and for Infor M3 version 7.x and above. It is also compatible with multi-tenant cloud editions of Infor M3 (Cloudsuite).

_ **LeanSwift eConnect for Infor M3** _ employs a layered architecture to allow flexibility in supporting different versions of Magento and Infor M3 and to allow independent upgrades.

### Architecture


With 20.1.0, the part of eConnect functionality dealing with connectivity to eLink and Infor OS and data processing has been moved out of eConnect extension into a new extension named

**eConnect-base**.

From 20.1.0 onward, eConnect will require the eConnect-base extension to function. eConnect 20.1.0 is compatible with eConnect-base 2.0.0. Similarly IDM 3.0.0 requires the eConnect-base extension to function and is compatible with eConnect-base 2.0.0.

For configuration details for eConnect-base, please refer to configuration section in [**LeanSwift eConnect for M3 20.1.0\_User Manual\_Part 1.docx**](https://docs.google.com/document/d/1WdRaZPywCGHdzo0oyYU5xZ6flvYoPPqQ/edit#heading=h.p1tjc9105a9h)

### eConnect-base v2.0.0

- It provides the connectivity to eLink and/or Infor systems with the use of a generic function which decides whether to call the eLink / ION APIs based on the M3 Connection Protocol chosen in the backend
- Acts as the communication layer for RabbitMQ Message consumption
- Acts as a core module for
  - eConnect
  - IDM
  - Supplier Portal
- eConnect add-ons depend on both eConnect-base and eConnect. eConnect and its Add-ons works only with eConnect-base configured

- IDM can now work without eConnect

###

#### Architecture with LeanSwift eLink

###

![](RackMultipart20210127-4-1nc7bvj_html_aa3e621d5e06587e.jpg)

###

#### Architecture with ION for multi-tenant Cloud M3

###

![](RackMultipart20210127-4-1nc7bvj_html_1a380fb028ca706a.jpg)

###

The add-ons for LeanSwift eConnect provide extended functionality over the standard features available on eConnect Core.

These add-ons can, if necessary, be modified, and new add-ons can be added to fulfill specific customer requirements.

**User interface**

During setup, the Magento Admin panel is used to configure which transactions that should be used and how they should function. There is also additional configuration within the Connector to support the transactions.

**Validated versions**

Magento Community 2.3.1

Magento Enterprise 2.3.1

Infor M3 13.x

## 1.2 Points of Contact

### 1.2.1 Information

This document and the software it describes are provided by LeanSwift Solutions Inc. For additional information regarding support, licensing, functionality etc. please contact LeanSwift Solutions Inc via contact form at [http://www.leanswift.com](http://www.leanswift.com/)or email info@leanswift.com

## 1.3 Organization of the Manual

This manual is not intended to cover any standard Magento functionality or user experience. The Magento user experience is customized and slightly different in each eCommerce implementation – though the general workflow is similar.

## 1.4 Acronyms and Abbreviations

ERP – Enterprise Resource Planning

1.
# ORDER GRID ADD-ON

### 2.0.1 Summary

The _Grid_ module extends the standard Magento functionality for displaying products based on selected attributes along with stock and price details and provides full integration to Infor M3 ERP.

Order Grid enables users to add multiple associated products (SKUs) of a Magento configurable product, to cart at once. It also displays attribute values based on configuration on X/Y/Z axis on the frontend for Magento configurable products.

The process remains the same irrespective of whether connection protocol selected in the configuration page is eLink or ION.

### 2.0.2 Assumptions/Limitations

1. Grid is available only for Configurable products.
2. Up to 3 attributes can be configured to display in the frontend.

## 2.1 CONFIGURATION

### 2.1.1 Add-on Configuration

The Configurable Order Grid setting can be found under LEANSWIFT SOLUTIONS menu.

User can &#39;Enable&#39; or &#39;Disable&#39; Grid view in the settings. When enabled, Grid appears for configurable products. When disabled, default Magento view appears to the user.

![](RackMultipart20210127-4-1nc7bvj_html_95342dc55262fce7.png)

**General Configuration:** This section includes

1. **Enable Order Grid:** User can enable or disable Grid
2. **Select X Axis attribute:** Attribute configured here will appear in X axis
3. **Select Y Axis attribute:** Attribute configured here will appear in the Y axis. If there is a third attribute for a product, it appears in Z axis
4. **Enable Stock:** When set to Yes, Stock is displayed on the Grid
5. **Enable Price:** When set to Yes, the Price is displayed on the Grid

Note: Enable order grid in product level is deprecated (From eConnect 17.2.1 version).

### 2.1.2 Magento Configuration

In order for attributes to appear in the X/Y axis dropdown, the attributes must be of type &#39;Dropdown&#39; or &#39;Visual swatch&#39; or &#39;Text swatch&#39;

To create attributes, Go to _Stores \&gt; Attributes \&gt; Products_

![](RackMultipart20210127-4-1nc7bvj_html_8c1675264f2da77e.png)

New attribute can be created by clicking on &#39;Add New Attribute&#39;. This will take you to a page similar to this:

![](RackMultipart20210127-4-1nc7bvj_html_1895d4c1aed16830.png)

Once attribute is created by choosing type to be &#39;Dropdown&#39; or &#39;Visual swatch&#39; or &#39;Text swatch&#39;

It will appear in the Grid configuration page in the X/Y axis dropdown.

## 2.2 PROCESS

Once the setup described in the previous section has been completed, the Grid functionality is ready to use from within Magento.

The following sections covers Order grid display in detail page for configurable product

### 2.2.1 Grid for 2-attribute-product

In this example, I have chosen Color in the X axis and Size in the Y axis. I have also enabled Stock and Price to be displayed in the frontend. When the product is loaded in Magento frontend, this is how it would look:

![](RackMultipart20210127-4-1nc7bvj_html_500fcbae0c4e12ca.png)

User can switch to display Qty/Price from the dropdown.

### 2.2.2 Grid for 3-attribute-product

In this example, I have chosen Color in X axis and Size in Y axis. So my 3rd attribute which is &#39;Material&#39; in this case is displayed in Z axis. User can click the dropdown and switch between different attribute values. I have also enabled Stock and Price to be displayed in the frontend. When the product is loaded in Magento frontend, this is how it would look:

![](RackMultipart20210127-4-1nc7bvj_html_3e0fcea738f936d.png)

### 2.2.3 Backorder

This is another feature in Magento that allows user to place an order for products that are &#39;Out of stock&#39;. When this feature is disabled, the grid becomes grayed which means user cannot add products to cart.

This feature can be found _Stores \&gt; Configuration \&gt; Catalog\&gt; Inventory_ Under Product Stock Options.

![](RackMultipart20210127-4-1nc7bvj_html_37bcfdcf146ede7e.png)

The above setting is applied at global level. To control this setting individually for a product, Open a product detail page in the admin, Click on Advanced Inventory

![](RackMultipart20210127-4-1nc7bvj_html_7fb4b7562e2f36f7.png)

![](RackMultipart20210127-4-1nc7bvj_html_99f2eec2a1b4efba.png)

When backorder is set to &#39;No Backorders&#39; The product grid looks like this :

![](RackMultipart20210127-4-1nc7bvj_html_bc18533b0d9e4528.png)

The grid remains disabled showing a text &#39;Out of stock&#39;

If Backorder is set to &#39;Allow Qty below 0&#39;, the out of stock products are enabled letting the user add the product to cart. In this case, the field says &#39;Backorder&#39; and looks like this:

![](RackMultipart20210127-4-1nc7bvj_html_fb65703b49e2abcb.png)

Note: Stock status must be &#39;In Stock&#39; in order for Backorder to work.

When user chooses option &#39;Allow Quantity below 0 and Notify customer&#39;, The customer would get a notification message in the cart page when a backorder product is added to cart.

![](RackMultipart20210127-4-1nc7bvj_html_cf9b6cc28755c09.png)

**User Manual Page** 5