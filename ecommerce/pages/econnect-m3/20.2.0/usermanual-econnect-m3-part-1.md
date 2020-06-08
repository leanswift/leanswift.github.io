![](RackMultipart20200605-4-1903pio_html_f5f7f63ec5d1a8b9.gif)

![](RackMultipart20200605-4-1903pio_html_5749ee4c7fdc9cd3.png)

# **USER MANUAL**

## _ **LeanSwift eConnect** _

_ **for Infor M3 &amp; Magento** _

**Part I – Configuration**

#

**Product Version 20.1.0**

**ECONNECT 20.1.0 USER MANUAL**

# TABLE OF CONTENTS

Page #

Contents

_**[TABLE OF CONTENTS](#_heading=h.30j0zll) 2**_

_**[GENERAL INFORMATION](#_heading=h.1fob9te) 5**_

_**[System Overview](#_heading=h.2et92p0) 5**_

**[Architecture](#_heading=h.u6fhnb7ross2) 5**

**[Architecture with LeanSwift eLink](#_heading=h.pedoav3dbcp) 6**

**[Architecture with ION for multi-tenant Cloud M3](#_heading=h.p4kahfgfd2ic) 6**

**[eConnect-base v2.0.0](#_heading=h.ql61v97hrxzk) 7**

**[Transactions](#_heading=h.eu6px4uccu0h) 7**

**[User Interface](#_heading=h.3dy6vkm) 7**

_**[Points of Contact](#_heading=h.1t3h5sf) 8**_

**[Organization of the Manual](#_heading=h.ak657x6x7zbk) 8**

_**[Acronyms and Abbreviations](#_heading=h.k095cvid3lmw) 8**_

_**[CONFIGURATION](#_heading=h.2s8eyo1) 9**_

_**[Magento Configuration](#_heading=h.26in1rg) 9**_

_**[System Menu](#_heading=h.35nkun2) 10**_

_**[Configuration](#_heading=h.1ksv4uv) 10**_

_**[Configuration/LeanSwift](#_heading=h.2jxsxqh) 12**_

_**[Configuration/LeanSwift/eConnect](#_heading=h.auxpnwsznva1) 13**_

_**[eConnect-base](#_heading=h.p1tjc9105a9h) 14**_

**[Service Configuration](#_heading=h.4mgr12u3td8o) 15**

**[M3 Connection Protocol](#_heading=h.p3jk2edk1tw4) 15**

**[Basic Data Configuration (M3 connection protocol - ION)](#_heading=h.shswq1sjeway) 16**

**[Company](#_heading=h.x0swopsmyutp) 16**

**[Division](#_heading=h.h3m72jgjobd0) 16**

**[Authentication](#_heading=h.suwbbrhjuxew) 16**

_**[eConnect-General](#_heading=h.3j2qqm3) 17**_

_**[General Configuration](#_heading=h.70b4254wl9go) 17**_

**[Use M3 order history](#_heading=h.qsh70q) 17**

**[Display Invoice](#_heading=h.3as4poj) 17**

**[Debug/log data](#_heading=h.1pxezwc) 18**

_**[eConnect-ION](#_heading=h.49x2ik5) 19**_

_**[Basic Data Configuration](#_heading=h.147n2zr) 19**_

**[Facility](#_heading=h.ihv636) 19**

**[Warehouse](#_heading=h.32hioqz) 19**

**[Price Code](#_heading=h.9e7gchtvqi2o) 19**

**[Currency code](#_heading=h.41mghml) 19**

**[Order Type](#_heading=h.2grqrue) 19**

_**[Shipping Method](#_heading=h.3fwokq0) 20**_

_**[Manual Sync Configuration](#_heading=h.yc3m5w4eql0k) 21**_

_**[Customer General Configuration](#_heading=h.3tbugp1) 21**_

**[Enable Registration](#_heading=h.28h4qwu) 21**

**[Create New Customer](#_heading=h.nmf14n) 23**

_**[Product Addition/ Synchronization](#_heading=h.1v1yuxt) 25**_

_**[Product attribute mapping](#_heading=h.4f1mdlm) 26**_

_**[Product Synchronization - AttributeSet Mapping](#_heading=h.19c6y18) 28**_

_**[Product Synchronization - Category Mapping](#_heading=h.2u6wntf) 29**_

_**[Customer Addition/ Synchronization](#_heading=h.37m2jsg) 30**_

**[Enable](#_heading=h.1mrcu09) 30**

**[Enable Customer sync](#_heading=h.46r0co2) 31**

**[Enable Customer Addition](#_heading=h.2lwamvv) 31**

**[Customer Group Id](#_heading=h.111kx3o) 31**

**[Customer Master Mapping](#_heading=h.206ipza) 31**

**[Customer Address Mapping](#_heading=h.4k668n3) 31**

_**[Sales](#_heading=h.2zbgiuw) 32**_

**[Enable order comments](#_heading=h.1egqt2p) 32**

**[Allow Item Price](#_heading=h.3ygebqi) 32**

**[Capture Payment Online](#_heading=h.sqyw64) 32**

_**[Order Charges](#_heading=h.3cqmetx) 33**_

**[Shipping/Freight Fee Charge Type](#_heading=h.1rvwp1q) 34**

**[Gift Wrap Transfer](#_heading=h.4bvk7pj) 36**

_**[Payments](#_heading=h.2r0uhxc) 38**_

**[Re-authorization Amount (Credit Cards)](#_heading=h.1664s55) 38**

**[Payment Provider](#_heading=h.3q5sasy) 38**

**[Invoice Fee Charge Type](#_heading=h.25b2l0r) 38**

**[Invoice Fees](#_heading=h.kgcv8k) 39**

_**[Price Synchronization](#_heading=h.34g0dwd) 40**_

**[Enable](#_heading=h.1jlao46) 40**

**[Enable in Admin](#_heading=h.43ky6rz) 40**

_**[Inventory Synchronization](#_heading=h.2iq8gzs) 40**_

**[ERP Inventory Attribute](#_heading=h.xvir7l) 40**

_**[Cron Settings](#_heading=h.3hv69ve) 42**_

_**[Version Info](#_heading=h.1x0gk37) 42**_

_**[MAGENTO STANDARD FUNCTIONALITY](#_heading=h.2w5ecyt) 44**_

_**[Exit System](#_heading=h.3vac5uf) 44**_

# ![](RackMultipart20200605-4-1903pio_html_ba25a3aa14ac570c.png) GENERAL INFORMATION

# System Overview

_ **LeanSwift eConnect for Infor M3** _ provides a powerful, seamless integration between Magento and Infor M3 ERP. The product consists of a base Magento extension that extends standard Magento functionality and offers several transactions to ensure your eCommerce websites contain up-to-date information from your M3 ERP. There exist a number of optional add-on extensions too for additional functionality

_ **LeanSwift eConnect for Infor M3** _ is available for Magento Open Source and Magento Commerce and for Infor M3 version 7.x and above. It is also compatible with multi-tenant cloud editions of Infor M3 (Cloudsuite).

_ **LeanSwift eConnect for Infor M3** _ employs a layered architecture to allow flexibility in supporting different versions of Magento and Infor M3 and to allow independent upgrades.

## Architecture

With 20.1.0, the part of eConnect functionality dealing with connectivity to Infor OS and

data processing has been moved out of eConnect extension into a new extension named

**eConnect-base**.

From 20.1.0 onward, eConnect will require the eConnect-base extension to function.

eConnect 20.1.0 is compatible with eConnect-base 2.0.0.

<kbd><img alt="Architecture with elink" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/architecture.png"></kbd>



### Architecture with ION for multi-tenant Cloud M3



<kbd><img alt="Architecture with elink" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/architecture-with-ebase.png"></kbd>



### eConnect-base v2.0.0

- It provides the connectivity to eLink and/or Infor systems with the use of a generic function which decides whether to call the eLink / ION APIs based on the M3 Connection Protocol chosen in the backend
- Acts as the communication layer for RabbitMQ Message consumption
- Acts as a core module for following LeanSwift Magento Extensions
  - eConnect
  - IDM
  - Supplier Portal
- eConnect add-ons depend on both eConnect-base and eConnect. eConnect and its Add-ons works only with eConnect-base configured

- IDM can now work without eConnect

### Transactions

eConnect 20.1.0 includes the following set of standard transactions like its previous versions:

- Product Addition
- Product Information Sync
- Price Sync (Base &amp; Customer prices)
- Inventory Sync
- Customer Registration
- Customer Addition
- Customer Information Sync
- Customer Address Sync
- Order Creation
- Order Information Sync
- Shipment Sync
- Invoice Sync
- Order History
- Invoice History
- BOD Mapping
- Initial Load / Import

- Manual Sync for Customer
- Manual Sync for Product
- Manual Sync for Order

These transactions can, if necessary, be modified and new transactions can be added to fulfill specific customer requirements.

### User Interface


During setup, the Magento Admin panel is used to configure which transactions should be used and how they should function.There is also additional background configuration within the Connector.

**Validated versions**

- Magento Commerce 2.3.4
- Magento Open Source 2.3.4
- Infor M3 16.1
- LeanSwift eLink 7.6.3
- RabbitMQ 3.8.3
- Infor ION Grid 12.0.2.0.20180308-135417.2
- ION Desk 12.0.0

# Points of Contact

This document and the software it describes are provided by LeanSwift Solutions Inc. For additional information regarding support, licensing, functionality etc. please contact LeanSwift Solutions Inc. via contact form at [http://www.leanswift.com](http://www.leanswift.com/)or email info@leanswift.com

# Organization of the Manual

This manual is not intended to cover any standard Magento functionality or user experience. The Magento user experience is customized and slightly different in each eCommerce implementation, though the general workflow is similar.

This manual describes the configuration of LeanSwift eConnect for Infor M3 with ION. For a detailed description of the standard transactions, please refer to **Part II of the User Manual - LeanSwift eConnect for M3**  **20****.1.0\_User Manual\_Part 2**.

_ **Section 2** _ in this manual includes the configuration required within LeanSwift eConnect Magento extension via the Magento Admin panel.

# Acronyms and Abbreviations

ERP – Enterprise Resource Planning

B2B – Business to Business

B2C – Business to Consumer

RMA – Return Materials Authorization

# ![](RackMultipart20200605-4-1903pio_html_8a644972a31e83d4.png) CONFIGURATION

# Magento Configuration

To support the use of LeanSwift eConnect for Infor M3, configuration is required within Magento, in LeanSwift eLink, in ION and also within the M3 ERP system. This section covers the configuration within _Magento_.

Log in to Magento Admin Panel using the URL provided to you and the applicable user credentials.

<kbd><img alt="Magento" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/magento.png"></kbd>

# System Menu

## Configuration

- To access the LeanSwift Configuration, click the **Leanswift** tab, and select the **Configuration** option under **econnect-ION**.

<kbd><img alt="Configuration" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/configuration.png"></kbd>

Also pay attention to which configuration scope you&#39;re working under.

<kbd><img alt="Configuration-scope" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/configuration-scope.png"></kbd>

For further information about _Configuration scope_ in Magento, please refer to the following article:

[http://www.magentocommerce.com/knowledge-base/entry/understanding-store-scopes](http://www.magentocommerce.com/knowledge-base/entry/understanding-store-scopes)

## Configuration/LeanSwift

Navigate to the **LeanSwift Solutions** sub-menu down in the left-hand side configuration menu.

Here, there will be several sections under the LeanSwift sub-menu.

<kbd><img alt="Configuration-scope" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/leanswift-tabs.png"></kbd>


##

## Configuration/LeanSwift/eConnect

The _ **eConnect-ION** _ section contains the vast majority of the settings for base eConnect, and the details of each group is covered in the following sections of this document.

The following sections are included in the eConnect configuration:

<kbd><img alt="Configuration-scope" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/configuration-ion.png"></kbd>

#

# eConnect-base

The eConnect-base section contains settings to connect with eLink/ION/M3, some of which were earlier a part of the eConnect-General and Basic data configuration section.

eConnect-base has 2 sections

<kbd><img alt="Configuration-scope" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-base.png"></kbd>



**Import History**

Whenever an initial load API(EVS002MI/Initiate) call gets triggered, that request and response information will be displayed in this grid. This API triggers the Show BODs.
 Entity Name can be customer, address, order, shipment, invoice, product, inventory, atp.
 To trigger the Initial load BOD, we pass Entity Name, From Date, To Date, No. of Actions, Search Query as input and the result will be the Job ID.
 
 <kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/import-history.png"></kbd>



**Connectivity**

The Connectivity section of eConnect-base has the following configurations.

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-base-configurations.png"></kbd>



### Service Configuration

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/service-configurations.png"></kbd>

###

### M3 Connection Protocol

Provides a choice for the admin to choose between Leanswift eLink/ION version of eConnect. There are 2 options, Leanswift eLink and ION. eConnect uses the configuration based on the option chosen.

### Basic Data Configuration (M3 connection protocol - ION)

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/basicdata-configuration.png"></kbd>

### Company

The default company within M3. Setting can be defined on Default or Store level.

### Division

The default division within M3. Setting can be defined on Default or Store level.

### Authentication

The **Authentication** group contains the settings related to the web service authentication using the OAuth2.0 standard that eConnect employs.

This section is configured by LeanSwift during product installation.


**Authentication (M3 connection protocol - ION)**

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/ebase-authentication.png"></kbd>

To ensure the security of eConnect, OAuth2.0 is always enabled by default.

The M3 User is the user with which we connect to ION APIs

We have a &#39;Test connection&#39; button to verify if connection is up.

#

# eConnect-General

The General section contains a number of basic settings that are generic for this instance of eConnect.

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-general.png"></kbd>

###

### General Configuration

###

### Use M3 order history

This parameter refers to the retrieval of order history from M3 from Magento front-end.

Select &quot;Yes&quot; to retrieve the order history from the ERP system in real-time when the user selects _Order History_ in _My Account_. This will make order history seamless between Magento and the ERP and any order changes in the back-end ERP will be displayed in Magento instantly.

Select &quot;No&quot; to only use the order history from Magento when the user selects Order History in My Account.

### Display Invoice

Set this option to &#39;Yes&#39; in order to retrieve Invoice history details from M3. Please note that this does not apply to the B2C configuration when a single customer# in M3 is used for all orders.

In this case, the invoice history from Magento is always displayed by default.

###

### Debug/log data

Select &quot;Yes&quot; to log additional information in Magento. This setting is recommended in test but should be set to &quot;No&quot; in production to improve performance.

# eConnect-ION

#

# Basic Data Configuration

The **Basic Data Configuration** section of the configuration contains a number of key settings needed for the various transactions within LeanSwift eConnect.

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/basicdata-configuration.png"></kbd>

### Facility

The default facility within M3. Setting can be defined on Default or Store level.

### Warehouse

The default facility within M3. Setting can be defined on Default or Store level. This setting is currently used as input to all transactions except the Order Entry.

###

### Price Code

This refers to the Price List within M3 from which the list price/MSRP/Retail price is synchronized for a site. This setting is optional and can be left blank. Also note that if prices for a site should be synchronized, the &#39;Price&#39; attribute must also be included as part of the mapping within the &#39;Production Synchronization&#39; setup that&#39;s covered later in this manual.

###

### Currency code

Only required if &#39;Price code&#39; is filled in and is then used to ensure the right price list in M3 is used for price synchronization.

###

### Order Type

The default order type to use for Order creation. This setting can be managed on a Default or Website level.

**Document Class**

The default document class is Co02. It is the class used while sending Order comments to M3

# Shipping Method

This section manages the mapping between the Shipping methods that have been enabled within Magento (_Leanswift \&gt; eConnect-ION Configuration \&gt; Sales \&gt; Shipping Methods_) and the Delivery method- &amp; term within M3.

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/shipping-method.png"></kbd>

To add an additional mapping entry, simply press the &#39;Add&#39; button, and select the Magento Shipping Method value to map

Then, in the right two columns (M3 Delivery Method &amp; M3 Delivery Term) – key in the M3 values to which the Shipping method should be mapped:

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/shipping-method.png"></kbd>

Following this, remember to save the configuration by pressing &#39;Save Config&#39; at the top of the page.

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/save-config.png"></kbd>

#

#

# Manual Sync Configuration

Maximum number of records that can be selected at a time for manual sync can be configured here. There are separate configurations to set limit for Product, Customer and Order modules.

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/manual-sync-configuration.png"></kbd>

There is a maximum limit of 200 beyond which manual sync cannot be done.

# Customer General Configuration

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/customer-general-config.png"></kbd>


This section now contains the key parameters for how to handle customer creation, both for a B2B- and a B2C site.

NOTE! The &#39;Customer Template ID&#39; field has dual function depending on whether the Customer Registration feature is used or not. For a single site, these features are mutually exclusive in that one is intended for B2B- and the other for B2C use.

### Enable Registration

This feature is intended for a B2B setup where new customers are allowed to register themselves on the front-end.

 <kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/customer-general-config3.png"></kbd>

If **Enable Registration** is set to &#39;Yes&#39;, eConnect will remove the **Create New Customer** parameter as this indicates the site being configured is a B2B site where every customer always exists already when an order is place.

When **Enable Registration** is set to &#39;Yes&#39;, this indicates that as new customers register from the Magento front-end [customer registration extension not supplied as part of eConnect], a customer record is added in Magento – and a customer in a preliminary status (status 10) is created within M3.

A manual process is assumed within M3, where a Customer service/Accounting responsible would review these preliminary customers (credit checks etc.) – and if they are approved as a new customer the status in M3 is manually changed to active (20). While the customer status in M3 is preliminary (10), the customer in question can&#39;t place an order within Magento (eConnect performs a real-time check against M3 during the checkout process to validate the customer status). Products can be added to cart and the cart saved, but the checkout process can&#39;t be completed.

Setting **Enable Registration** to &#39;No&#39; disables the registration feature completely, which then in turn enables the Create New Customer parameter:

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/customer-general-config.png"></kbd>

### Create New Customer

This parameter is intended to be used for B2C sites where a choice needs to be made whether individual customers should exist in M3 for each consumer, or if a single &quot;common&quot; customer should be used for all consumer orders received from Magento.

If **Create New Customer** is set to &#39;Yes&#39;, the customer number specified in **Customer Template ID** will be used to create a new customer number within M3 for each order being placed. If a registered user is signed in, and as such already has a Magento customer# - a verification is always first performed to see whether there&#39;s a value on External Customer # or not. If there is – no new customer# will be created in M3.

If **Create New Customer** is set to &#39;No&#39;, then the same Customer# is used for each order created within M3. This customer number is then defined in the **Common Customer ID** field.

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/customer-general-config2.png"></kbd>

# Product Addition/ Synchronization

There exists functionality to conveniently map your M3 items to your Magento webshop. _Leanswift \&gt; econnect-ION \&gt; Configuration \&gt; [Product Addition/Synchronization](http://econnectqa.leanswiftdev.net/admin/admin/system_config/edit/section/ion/key/c35142ed29bd2e0250b9bfba0bb952a1c067e5f472b65ab9091ee1ab7ed48f08/#ion_product_sync-link)_. In the current version, simple and configurable products are supported using this process, for all other product types, the default Magento process of importing via CSV is in place.

You can control the Product sync in website level by choosing Yes/No option in the Enable field. Each of the features, addition of new items, and syncing of existing can be controlled independently of each other.

Set Enable to Yes to enable this feature.

Apart from this, Addition and Sync can be turned on/off individually.

The Dropdown attributes that need to be synced can be added in the Dropdown attributes field. Multiple values can be selected.

Batch size and Sync from Date features are removed in this version as sync happens instantly unlike in the eLink version which requires a cron to be triggered.

The New product status should be set to No to ensure the products do not appear in the webshop and set to Yes to appear.

&#39;Style SKUs as Configurable Products&#39; can be set to Yes if we want style items and can be set to No to save them as simple items

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/product-addition-sync.png"></kbd>

## Product attribute mapping

In order to ensure that the solution can deal with the flexibility and complexity of M3, the configuration allows you to specify what values from M3 should be mapped to the attributes which you have defined in magento. A Default field is provided to map a default value to any of the M3 fields.

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/m3-attribute-mapping.png"></kbd>

**Product Addition conditions:**

As the most common scenario faced is that your M3 instance will contain far more items than you wish to have available in your webshop, eConnect comes with the ability to provide configurable criteria for selecting which items to include from M3.

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/item-addition-condition.png"></kbd>

In Addition to this, we also have the option to choose if it is &#39;Any/All&#39; of all conditions.

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/condition-true.png"></kbd>

The main product tables are MITMAS, MITBAL and MITFAC.

**[Product Synchronization - Item](http://econnectqa.leanswiftdev.net/admin/admin/system_config/edit/section/ion/key/c35142ed29bd2e0250b9bfba0bb952a1c067e5f472b65ab9091ee1ab7ed48f08/#ion_category_sync-link)Disabling**

Configuration is provided to Enable or Disable the products in Magento.

Set yes to Disable the product status and map the required conditions.

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/item-disabling.png"></kbd>

# [Product Synchronization - AttributeSet Mapping](http://econnectqa.leanswiftdev.net/admin/admin/system_config/edit/section/ion/key/c35142ed29bd2e0250b9bfba0bb952a1c067e5f472b65ab9091ee1ab7ed48f08/#ion_attributeset_sync-link)

#

Magento uses the concept of attributes sets which allows products with similar features to be grouped and share a common set of attributes. Shoes for example would maybe need different attributes than the rental heavy equipment item. In order to ensure that items are imported and synced to Magento using the correct set of attributes, configuration is provided to assist in defining what M3 values indicate the product attribute set which the item will belong to.

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/attributeset-mapping.png"></kbd>

Similar to category mapping, a feature has been provided to define the behavior for attribute sets which have changed or those which do have a matching M3 value as has been defined.

To enable this feature &#39;Change AttributeSet for existing products&#39;is set to Yes

# [Product Synchronization - Category Mapping](http://econnectqa.leanswiftdev.net/admin/admin/system_config/edit/section/ion/key/c35142ed29bd2e0250b9bfba0bb952a1c067e5f472b65ab9091ee1ab7ed48f08/#ion_category_sync-link)

When items are imported into Magento, they will need to have at least one product category to which they will be associated with. When this information is available in M3, this can be used to avoid duplication of record maintained.

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/category-mapping.png"></kbd>

The category mapping is flexible enough to allow for more than one field in M3 to define which category it should belong to in Magento. The first step is to define the order and which fields in M3 will indicate category. The M3 Category source value should be entered in one continuous string.

Once the source is entered, Items get created into magento and the categories are created based on Source.

The first source value acts as a Parent and the rest of the source value forms sub-categories.

Once Category source is defined, any changes can cause abnormality in the behavior of product Addition/sync.In addition, a default category can be used for values which are missing values in the fields which have been defined for category mapping.



# Customer Addition/ Synchronization

Customer Addition/Synchronizationcontains all settings related to fetching Customers from M3 and synchronizing Customer data. In this version, the following limitations apply:

Addition:

- Fetches all customers irrespective of active/inactive (status)
- Fetches customers with a default email address

Synchronization:

- Sync only applies to existing customers
- Customer master and Financial Data is synchronized.
- Address data is synchronized

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/customer-addition.png"></kbd>

###

### Enable

This setting provides the option to enable/disable the Customer Addition/Sync on website level.

###

### Enable Customer sync

This setting provides the option to enable/disable the Customer Sync on website level.

###

### Enable Customer Addition

This setting provides the option to enable/disable the Customer Addition on website level.

###

### Customer Group Id

This setting provides the option to choose the group from which customers from M3 needs to be imported.

**New Account Email Notification**

This field sends a mail confirmation to the newly added customer when set to yes. The mail will have a &#39;Confirm Account&#39; option. When clicked on that, user will get redirected to frontend page

### Customer Master Mapping

This section allows for mapping of additional Customer related fields within Magento to Customer master fields in M3. The mapping works exactly the same way as for the previous two sections. Customer&#39;s Order type, Facility and Division can also be synchronized. When a customer has this data synchronized, this detail gets picked over the basic data while order is getting placed

### Customer Address Mapping

This section controls how the Billing and Shipping Address for the customer in Magento is to be created based on the address details in M3.

The mapping is done in the same way as for Shipping methods and Product Sync for example. The Magento address attribute to map is selected from the drop-down list in the &#39;Magento Attribute&#39; column. The M3 attribute this should be mapped to is then selected from the drop- down list in the &#39;M3 Attribute&#39; column.

# Sales

The &#39;Sales&#39; section contains three key settings related to the sales order process from Magento to M3.

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/sales.png"></kbd>

### Enable order comments

If set to &#39;Yes&#39;, this enables sending header-level comments [entered in the last step of the Checkout process] for the entire order to M3.

### Allow Item Price

If set to &#39;Yes&#39;, this enables sending Price for the order to M3.

### Capture Payment Online

This option set to &#39;Yes&#39; will during Invoice creation in Magento [as part of the synchronization when the invoice details from M3 are used to create the Magento invoice] also invoke the &#39;Capture&#39; transaction from Magento for credit card orders. If this option is set to &#39;No&#39;, it&#39;s assumed that capture of funds via whatever payment gateway is used within Magento is handled manually via a separate process.

# Order Charges

The **Order Charges** group contains the settings related to how various additional charges within Magento, such as Tax- &amp; Shipping (freight) should be handled by eConnect.

**Tax Transfer &amp; Tax Charge code:** If Tax Transferis set to &#39;No&#39;, then dynamically the Tax Chargefield is not displayed as it doesn&#39;t apply:

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/order-charges.png"></kbd>

When **Tax Transfer** is set to &#39;Yes&#39;, the **Tax Charge** field is visible:

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/order-charges-taxcode.png"></kbd>

The drop-down for Tax Charge code provides dynamic values from M3 to enable an easy selection and reduce the risk for erroneous entry:

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/order-charges-taxcode-dropdown.png"></kbd>

### Shipping/Freight Fee Charge Type

This setting provides the option to determine whether to in M3 handle the Shipping fee from Magento as a Non-stock item or an order header charge.

There exists an option to enable/disable, with which one can control whether to send the shipping charge to M3 or not,the parameter offers the user a simple selection between the two options:

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/order-charges-shipping.png"></kbd>


Depending on the selection, the following setting is dynamically adjusted. When &#39;Non-stock item&#39; is selected as in the screen shot above, the user can select Shipping/Freight Fee Item Number in the field below. The selection is also here dynamic against M3 so that it provides the user with a simple drop-down of applicable items from M3.

If &#39;Charges&#39; is selected, the following field provides selection of &#39;Shipping/Freight Fee Charge Code&#39;, and also in this case the list of available Charge ID&#39;s is dynamically retrieved from M3:

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/order-charges-shipping-dropdown.png"></kbd>


### Gift Wrap Transfer

The **Gift Wrap** Transfer parameter controls whether or not to transfer Gift Wrapping related information from Magento. This information includes:

- Order level gift wrapping (Cost &amp; Description)
- Line level gift wrapping (Cost &amp; Description)
- Gift messages (Order &amp; Line level)
- Printed Gift message card cost

If **Gift Wrap Transfer** is set to &#39;No&#39; – no information related to Gift Wrapping will be transferred from Magento to M3.

If **Gift Wrap Transfer** is set to &#39;Yes&#39; – all of the above-mentioned information can be transferred (depending on what&#39;s been configured and is in use within Magento).

Setting the parameter to &#39;Yes&#39;, will also in this case dynamically open up a number of additional fields on the screen:

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/order-charges-giftwrap.png"></kbd>

The **Gift Wrap Charge Type** parameter controls whether the Gift Wrapping related costs in Magento should be transferred over to M3 as Charges (Order- and/or Line) or Non-stock items.

As in the previous screen shot – if **Gift Wrap Charge Type** is set to &#39;Non-stock items&#39; – the user is presented with selecting a non-stock item to use for (i) Order level gift wrapping charges and

(ii) Line level gift wrapping charges. These two non-stock items don&#39;t have to be different – they can both use the same M3 non-stock item value.

If instead the **Gift Wrap Charge Type** parameter is set to &#39;Charges&#39; – the following two parameters are dynamically adjusted to **Gift Wrap Order Charge Code** &amp; **Gift Wrap Line Charge Code** , offering a selection of Order-level and Line-level charge codes in M3 to handle Order-level Gift wrapping costs and Line-level Gift Wrapping costs.

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/oder-charges-giftwrap-charges.png"></kbd>

# Payments

The Payments group contains the configuration related to credit-card integration, payment terms &amp; methods mapping, invoice fees etc.

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/payments.png"></kbd>

### Re-authorization Amount (Credit Cards)

Single-authorization is used by eConnect, i.e. the credit card authorization created by Magento is transferred over to M3 without the need to re-authorize. This parameter will be removed.

### Payment Provider

The mapping within this setup provides the link between Magento Payment Method values and Payment Terms &amp; Payment Method values in M3. In the case of the mapping for the Credit Card Payment Method, the &#39;M3 Credit Card Provider&#39; value also provides direct input to the order creation process.

### Invoice Fee Charge Type

Invoice fees that can be imposed by certain payment providers can via this setting be handled two different ways in M3 – either as a non-stock item or as a [order header] charge.

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/invoice-fee-type.png"></kbd>

The selection made on this parameter will control which of the two values &#39;Invoice Fee Charge Code&#39; or &#39;Invoice Fee Charge Item no&#39; in the mapping below that will be used

### Invoice Fees

This section is used if any Payment provider imposes some kind of transaction fee that needs to be represented on the order in M3. One example of this is the Swedish payment provider _Klarna_, that imposes a fee of about 25 SEK on each purchase when their service is used.

The fee corresponding to the value entered in the &#39;Invoice Fee Amount&#39; column is added to the order either as a header charge or as a non-stock item depending on the previous settings.

In the example here, a fee of $2.00 would be added to each order as a non-stock item when the Credit Card payment option is used.

# Price Synchronization

The Price Synchronization settings have been added to provide an option to enable or disable the real-time customer/item specific price call, as well as provide an option to increase site performance when needed.

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/price-sync.png"></kbd>


### Enable

Setting this parameter to &#39;Yes&#39; enables the Customer special price to be updated in magento when there is a change in M3 price table. Setting to No will not update any changes in magento.

When his setting is turned On, Customer special price is displayed in frontend when the customer places the order.

### Enable in Admin

Setting this parameter to &#39;Yes&#39; enables the Customer special price to be updated in magento when there is a change in M3 price table. Setting to No will not update any changes in magento.

When his setting is turned On, Customer special price is displayed in the backend when customer places the order.

#

# Inventory Synchronization

This setting provides an option for which stock to invoke when stock is updated in M3.

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/inventory-sync.png"></kbd>

### ERP Inventory Attribute

Allows admin to choose between On-Hand/Available Inventory/Allocatable Net.

**Initial Load/ Import**

This feature enables to import the data from M3.

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/load-import.png"></kbd>

Each of this section has a set of fields that allows to choose date range and conditions for the data to be imported.

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/import-customers.png"></kbd>

**BOD Mapping**

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/bod-mapping.png"></kbd>

#

# Cron Settings

This section contains the basic setup for how often the LeanSwift specific background (cron) jobs should run. The actual configuration of the job in the screenshot below is not representative of a normal customer installation.

The setup will vary from customer to customer depending on a number of factors such as basic data volumes, ordering processes etc.

This section should always be reviewed within the project, and with the help of the LeanSwift Services team be adjusted to best fit each customer&#39;s environment.

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/cron-settings.png"></kbd>

#

# Version Info

This last section provides information related to the version of the LeanSwift Magento extension that&#39;s installed.

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/version-info.png"></kbd>

# MAGENTO STANDARD FUNCTIONALITY

The ERP connector does not override or impact any other functionality in Magento. Configure Magento using the Magento admin panel as required.

# Exit System

Log out from Magento admin using the link at the top right.

<kbd><img alt="import history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/manual-sync-configuration.png"></kbd>


