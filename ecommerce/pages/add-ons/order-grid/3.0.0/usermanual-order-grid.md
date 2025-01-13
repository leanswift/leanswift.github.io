
# **eConnect User Manual – Order Grid**
![econnect_banner](../../../../../images/banner-econnect-m3.jpg)
## **LeanSwift eConnect for Infor M3 &amp; Magento**


**Product Version**  **3.0.0**

**eConnect version 24.1.0**


# TABLE OF CONTENTS

- [GENERAL INFORMATION](#general-information)
  - [1.1 System Overview](#11-system-overview)
  - [Architecture](#architecture)
    - [eConnect-base v6.4.0](#econnect-base-v500)
    - [Architecture with LeanSwift eLink](#architecture-with-leanswift-elink)
    - [Architecture with ION for multi-tenant Cloud M3](#architecture-with-ion-for-multi-tenant-cloud-m3)
  - [1.2 Points of Contact](#12-points-of-contact)
    - [1.2.1 Information](#121-information)
  - [1.3 Organization of the Manual](#13-organization-of-the-manual)
  - [1.4 Acronyms and Abbreviations](#14-acronyms-and-abbreviations)
  - [2.0 ORDER GRID ADD-ON](#20-order-grid-add-on)
    - [2.0.1 Summary](#201-summary)
    - [2.0.2 Assumptions/Limitations](#202-assumptions-limitations)
  - [2.1 CONFIGURATION](#21-configuration)
    - [2.1.1 Add-on Configuration](#211-add-on-configuration)
    - [2.1.2 Magento Configuration](#212-magento-configuration)
  - [2.2 PROCESS](#22-process)
    - [2.2.1 Grid for 2-attribute-product](#221-grid-for-2-attribute-product)
    - [2.2.2 Grid for 3-attribute-product](#222-grid-for-3-attribute-product)
    - [2.2.3 Backorder](#223-backorder)


## GENERAL INFORMATION

## 1.1 System Overview

- **LeanSwift eConnect for Infor M3** provides a powerful, seamless integration between Magento and Infor M3 ERP. The product consists of a base Magento extension that extends standard Magento functionality and offers several transactions to ensure your eCommerce websites contain up-to-date information from your M3 ERP. There exist a number of optional add-on extensions too for additional functionality

- **LeanSwift eConnect for Infor M3** is available for Magento Open Source and Magento Commerce and for Infor M3 version 7.x and above. It is also compatible with multi-tenant cloud editions of Infor M3 (Cloudsuite).

- **LeanSwift eConnect for Infor M3** employs a layered architecture to allow flexibility in supporting different versions of Magento and Infor M3 and to allow independent upgrades.


[Go to Top](#table-of-contents)
 
## Architecture

With 20.3.0, there is a major technical architectural change in the solution. BODs from ION are now configured to be sent to a REST API in Magento, which in turn sends them to RabbitMQ for storage and processing by eConnect. In the previous versions, ION sends BODs to RabbitMQ directly.

### eConnect-base v6.4.0

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

<kbd>
<img alt ="elink architecture" src="https://github.com/leanswift/leanswift.github.io/blob/master/ecommerce/images/add-ons/order-grid/elink_arch.png"></kbd>



### Architecture with ION for multi-tenant Cloud M3

<kbd><img alt ="ION architecture" src="https://github.com/leanswift/leanswift.github.io/blob/master/ecommerce/images/add-ons/order-grid/ION_Architecture.jpg"></kbd>



The add-ons for LeanSwift eConnect provide extended functionality over the standard features available on eConnect Core.

These add-ons can, if necessary, be modified, and new add-ons can be added to fulfill specific customer requirements.


[Go to Top](#table-of-contents)

**User interface**

During setup, the Magento Admin panel is used to configure which transactions that should be used and how they should function. There is also additional configuration within the Connector to support the transactions.

**Validated versions**

Magento Community 2.4.7

Magento Enterprise 2.4.6

Infor M3 16.x



## 1.2 Points of Contact

### 1.2.1 Information

This document and the software it describes are provided by LeanSwift Solutions Inc. For additional information regarding support, licensing, functionality etc. please contact LeanSwift Solutions Inc via contact form at [http://www.leanswift.com](http://www.leanswift.com/)or email info@leanswift.com

## 1.3 Organization of the Manual

This manual is not intended to cover any standard Magento functionality or user experience. The Magento user experience is customized and slightly different in each eCommerce implementation – though the general workflow is similar.

## 1.4 Acronyms and Abbreviations

ERP – Enterprise Resource Planning

[Go to Top](#table-of-contents)

## 2.0 ORDER GRID ADD-ON

### 2.0.1 Summary

The _Grid_ module extends the standard Magento functionality for displaying products based on selected attributes along with stock and price details and provides full integration to Infor M3 ERP.

Order Grid enables users to add multiple associated products (SKUs) of a Magento configurable product, to cart at once. It also displays attribute values based on configuration on X/Y/Z axis on the frontend for Magento configurable products.

The process remains the same irrespective of whether connection protocol selected in the configuration page is eLink or ION.

### 2.0.2 Assumptions/Limitations

1. Grid is available only for Configurable products.
2. Up to 3 attributes can be configured to display in the frontend.


[Go to Top](#table-of-contents)


## 2.1 CONFIGURATION

### 2.1.1 Add-on Configuration

The Configurable Order Grid setting can be found under LEANSWIFT SOLUTIONS menu.

User can 'Enable' or 'Disable' Grid view in the settings. When enabled, Grid appears for configurable products. When disabled, default Magento view appears to the user.

<kbd>
<img alt ="ordergrid config" src="https://github.com/leanswift/leanswift.github.io/blob/master/ecommerce/images/add-ons/order-grid/order_grid_config.png"></kbd>

**General Configuration:** This section includes



1. **Enable Order Grid:** User can enable or disable Grid
2. **Select X Axis attribute:** Attribute configured here will appear in X axis
3. **Select Y Axis attribute:** Attribute configured here will appear in the Y axis. If there is a third attribute for a product, it appears in Z axis

<kbd>
<img alt ="product attribute" src="https://github.com/leanswift/leanswift.github.io/blob/master/ecommerce/images/add-ons/order-grid/product_attribute.png"></kbd>


4. **Enable Stock:** When set to Yes, Stock is displayed on the Grid
5. **Enable Price:** When set to Yes, the Price is displayed on the Grid

Note: Enable order grid in product level is deprecated (From eConnect 17.2.1 version).


[Go to Top](#table-of-contents)

### 2.1.2 Magento Configuration

In order for attributes to appear in the X/Y axis dropdown, the attributes must be of type 'Dropdown' or 'Visual swatch' or 'Text swatch'

To create attributes, Go to _Stores > Attributes > Products_



New attribute can be created by clicking on 'Add New Attribute'. This will take you to a page similar to this:

<kbd>
<img alt ="new product attribute" src="https://github.com/leanswift/leanswift.github.io/blob/master/ecommerce/images/add-ons/order-grid/new_product_attribute.png"></kbd>

Once attribute is created by choosing type to be 'Dropdown' or 'Visual swatch' or 'Text swatch'

It will appear in the Grid configuration page in the X/Y axis dropdown.

[Go to Top](#table-of-contents)

## 2.2 PROCESS

Once the setup described in the previous section has been completed, the Grid functionality is ready to use from within Magento.

The following sections covers Order grid display in detail page for configurable product


### 2.2.1 Grid for 2-attribute-product

In this example, I have chosen Color in the X axis and Size in the Y axis. I have also enabled Stock and Price to be displayed in the frontend. When the product is loaded in Magento frontend, this is how it would look:

<kbd>
<img alt ="frontend product for ordergrid" src="https://github.com/leanswift/leanswift.github.io/blob/master/ecommerce/images/add-ons/order-grid/frontend_pdt.png"></kbd>

User can switch to display Qty/Price from the dropdown.

[Go to Top](#table-of-contents)


### 2.2.2 Grid for 3-attribute-product

In this example, I have chosen Color in X axis and Size in Y axis. So my 3rd attribute which is 'Material' in this case is displayed in Z axis. User can click the dropdown and switch between different attribute values. I have also enabled Stock and Price to be displayed in the frontend. When the product is loaded in Magento frontend, this is how it would look:

<kbd>
<img alt ="3grid" src="https://github.com/leanswift/leanswift.github.io/blob/master/ecommerce/images/add-ons/order-grid/grid_for_3attribute_pdt.png"></kbd>

[Go to Top](#table-of-contents)

### 2.2.3 Backorder

This is another feature in Magento that allows user to place an order for products that are 'Out of stock'. When this feature is disabled, the grid becomes grayed which means user cannot add products to cart.

This feature can be found _Stores > Configuration > Catalog > Inventory_ Under Product Stock Options.

<kbd>
<img alt ="backorder configuration" src= "https://github.com/leanswift/leanswift.github.io/blob/master/ecommerce/images/add-ons/order-grid/backorder_config.png"></kbd>

The above setting is applied at global level. To control this setting individually for a product, Open a product detail page in the admin, Click on Advanced Inventory

<kbd>
<img alt ="pdt page quantity" src="https://github.com/leanswift/leanswift.github.io/blob/master/ecommerce/images/add-ons/order-grid/product_page_quantity.png"></kbd>

<kbd>
<img alt ="backorder product page" src="https://github.com/leanswift/leanswift.github.io/blob/master/ecommerce/images/add-ons/order-grid/backorder_productpage.png"></kbd>

When backorder is set to 'No Backorders' The product grid looks like this :

<kbd>
<img alt ="product out of stock" src="https://github.com/leanswift/leanswift.github.io/blob/master/ecommerce/images/add-ons/order-grid/pdt_outofstock.png"></kbd>

The grid remains disabled showing a text 'Out of stock'

If Backorder is set to 'Allow Qty below 0', the out of stock products are enabled letting the user add the product to cart. In this case, the field says 'Backorder' and looks like this:

<kbd><img alt ="ION architecture" src="https://github.com/leanswift/leanswift.github.io/blob/master/ecommerce/images/add-ons/order-grid/ConfigPrdt_Backorders.PNG"></kbd>

Note: Stock status must be 'In Stock' in order for Backorder to work.

When user chooses option 'Allow Quantity below 0 and Notify customer', The customer would get a notification message in the cart page when a backorder product is added to cart.

<kbd><img alt ="ION architecture" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/order-grid/ConfigPrdt_NotifyCustomer.PNG"></kbd>

[Go to Top](#table-of-contents)

