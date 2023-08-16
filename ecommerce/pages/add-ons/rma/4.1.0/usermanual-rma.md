# **User Manual – RMA Add-on for eConnect**
![econnect_banner](../../../../../images/banner-econnect-m3.jpg)

**Product Version**  **4.1.0**

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
- [RMA ADD-ON](#rma-add-on)
    - [2.0.1 Summary](#201-summary)
    - [2.0.2 Assumptions/Limitations](#202-assumptionslimitations)
  - [2.1 CONFIGURATION](#21-configuration)
    - [2.1.1 Standard Magento Configuration - General](#211-standard-magento-configuration---general)
    - [2.1.2 Standard Magento Configuration – RMA Item Attributes](#212-standard-magento-configuration--rma-item-attributes)
    - [2.1.3 Standard Magento Configuration – Product Setup](#213-standard-magento-configuration--product-setup)
    - [2.1.4 LeanSwift Extension Configuration – RMA](#214-leanswift-extension-configuration--rma)
  - [2.2 PROCESS](#22-process)
    - [2.2.1 RMA Creation (Return) – Magento Admin](#221-rma-creation-return--magento-admin)
    - [2.2.2 RMA Creation (Exchange) – Magento Admin](#222-rma-creation-exchange--magento-admin)
- [APPENDIX A – Status mapping](#appendix-a--status-mapping)


# GENERAL INFORMATION

## 1.1 System Overview

**LeanSwift eConnect for Infor M3** provides a powerful, seamless integration between Magento and Infor M3 ERP. The product consists of a base Magento extension that extends standard Magento functionality and offers several transactions to ensure your eCommerce websites contain up-to-date information from your M3 ERP. There exist a number of optional add-on extensions too for additional functionality

**LeanSwift eConnect for Infor M3** is available for Magento Open Source and Magento Commerce and for Infor M3 version 7.x and above. It is also compatible with multi-tenant cloud editions of Infor M3 (Cloudsuite).

**LeanSwift eConnect for Infor M3** employs a layered architecture to allow flexibility in supporting different versions of Magento and Infor M3 and to allow independent upgrades.

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


<kbd><img alt="eLink Architecture" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/elink_Architecture.png"></kbd>


### Architecture with ION for multi-tenant Cloud M3

<kbd><img alt="ION Architecture" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/ION_Architecture.png"></kbd>

The add-ons for LeanSwift eConnect provide extended functionality over the standard features available on eConnect Core.

These add-ons can, if necessary, be modified, and new add-ons can be added to fulfill specific customer requirements.

[Go to Top](#table-of-contents)

**User interface**

During setup, the Magento Admin panel is used to configure which transactions that should be used and how they should function. There is also additional configuration within the Connector to support the transactions.

**Validated versions**

Magento Commerce 2.4.1

Infor M3 CloudSuite

## 1.2 Points of Contact

### 1.2.1 Information

This document and the software it describes are provided by LeanSwift Solutions Inc. For additional information regarding support, licensing, functionality etc. please contact LeanSwift Solutions Inc via contact form at [http://www.leanswift.com](http://www.leanswift.com/)or email info@leanswift.com

## 1.3 Organization of the Manual

This manual is not intended to cover any standard Magento functionality or user experience. The Magento user experience is customized and slightly different in each eCommerce implementation – though the general workflow is similar.

[Section 2](#_heading=h.3o7alnk) provides the detailed setup &amp; functionality of the LeanSwift RMA add-on.

## 1.4 Acronyms and Abbreviations

ERP – Enterprise Resource Planning

RMA – Return Merchandise Authorization

[Go to Top](#table-of-contents)


# RMA ADD-ON

### 2.0.1 Summary

The _RMA_ (Return Merchandise Authorization) module extends the standard Magento Enterprise functionality for managing Customer Returns by providing full integration to Infor M3 ERP. **This add-on is available only for Magento Commerce**.

RMAs can be defined in several different ways. Within eConnect the following terms have been applied:

**Return** – Generally these are for product that was incorrectly purchased (but the goods are undamaged)

**Claim** – Generally these can be defined as some damage has occurred to purchased products. However, 2 types of claims need to be supported:

- Stock to be returned
- Stock not to be returned

**Exchange** – could be either a Return or Claim, but on top of bringing back one product - a new sales order to ship out the exact same product as a replacement would be created

Depending on the customer specific configuration of M3, a Return and Claim where stock should be returned could be treated the same way.

An RMA can only be created if the original sales order exists within Magento, and is in a 'Complete' status. The current date must also be within the valid RMA period as specified within the LeanSwift extension configuration (see section [**2.1.4.1**](#_heading=h.z337ya) of this manual for further details).

In this manual, the process to create the following RMA types are illustrated:

1. RETURN
2. EXCHANGE

The process to create a CLAIM (Stock return or not) is exactly the same as 1) – the only difference is the M3 order type used, and with that possibly the behavior of the transaction in M3.

Please note that within Magento – the process is exactly the same for creating a **Claim** as well as an Exchange. The only difference is that different selections are being made for the 'Reason to Return' and 'Resolution' values during the step where products are added to the RMA.

The main difference between the various types of RMAs can be found within M3, and the degree of difference can vary between M3 installations based on system configuration.


### 2.0.2 Assumptions/Limitations

- The RMA add-on requires Magento Commerce

- The RMA add-on requires LeanSwift eConnect Magento extension

- The M3 OIS390 functionality is not used as it does not automatically provide for either:

	- Return Header creation
	- The connection of header and line charges

- For the RMA configuration in M3, it is recommended that a Customer order type with Order category '1' and 'Nmf' '1' is used. This way (together with appropriate settings on the Dispatch policy) it's possible to ensure that the RMA created in M3 stops in a status '44', and in this way – no quantity is automatically received in the system.

- Exchanges are defined as the return &amp; replacement of the exact same item, quantity &amp; price, where no fees associated with the original are refunded – and no additional shipping is charged.

- Partial receipts of RMAs (i.e. 2 EA requested to be returned but only 1 EA received) must be handled as a 'report complete' receipts within M3, i.e. the delivery line should not be left open with any quantity pending following the receipt.

- If an order type is used that moves the order all the way to &quot;received&quot; (66) status upon creation, it's key to use the 'Picking Correction' option to adjust the received quantity prior to syncing with Magento.

[Go to Top](#table-of-contents)

## 2.1 CONFIGURATION

The configuration for RMAs is made up of two parts – the standard Magento setup and the LeanSwift-specific setup.

### 2.1.1 Standard Magento Configuration - General

The general standard Magento configuration can be found under Stores > Configuration > Sales > Sales.

<kbd><img alt="Magento Config" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/standard_magento_config.png"></kbd>

The options include whether or not RMAs should be possible to create from the front-end, whether RMAs are enabled on product level and whether or not to use the address for the store for RMAs. If the last setting is set to 'No', the address to use must be filled in:

<kbd><img alt="Magento Config" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/rma_setting.png"></kbd>

### 2.1.2 Standard Magento Configuration – RMA Item Attributes

Another key setup for the RMA process is the definition of what Magento refers to as 'RMA Item Attributes'. These attributes are the classifications used during addition/editing of RMA lines to indicate what's wrong with each product and what the desired course of action for each is.

The RMA Item Attribute configuration can be accessed via _Stores \&gt; Attributes \&gt; Returns_

<kbd><img alt="Magento Config" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/returns_attributes.png"></kbd>

With the installation of LeanSwift's Magento RMA Add-on, the required Attribute codes &amp; values are added to your Magento installation. The following Attribute codes &amp; values are added:

| **Attribute ID** | **Values** | **Comment** |
| --- | --- | --- |
| resolution | ReturnClaim Claim-NonStock Exchange | Represents the four RMA types available |
| reason | \* dynamic \* | Holds the M3 reason codes values for the installation in question (i.e. CRS103) |

### 2.1.3 Standard Magento Configuration – Product Setup

The key setting for each product is whether RMAs are enabled for the product in question. The options are 'Yes', 'No' or to use the general configuration mentioned in section 2.1.1.

<kbd><img alt="Magento Config" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/enable_rma.png"></kbd>

### 2.1.4 LeanSwift Extension Configuration – RMA

The LeanSwift specific settings related to RMA can be found under _LeanSwift \&gt;Add-ons\&gt; Returns_.

<kbd><img alt="Magento Config" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/add_ons.png"></kbd>

<kbd><img alt="Magento Config" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/returns_addon.png"></kbd>

The four groups of RMA parameters are covered in the following four sections.

#### 2.1.4.1 LeanSwift Extension Configuration – General Configuration

This group contains settings to define the valid RMA period, and for which M3 customer order type that should be used for each type of RMA.

<kbd><img alt="Magento Config" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/general_config_rma.png"></kbd>

**Valid RMA Period**

An RMA can only be created within the number of [calendar days] defined here from when the original order was created. This setting is only validated for RMA creation via the front-end.

**Return Order Type**

The M3 customer order type to be used when _RMA type_ **Return** is selected.

**Claims Order Type (Stock Return)**

The M3 customer order type to be used when _RMA type_ **Claim** is selected.

**Claims Order Type (No Stock Return)**

The M3 customer order type to be used when _RMA type_ **Claim NoN-Stock** is selected.

**Exchange Credit Order Type**

The M3 customer order type to be used when _RMA type_ **Exchange** is selected. This order type is used to generate the first [out of two] Exchange transaction – the initial _credit_ order in M3. Both of the Exchange order types are assumed to impact stock.

**Exchange Debit Order Type**

The M3 customer order type to be used when _RMA type_ **Exchange** is selected. This order type is used to generate the second [out of two] Exchange transaction – the final _debit_ order in M3 (i.e. the order used to ship out the new/replacement product to the customer).

#### 2.1.4.2 LeanSwift Extension Configuration – Warehouses

This group allows for a mapping to be created that will ensure a different warehouse for the RMA transaction is used depending on which country the original order was delivered to( **CHECK** ).

<kbd><img alt="Magento Config" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/warehouse_rma.png"></kbd>

#### 2.1.4.3 LeanSwift Extension Configuration – Reason Codes

This group contains mappings between the M3 reason codes &amp; RMA type. For each mapping, it's also possible to control whether the reason code is usable by the end-customer from the front-end or not.

Please note that this mapping affects the front-end behavior only in the way that if 'RETURN' for example is selected as the _Resolution_ – only those RMA codes that here have been associated with that RMA type are available for the end-customer to select. This same restriction is not available within Magento Admin.

The values on 'RMA Code' are dynamically (for each session) retrieved [and cached for each session] from '' (CRS103) in M3.

<kbd><img alt="Magento Config" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/reason_code_rma.png"></kbd>

[Go to Top](#table-of-contents)

## 2.2 PROCESS

Once the setup described in the previous section has been completed, the RMA functionality is ready to use both from the front-end (if enabled) and from within Magento Admin.

The following sections cover both processes. Creation of both a _RETURN_ and an _EXCHANGE_ from Magento Admin is covered. Creation of all types of RMAs is also available from the front-end of any associated Magento web shop, but is not covered separately in this document.

### 2.2.1 RMA Creation (Return) – Magento Admin

The prerequisites for creating any RMA from either Magento Admin or front-end are:

- the original sales order must exist in Magento
- the current date must be within the specified valid return period
- the product/products to be added to the RMA must be enabled for RMA processing

Once all of the above is fulfilled, the following steps make up the RMA process within LeanSwift eConnect.

In the following example, the original sales order below is used as the basis:

<kbd><img alt="Returns order summary" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/returns_order_summary.png"></kbd>

#### 2.2.1.1 RMA Creation – Magento Admin

An RMA can from within Magento Admin be initiated in two different ways.

**From Original Order**

Opening up the details of the original sales order reveals a '' button in the upper left corner:

<kbd><img alt="create Returns order" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/create_returns_orderpage.png"></kbd>

**From RMA Grid**

The RMA grid is accessed via _Sales> Operations> Returns_. In the upper right-hand corner of the RMA grid, the 'New RMA Request' button can be found.

<kbd><img alt="New return request" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/new_return_request.png"></kbd>

From within Magento Admin, both of the above options brings the user to the same starting point for creating a new RMA transaction.

**General Information**

The first panel contains general information that applies to the entire RMA.

1. Request details with the original Magento sales order number, Customer name &amp; e-mail and an optional additional contact e-mail.
2. The Customer's shipping address.
3. The return address per the configuration in Magento.

<kbd><img alt="New return general information" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/new_returns_general_info.png"></kbd>

**RMA Items**

The detailed panel is where the actual products to be returned are added. This is done via the '+Add Products' button in the upper right-hand corner.

<kbd><img alt="New return add product" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/new_returns_add_product.png"></kbd>

This action reveals a list of products eligible to be added to the RMA.

<kbd><img alt="New return add selected product" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/new_returns_add_selected_pdt.png"></kbd>

**1)** Check the selection boxes for each product that should be added to the RMA (information to the right indicates the SKU, sold price and quantity that remains possible to return).

**2)** Pressing the '+Add Selected Product(s) to RMA' will bring up the next panel where the final details for the RMA can be completed.

<kbd><img alt="New return empty fields" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/new_return_details.png"></kbd>

**1)**_Requested Qty_ refers to the quantity per line item that the customer is requesting to add to this RMA transaction.

**2)**_Reason to Return_ refers to which reason code [dynamically retrieved from M3] best describe why the RMA transaction is being created for this product.

**3)**_Resolution_ refers to the requested action on this RMA (i.e. Return, Claim, Claim-NonStock or Exchange).

**Please note** that since each _Resolution_ corresponds to a different order type in M3 – all products on a RMA transaction must have the same _Resolution_ value.

**4)** Once all the above information have been entered – the RMA is created by pressing the 'Submit RMA' button.

The same screen with all the completed information necessary to create the RMA:

<kbd><img alt="New return highlights" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/new_returns_product_highlighted.png"></kbd>

Once the RMA has been submitted, the user is returned to the RMA grid with a confirmation message that the RMA has been successfully created, and the first transaction in the list is the latest RMA added.

The status of a new RMA is always 'Pending'.

As part of the LeanSwift RMA add-on, two new columns have been added to the RMA grid – 'Temp Order#' and 'Final Order#'. The 'Temp Order#' is the batch order number from M3 (OIS275), and the 'Final Order#' is the actual [final] customer order number assigned by M3 once the transaction has been successfully added.

<kbd><img alt="rma request submitted" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/request_submitted.png"></kbd>

#### 2.2.1.2 RMA Synchronization

The create RMA can [just like a sales order] be synchronized over to M3 in two different ways – manually or automatically (via a cron job).

**Manual Sync**

The manual sync is initiated via the RMA transaction grid:

<kbd><img alt="rma manual sync" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/returns_manualsync.png"></kbd>

Once the synchronization has completed, the result is indicated by the message at the top of the screen (1). The RMA transaction is also updated:

**Temp Ord#** : A value is received in this field (M3 Temporary/Batch order number) once the sync has successfully initiated the order creation within M3. Even if there are issues during order creation in M3 so that the order is stopped in 'Batch Customer Order. Open' (OIS275) – this value is still updated to indicate the communication &amp; synchronization with M3 was successful.

**Final Ord#** : This field represents the actual final customer order number assigned by M3. Once this field is populated, this indicates that the complete synchronization for the transaction completed successfully.

**Status** : The RMA status is always updated to 'Authorized' once the RMA has been fully synchronized over initially to M3. For further details on the Status values, please refer to the Appendix of this document.


**Cron Sync**

The synchronization via the available cron job works exactly the same way as the Manual Sync described above. The RMA Sync cron is configured following the same standard Linux rules as any of the other cron jobs.

<kbd><img alt="rma cron sync" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/cron_setting_rma.png"></kbd>

**ION version:**

The difference between ION &amp; eLink version is that, order have to be synced manually in elink whereas in ION version, BOD updates the order status

We also have an additional functionality which is importing RMA config using import option unlike the cron option in elink version

<kbd><img alt="import config" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/import_config.png"></kbd>

.

Once user clicks on Import button, RMA configuration will be imported from M3.

#### 2.2.1.3 M3 Processing – Return

\*\* Please Note \*\*\*

The processing of the Return transaction in M3 that's described in this section can vary from customer to customer, as there are a multitude of different ways to configure both customer order types and dispatch policies. Depending on the configuration of these in M3, slightly different variations of this process can be achieved.

As a reference and background to the example in this document, the following key settings on _Customer order type (OIS010)_ and _Dispatch policy (MWS010)_ are used. These represent a process that some of LeanSwift's customers employ, and that is representative for how we feel the RMA transactions should be managed in M3.

There are of course a larger number of additional settings besides those mentioned below, for example related to how to handle invoicing. The below simply represents the key setup for the main Return process.

**Customer Order Type (OIS010)**

Order Category: 1 – Normal Order

Next Manual Function (Nmf): 1 – According to settings on connected Dispatch Policy

Quantity Sign: 1 – Only Negative

**Dispatch Policy (MWS010)**

Auto Level: 3 – Pick list reporting

030 Released for allocation: 1 – Checked

040 Released for picking: 1 – Checked

100 Auto print of picking lists: 1 – Checked

160 Shipment assembly point: 9 – Not Used

170 Partial reporting allowed: 1 – Partial report

175 Pick reporting level 1 – Pick line mode

190 Flag as compl permitted 1 – Checked

200 Create accounting entries 1 – Checked

240 Packaging reporting method 0 – Packing not sued

300 Closing point 2 – First pick list created

310 Next delivery released for alloc 1 – Released

320 Next delivery released for pick 0 – Not released

With the setup described above, the Return transaction is in M3 created and stopped in a status '44' (Out to pick). For a Return, this signifies that the Return is pending receipt.

<kbd><img alt="customer order open" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/rma_m31.png"></kbd>

To illustrate the capabilities of eConnect's RMA sync, this Return will in this example be processed in two steps. The business scenario here being that the customer (for size reasons for example) had to ship the two products that are being returned in different packages. With this in mind, an RMA must be possible to process in multiple steps.


**Please note!**

The pick reporting (receipt) of each individual picking list line must be complete, and not left partially open as M3 allows. This should in most instances make perfect business sense in that if a customer says they will return 3 EA of an item, and only 1 EA is received – then for whatever reason they decided to only return 1 EA instead of 3 EA and someone would reach out to the customer and confirm. If it's then found that additional units are on the way – the RMA line should not be reported until the full quantity expected has been received.


This is the original picking list, where 2 EA of both products are expected to be returned:

<kbd><img alt="customer order open" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/rma_m32.png"></kbd>

The first pass at receipt reporting

<kbd><img alt="customer order open" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/rma_m33.png"></kbd>

The above action will receive 1 of 2 EA for the first line and close it for further processing (signified by '1' in the Com (_Complete_) field).

Following the _Confirm All_ action, the order will look as follows [once M3's auto jobs have finished processing], meaning that the second line (product 200200) is then still expected to be received at at later time:

<kbd><img alt="customer order open" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/rma_m34.png"></kbd>

A sync with Magento and verification of the RMA transaction in Magento shows it as 'Return Partially Received':

<kbd><img alt="return partially received" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/partially_received.png"></kbd>

Looking at the RMA lines, this is then simply due to the fact that one line at this point has been completely returned (status 'Return Received') and the second line hasn't been received at all.

<kbd><img alt="return received" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/return_received.png"></kbd>


As a final step, the complete receipt of the second line is performed within M3:

<kbd><img alt="return received" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/rma_m35.png"></kbd>

Once this has been completed and the RMA synced again in Magento, the final result of the complete receipt reporting can be seen:

<kbd><img alt="return fully received" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/order_fully_received.png"></kbd>


Once the order in M3 is invoiced and synced again in Magento, the final result and status is received:

![](RackMultipart20210209-4-1hab68o_html_bb637e005ed5914.png)

![](RackMultipart20210209-4-1hab68o_html_af81f089cc7741e4.png)

![](RackMultipart20210209-4-1hab68o_html_8f291c4c99a19b5.png)

### 2.2.2 RMA Creation (Exchange) – Magento Admin

The overall process to create any type of RMA from a Magento front-end is very similar to how it's handled within Magento Admin when it comes to the overall process. There are however certain details that differ, and this section covers this.

#### 2.2.2.1 RMA Creation – Exchange

An RMA of type _Exchange_ can just like the _Return_ from within Magento Admin be initiated in two different ways. In this section, the Exchange is created from within the original order – which is displayed below. A new RMA of the type Exchange is created in the same as the Return – by pressing the 'Create RMA' button in the upper left corner.

<kbd><img alt="exchanges order page" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/create_returns_orderpage.png"></kbd>

In the step that follows, move to the 'RMA Items' section on the left and press 'Add Products' in the upper right-hand corner.

<kbd><img alt="exchanges add product" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/exchanges_add_product.png"></kbd>

On the following screen displayed below, select all the products that should be included in the Exchange. Press '+Add Selected Product(s) to RMA' when done.

<kbd><img alt="exchanges add selected product" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/exchanges_add_selected_pdt.png"></kbd>

In the next step is really where the determination of what kind of RMA this transaction will become is done (please refer to screen shot below). Enter how many of each product that should be included on this RMA in the 'Requested Qty' field **(1)**, what the reason for the return is in the 'Reason to Return' field **(2)** – and finally what the requested resolution (i.e. type of RMA) is in the 'Resolution' field **(3)**.

Please note! That the above information must be entered for all products that are listed on this screen. If one of the fields are left blank – Magento will require input and the following message is displayed to the user: 'This is a required field'

If at this point the customer would change their mind and not want to include one or several of the products on the RMA – simply use the 'Delete' option to the right of the applicable line to remove it from the RMA.

Once all this information has been entered – press 'Submit RMA' **(4)** to complete the RMA creation.

<kbd><img alt="exchanges add selected product" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/exchange_newreturns_steps.png"></kbd>

The new RMA will show up in the RMA grid that's displayed as the next step, and the initial status prior to synchronization is 'Pending'.

<kbd><img alt="exchanges request submit" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/exchange_request_submit.png"></kbd>

#### 2.2.2.2 RMA Synchronization

The Exchange RMA transaction can in the same way as the Return be synchronized Manually or Automatically via a cron job. In this example, only the manual option is covered.

The manual sync is also for the Exchange performed directly from within the RMA grid. Mark the selected transaction/transactions to be synced, select 'Sync with ERP' as _Action_ and press 'Submit':

<kbd><img alt="exchanges request submit2" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/exchange_request_submit2.png"></kbd>

A confirmation is received, in this example that the order was successfully created in M3 – and the _Status_ is also updated accordingly. If the RMA was successfully added in M3, the actual M3 order number will also be displayed in the 'Final Ord #' field.

<kbd><img alt="exchanges request submit2" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/exchange_return_request.png"></kbd>

For further details on the final order# and other fields on this screen, please refer to section [**2.2.1.2**](#_heading=h.3whwml4) earlier in this document.

#### 2.2.2.3 M3 Processing of Exchange

Please refer to section **2.2.1.3** for some comments regarding the processing of RMAs in general in M3. It's true also for the Exchange that there are multiple different ways this can be configured within M3, so what is covered in this section is one possible way to handle this.

With regards to Exchanges, a few things are specifically worth mentioning. Also please refer to section **2.0.2** for applicable Assumptions/Limitations.

- An Exchange is defined as the exact replacement (one-to-one) of a product at the same price.
- For an exchange, there are always two orders generated &amp; processed within M3:
  - One _Credit_ order to manage the return of the product.
  - One _Debit_ order to manage the dispatch of the new replacement product to the customer.
- The Debit &amp; Credit order types are defined within the LeanSwift Magento extension configuration (see section [**2.1.4.1**](#_heading=h.z337ya) for more details).

With the M3 setup for this example, the resulting Debit order in M3 is created in a status '44' (i.e. &quot;Pending receipt):

<kbd><img alt="exchanges m3 part1" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/exchange_rma_m3_1.png"></kbd>

To process through the receipt in this case, a 'Confirm Issues' is performed for the applicable number of units (just one in this example). Please note that also here it is possible to receive fewer that expected, as long as the delivery line is closed.

The Exchange will move to a status of '66' (Received) after this.

<kbd><img alt="exchanges m3 part2" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/exchange_rma_m3_2.png"></kbd>

The final step [for any RMA in M3] is Invoicing. This can be done in a number of different ways, normally in batch and scheduled to run with a certain frequency. It's also possible to have the order automatically invoice right after it reaches a received (66) status.

To describe the complete process for an Exchange, it's crucial that this step is performed – and the order synchronized with Magento after that. This final synchronization will check if the transaction is of an Exchange type and if it's been invoiced. If that's the case, the final synchronization will generate the _Debit_ order – i.e. the new &quot;normal&quot; sales order that in M3 will be used to ship out the replacement product to the customer.

If manually performed, invoicing is initiated from 'CO Invoice. Print' (OIS180). Enter in the sales order number in both the 'From' and 'To' CO no fields and press _ENTER/NEXT_. The [Credit] Exchange order in M3 will move to status '77' (Invoiced).

<kbd><img alt="exchanges m3 part3" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/exchange_rma_m3_3.png"></kbd>

Perform one final synchronization (manually in this example, but this would normally be handled automatically by the associated cron job in Magento):

And once the RMA in Magento has reached a 'Processed &amp; Closed' status, the final Debit order to ship out the replacement product in M3 has been generated.

<kbd><img alt="processed and closed" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/exchanges_returns_processednclosed.png"></kbd>

The Debit order can be found by looking for one of the last &quot;normal&quot; sales orders based on the applicable number sequence defined in M3. In this case, no additional sales orders have been processed since the one used to initiate this example – so it will be the next number following the original sale orders (which was 0001113237) i.e. **0001113238**.

<kbd><img alt="exchanges m3 part4" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/exchange_rma_m3_4.png"></kbd>

This then concludes the Exchange process. The Debit order will be processed following whatever routines are configured for that order type in M3, which [since it's a separate order type] can be different from other types of sales orders.


# APPENDIX A – Status mapping

In order to properly handle the case where only a part of an RMA should be received, the synchronization between M3 and Magento needs to be based on line level order statuses.

LeanSwift's synchronization within eConnect ensures that that the RMA line status is updated correctly based on the M3 order line status, and the RMA header status is then updated appropriately by Magento.

<kbd><img alt="statuses" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/rma/statuses_sync.png"></kbd>

[Go to Top](#table-of-contents)
