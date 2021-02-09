# **eConnect User Manual – RMA**
![econnect_banner](../../../../../images/banner-econnect-m3.jpg)
## **LeanSwift eConnect for Infor M3 &amp; Magento** 


**Product Version**  **4.1.0**

**eConnect version 20.3.0**


**TABLE OF CONTENTS**


[1.0 GENERAL INFORMATION](#general-information)

- [1.1 System Overview](#system-overview)

- [1.2 Points of Contact](#points-of-contact)

- [1.2.1 Information](#information)

- [1.3 Organization of the Manual](#organization-of-the-manual)

- [1.4 Acronyms and Abbreviations](#acronyms-and-abbreviations)

[2.0 RMA ADD-ON](#rma-add-on)

- [2.0.1 Summary](#summary)

- [2.0.2 Assumptions/Limitations](#assumptionslimitations)

- [2.1 CONFIGURATION](#configuration)

	- [2.1.1 Standard Magento Configuration - General](#standard-magento-configuration-general)

	- [2.1.2 Standard Magento Configuration – RMA Item Attributes](#standard-magento-configuration-rma-item-attributes)

	- [2.1.3 Standard Magento Configuration – Product Setup](#standard-magento-configuration-product-setup)

	- [2.1.4 LeanSwift Extension Configuration – RMA](#leanSwift-extension-configuration-rma)

		- [2.1.4.1 LeanSwift Extension Configuration – General Configuration](#leanSwift-extension-configuration-general-configuration)

		- [2.1.4.2 LeanSwift Extension Configuration – Warehouses](#leanSwift-extension-configuration-warehouses)

		- [2.1.4.3 LeanSwift Extension Configuration – Reason Codes](#leanSwift-extension-configuration-reason-codes)

- [2.2 PROCESS](#process)

	- [2.2.1 RMA Creation (Return) – Magento Admin](#rma-creation-(return)–magento-admin)

		- [2.2.1.1 RMA Creation – Magento Admin](#rma-creation-magento-admin)

		- [2.2.1.2 RMA Synchronization](#rma-synchronization)

		- [2.2.1.3 M3 Processing – Return](#m3-processing-return)

	- [2.2.2 RMA Creation (Exchange) – Magento Admin](#rma-creation-(exchange)-magento-admin)

		- [2.2.2.1 RMA Creation – Exchange](#rma-creation-exchange)

		- [2.2.2.2 RMA Synchronization](#rma-synchronization)

		- [2.2.2.3 M3 Processing of Exchange](#m3-processing-of-exchange)

[3.0 APPENDIX A – Status mapping](#appendix-a-status-mapping)


# GENERAL INFORMATION

## 1.1 System Overview

_ **LeanSwift eConnect for Infor M3** _ provides a powerful, seamless integration between Magento and Infor M3 ERP. The product consists of a base Magento extension that extends standard Magento functionality and offers several transactions to ensure your eCommerce websites contain up-to-date information from your M3 ERP. There exist a number of optional add-on extensions too for additional functionality

_ **LeanSwift eConnect for Infor M3** _ is available for Magento Open Source and Magento Commerce and for Infor M3 version 7.x and above. It is also compatible with multi-tenant cloud editions of Infor M3 (Cloudsuite).

_ **LeanSwift eConnect for Infor M3** _ employs a layered architecture to allow flexibility in supporting different versions of Magento and Infor M3 and to allow independent upgrades.

## Architecture

#

Prior to version 19.1.0, the product architecture included LeanSwift eLink as the integration/interfacing application for the Magento extension to communicate with Infor M3.

Version 19.1.0 includes the following:

1. Infor ION as the integration platform, an alternative to LeanSwift eLink  
2. Replace CRON jobs that pull information for syncing data between M3 and Magento/eConnect with event-based data push from M3 via ION/Eventhub/MEC  
3. Use ION REST API framework to make M3 API calls 

The new version will coexist with the older version of eConnect which uses LeanSwift eLink and all new installations of eConnect have the ability to choose the connection protocol to M3, that is, either eLink or ION.

###

### Architecture with LeanSwift eLink

###

![](RackMultipart20210209-4-1hab68o_html_aa3e621d5e06587e.jpg)

###

### Architecture with ION for multi-tenant Cloud M3

###

![](RackMultipart20210209-4-1hab68o_html_1a380fb028ca706a.jpg)

The add-ons for LeanSwift eConnect provide extended functionality over the standard features available on eConnect Core.

These add-ons can, if necessary, be modified, and new add-ons can be added to fulfill specific customer requirements.

**User interface**

During setup, the Magento Admin panel is used to configure which transactions that should be used and how they should function. There is also additional configuration within the Connector to support the transactions.

**Validated versions**

Magento Open Source 2.3.1

Magento Commerce 2.3.1

Infor M3 13.4

## 1.2 Points of Contact

### 1.2.1 Information

This document and the software it describes are provided by LeanSwift Solutions Inc. For additional information regarding support, licensing, functionality etc. please contact LeanSwift Solutions Inc via contact form at [http://www.leanswift.com](http://www.leanswift.com/)or email info@leanswift.com

## 1.3 Organization of the Manual

This manual is not intended to cover any standard Magento functionality or user experience. The Magento user experience is customized and slightly different in each eCommerce implementation – though the general workflow is similar.

[Section 2](#_heading=h.3o7alnk) provides the detailed setup &amp; functionality of the LeanSwift RMA add-on.

## 1.4 Acronyms and Abbreviations

ERP – Enterprise Resource Planning

RMA – Return Merchandise Authorization

1.
# RMA ADD-ON

### 2.0.1 Summary

The _RMA_ (Return Merchandise Authorization) module extends the standard Magento Enterprise functionality for managing Customer Returns by providing full integration to Infor M3 ERP. **This add-on is available only for Magento Commerce**.

RMAs can be defined in several different ways. Within eConnect the following terms have been applied:

- **Return** – Generally these are for product that was incorrectly purchased (but the goods are undamaged)

- **Claim** – Generally these can be defined as some damage has occurred to purchased products. However, 2 types of claims need to be supported:

    - Stock to be returned
    - Stock not to be returned

- **Exchange** – could be either a Return or Claim, but on top of bringing back one product - a new sales order to ship out the exact same product as a replacement would be created

Depending on the customer specific configuration of M3, a Return and Claim where stock should be returned could be treated the same way.

An RMA can only be created if the original sales order exists within Magento, and is in a &#39;Complete&#39; status. The current date must also be within the valid RMA period as specified within the LeanSwift extension configuration (see section [**2.1.4.1**](#_heading=h.z337ya) of this manual for further details).

In this manual, the process to create the following RMA types are illustrated:

1. RETURN
2. EXCHANGE

The process to create a CLAIM (Stock return or not) is exactly the same as 1) – the only difference is the M3 order type used, and with that possibly the behavior of the transaction in M3.

Please note that within Magento – the process is exactly the same for creating a **Claim** as well as an Exchange. The only difference is that different selections are being made for the &#39;Reason to Return&#39; and &#39;Resolution&#39; values during the step where products are added to the RMA.

The main difference between the various types of RMAs can be found within M3, and the degree of difference can vary between M3 installations based on system configuration.

### 2.0.2 Assumptions/Limitations

1. The RMA add-on requires Magento Commerce

1. The RMA add-on requires LeanSwift eConnect Magento extension

1. The M3 OIS390 functionality is not used as it does not automatically provide for either:

- Return Header creation
- The connection of header and line charges

1. For the RMA configuration in M3, it is recommended that a Customer order type with Order category &#39;1&#39; and &#39;Nmf&#39; &#39;1&#39; is used. This way (together with appropriate settings on the Dispatch policy) it&#39;s possible to ensure that the RMA created in M3 stops in a status &#39;44&#39;, and in this way – no quantity is automatically received in the system.

1. Exchanges are defined as the return &amp; replacement of the exact same item, quantity &amp; price, where no fees associated with the original are refunded – and no additional shipping is charged.

1. Partial receipts of RMAs (i.e. 2 EA requested to be returned but only 1 EA received) must be handled as a &#39;report complete&#39; receipts within M3, i.e. the delivery line should not be left open with any quantity pending following the receipt.

1. If an order type is used that moves the order all the way to &quot;received&quot; (66) status upon creation, it&#39;s key to use the &#39;Picking Correction&#39; option to adjust the received quantity prior to syncing with Magento.

## 2.1 CONFIGURATION

The configuration for RMAs is made up of two parts – the standard Magento setup and the LeanSwift-specific setup.

### 2.1.1 Standard Magento Configuration - General

The general standard Magento configuration can be found under _Stores \&gt; Configuration \&gt; Sales \&gt; Sales_.

![](RackMultipart20210209-4-1hab68o_html_9ef59dd4a73d2e20.png)

The options include whether or not RMAs should be possible to create from the front-end, whether RMAs are enabled on product level and whether or not to use the address for the store for RMAs. If the last setting is set to &#39;No&#39;, the address to use must be filled in:

![](RackMultipart20210209-4-1hab68o_html_6fc672f120f9fca2.png)

### 2.1.2 Standard Magento Configuration – RMA Item Attributes

Another key setup for the RMA process is the definition of what Magento refers to as &#39;RMA Item Attributes&#39;. These attributes are the classifications used during addition/editing of RMA lines to indicate what&#39;s wrong with each product and what the desired course of action for each is.

The RMA Item Attribute configuration can be accessed via _Stores \&gt; Attributes \&gt; Returns_

![](RackMultipart20210209-4-1hab68o_html_82b02bb044840a42.png)

With the installation of LeanSwift&#39;s Magento RMA Add-on, the required Attribute codes &amp; values are added to your Magento installation. The following Attribute codes &amp; values are added:

| **Attribute ID** | **Values** | **Comment** |
| --- | --- | --- |
| resolution | ReturnClaim
 Claim-NonStock
 Exchange | Represents the four RMA types available |
| reason | \* dynamic \* | Holds the M3 reason codes values for the installation in question (i.e. CRS103) |

### 2.1.3 Standard Magento Configuration – Product Setup

The key setting for each product is whether RMAs are enabled for the product in question. The options are &#39;Yes&#39;, &#39;No&#39; or to use the general configuration mentioned in section 2.1.1.

![](RackMultipart20210209-4-1hab68o_html_beacbe2acf56b66f.png)

### 2.1.4 LeanSwift Extension Configuration – RMA

The LeanSwift specific settings related to RMA can be found under _LeanSwift \&gt;Add-ons\&gt; Returns_.

![](RackMultipart20210209-4-1hab68o_html_42049784fe094c0d.png)

![](RackMultipart20210209-4-1hab68o_html_ddd7ef349aa8d79c.png)

The four groups of RMA parameters are covered in the following four sections.

#### 2.1.4.1 LeanSwift Extension Configuration – General Configuration

This group contains settings to define the valid RMA period, and for which M3 customer order type that should be used for each type of RMA.

![](RackMultipart20210209-4-1hab68o_html_d97f9af89e173cc7.png)

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

      1.
#### 2.1.4.2 LeanSwift Extension Configuration – Warehouses

This group allows for a mapping to be created that will ensure a different warehouse for the RMA transaction is used depending on which country the original order was delivered to( **CHECK** ).

![](RackMultipart20210209-4-1hab68o_html_eb084bcbabc4dddd.png)

#### 2.1.4.3 LeanSwift Extension Configuration – Reason Codes

This group contains mappings between the M3 reason codes &amp; RMA type. For each mapping, it&#39;s also possible to control whether the reason code is usable by the end-customer from the front-end or not.

Please note that this mapping affects the front-end behavior only in the way that if &#39;RETURN&#39; for example is selected as the _Resolution_ – only those RMA codes that here have been associated with that RMA type are available for the end-customer to select. This same restriction is not available within Magento Admin.

The values on &#39;RMA Code&#39; are dynamically (for each session) retrieved [and cached for each session] from &#39;&#39; (CRS103) in M3.

![](RackMultipart20210209-4-1hab68o_html_2398da34dcc9f35c.png)

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

![](RackMultipart20210209-4-1hab68o_html_b83e09c20dbb6e04.png)

#### 2.2.1.1 RMA Creation – Magento Admin

An RMA can from within Magento Admin be initiated in two different ways.

**From Original Order**

Opening up the details of the original sales order reveals a &#39;&#39; button in the upper left corner:

![](RackMultipart20210209-4-1hab68o_html_8ffee67341be2f64.png)

**From RMA Grid**

The RMA grid is accessed via _Sales \&gt; Operations \&gt; Returns_. In the upper right-hand corner of the RMA grid, the &#39;New RMA Request&#39; button can be found.

![](RackMultipart20210209-4-1hab68o_html_820e3b3d49a634f.png)

From within Magento Admin, both of the above options brings the user to the same starting point for creating a new RMA transaction.

**General Information**

The first panel contains general information that applies to the entire RMA.

1. Request details with the original Magento sales order number, Customer name &amp; e-mail and an optional additional contact e-mail.
2. The Customer&#39;s shipping address.
3. The return address per the configuration in Magento.

![](RackMultipart20210209-4-1hab68o_html_1e07f0736177cb83.png)

**RMA Items**

The detailed panel is where the actual products to be returned are added. This is done via the &#39;&#39;+Add Products&#39; button in the upper right-hand corner.

![](RackMultipart20210209-4-1hab68o_html_4bee6b42cde6ddfb.png)

This action reveals a list of products eligible to be added to the RMA.

![](RackMultipart20210209-4-1hab68o_html_7e2da22f0351b9ab.png)

**1)** Check the selection boxes for each product that should be added to the RMA (information to the right indicates the SKU, sold price and quantity that remains possible to return).

**2)** Pressing the &#39;+Add Selected Product(s) to RMA&#39; will bring up the next panel where the final details for the RMA can be completed.

![](RackMultipart20210209-4-1hab68o_html_48a8cbcf3948c12a.png)

**1)**_Requested Qty_ refers to the quantity per line item that the customer is requesting to add to this RMA transaction.

**2)**_Reason to Return_ refers to which reason code [dynamically retrieved from M3] best describe why the RMA transaction is being created for this product.

**3)**_Resolution_ refers to the requested action on this RMA (i.e. Return, Claim, Claim-NonStock or Exchange).

**Please note** that since each _Resolution_ corresponds to a different order type in M3 – all products on a RMA transaction must have the same _Resolution_ value.

**4)** Once all the above information have been entered – the RMA is created by pressing the &#39;Submit RMA&#39; button.

The same screen with all the completed information necessary to create the RMA:

![](RackMultipart20210209-4-1hab68o_html_c976ffa191668f0a.png)

Once the RMA has been submitted, the user is returned to the RMA grid with a confirmation message that the RMA has been successfully created, and the first transaction in the list is the latest RMA added.

The status of a new RMA is always &#39;Pending&#39;.

As part of the LeanSwift RMA add-on, two new columns have been added to the RMA grid – &#39;Temp Order#&#39; and &#39;Final Order#&#39;. The &#39;Temp Order#&#39; is the batch order number from M3 (OIS275), and the &#39;Final Order#&#39; is the actual [final] customer order number assigned by M3 once the transaction has been successfully added.

![](RackMultipart20210209-4-1hab68o_html_931321dcc3353162.png)

#### 2.2.1.2 RMA Synchronization

The create RMA can [just like a sales order] be synchronized over to M3 in two different ways – manually or automatically (via a cron job).

**Manual Sync**

The manual sync is initiated via the RMA transaction grid:

![](RackMultipart20210209-4-1hab68o_html_27b85f0022e5bb8a.png)

Once the synchronization has completed, the result is indicated by the message at the top of the screen (1). The RMA transaction is also updated:

**Temp Ord#** : A value is received in this field (M3 Temporary/Batch order number) once the sync has successfully initiated the order creation within M3. Even if there are issues during order creation in M3 so that the order is stopped in &#39;Batch Customer Order. Open&#39; (OIS275) – this value is still updated to indicate the communication &amp; synchronization with M3 was successful.

**Final Ord#** : This field represents the actual final customer order number assigned by M3. Once this field is populated, this indicates that the complete synchronization for the transaction completed successfully.

**Status** : The RMA status is always updated to &#39;Authorized&#39; once the RMA has been fully synchronized over initially to M3. For further details on the Status values, please refer to the Appendix of this document.

![](RackMultipart20210209-4-1hab68o_html_cfaf35abbeaa4ea3.png)

**Cron Sync**

The synchronization via the available cron job works exactly the same way as the Manual Sync described above. The RMA Sync cron is configured following the same standard Linux rules as any of the other cron jobs.

![](RackMultipart20210209-4-1hab68o_html_e4a10631d8c8a8eb.png)

**ION version:**

The difference between ION &amp; eLink version is that, order have to be synced manually in elink whereas in ION version, BOD updates the order status

We also have an additional functionality which is importing RMA config using import option unlike the cron option in elink version

![](RackMultipart20210209-4-1hab68o_html_1b0db46c5febf848.png)

.

Once user clicks on Import button, RMA configuration will be imported from M3.

#### 2.2.1.3 M3 Processing – Return

\*\* Please Note \*\*\*

The processing of the Return transaction in M3 that&#39;s described in this section can vary from customer to customer, as there are a multitude of different ways to configure both customer order types and dispatch policies. Depending on the configuration of these in M3, slightly different variations of this process can be achieved.

As a reference and background to the example in this document, the following key settings on _Customer order type (OIS010)_ and _Dispatch policy (MWS010)_ are used. These represent a process that some of LeanSwift&#39;s customers employ, and that is representative for how we feel the RMA transactions should be managed in M3.

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

With the setup described above, the Return transaction is in M3 created and stopped in a status &#39;44&#39; (Out to pick). For a Return, this signifies that the Return is pending receipt.

![](RackMultipart20210209-4-1hab68o_html_aeee3e28f5aceae1.png)

To illustrate the capabilities of eConnect&#39;s RMA sync, this Return will in this example be processed in two steps. The business scenario here being that the customer (for size reasons for example) had to ship the two products that are being returned in different packages. With this in mind, an RMA must be possible to process in multiple steps.

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

**Please note!**

The pick reporting (receipt) of each individual picking list line must be complete, and not left partially open as M3 allows. This should in most instances make perfect business sense in that if a customer says they will return 3 EA of an item, and only 1 EA is received – then for whatever reason they decided to only return 1 EA instead of 3 EA and someone would reach out to the customer and confirm. If it&#39;s then found that additional units are on the way – the RMA line should not be reported until the full quantity expected has been received.

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

This is the original picking list, where 2 EA of both products are expected to be returned:

![](RackMultipart20210209-4-1hab68o_html_9eeb24e0c41a3dfb.png)

The first pass at receipt reporting

![](RackMultipart20210209-4-1hab68o_html_5d1f7d2294390adc.png)

The above action will receive 1 of 2 EA for the first line and close it for further processing (signified by &#39;1&#39; in the Com (_Complete_) field).

Following the _Confirm All_ action, the order will look as follows [once M3&#39;s auto jobs have finished processing], meaning that the second line (product 200200) is then still expected to be received at at later time:

![](RackMultipart20210209-4-1hab68o_html_d4ca0d48107debaa.png)

A sync with Magento and verification of the RMA transaction in Magento shows it as &#39;Return Partially Received&#39;:

![](RackMultipart20210209-4-1hab68o_html_7e09ae2d9778aec1.png)

Looking at the RMA lines, this is then simply due to the fact that one line at this point has been completely returned (status &#39;Return Received&#39;) and the second line hasn&#39;t been received at all.

![](RackMultipart20210209-4-1hab68o_html_91bd2216ed684720.png)

As a final step, the complete receipt of the second line is performed within M3:

![](RackMultipart20210209-4-1hab68o_html_716b158c8d1f2059.png)

Once this has been completed and the RMA synced again in Magento, the final result of the complete receipt reporting can be seen:

![](RackMultipart20210209-4-1hab68o_html_1cd55c2cdaf73068.png)

![](RackMultipart20210209-4-1hab68o_html_86ef9422d64fd055.png)

Once the order in M3 is invoiced and synced again in Magento, the final result and status is received:

![](RackMultipart20210209-4-1hab68o_html_bb637e005ed5914.png)

![](RackMultipart20210209-4-1hab68o_html_af81f089cc7741e4.png)

![](RackMultipart20210209-4-1hab68o_html_8f291c4c99a19b5.png)

### 2.2.2 RMA Creation (Exchange) – Magento Admin

The overall process to create any type of RMA from a Magento front-end is very similar to how it&#39;s handled within Magento Admin when it comes to the overall process. There are however certain details that differ, and this section covers this.

#### 2.2.2.1 RMA Creation – Exchange

An RMA of type _Exchange_ can just like the _Return_ from within Magento Admin be initiated in two different ways. In this section, the Exchange is created from within the original order – which is displayed below. A new RMA of the type Exchange is created in the same as the Return – by pressing the &#39;Create RMA&#39; button in the upper left corner.

![](RackMultipart20210209-4-1hab68o_html_629c61c06d0c6e61.png)

In the step that follows, move to the &#39;RMA Items&#39; section on the left and press &#39;Add Products&#39; in the upper right-hand corner.

![](RackMultipart20210209-4-1hab68o_html_9324f27364939623.png)

On the following screen displayed below, select all the products that should be included in the Exchange. Press &#39;+Add Selected Product(s) to RMA&#39; when done.

![](RackMultipart20210209-4-1hab68o_html_3b16e6706f35f3dc.png)

In the next step is really where the determination of what kind of RMA this transaction will become is done (please refer to screen shot below). Enter how many of each product that should be included on this RMA in the &#39;Requested Qty&#39; field **(1)**, what the reason for the return is in the &#39;Reason to Return&#39; field **(2)** – and finally what the requested resolution (i.e. type of RMA) is in the &#39;Resolution&#39; field **(3)**.

Please note! That the above information must be entered for all products that are listed on this screen. If one of the fields are left blank – Magento will require input and the following message is displayed to the user:

![](RackMultipart20210209-4-1hab68o_html_9f298cd7229268cb.png)

If at this point the customer would change their mind and not want to include one or several of the products on the RMA – simply use the &#39;Delete&#39; option to the right of the applicable line to remove it from the RMA.

Once all this information has been entered – press &#39;Submit RMA&#39; **(4)** to complete the RMA creation.

![](RackMultipart20210209-4-1hab68o_html_bede398957127df4.png)

The new RMA will show up in the RMA grid that&#39;s displayed as the next step, and the initial status prior to synchronization is &#39;Pending&#39;.

![](RackMultipart20210209-4-1hab68o_html_27b85f0022e5bb8a.png)

#### 2.2.2.2 RMA Synchronization

The Exchange RMA transaction can in the same way as the Return be synchronized Manually or Automatically via a cron job. In this example, only the manual option is covered.

The manual sync is also for the Exchange performed directly from within the RMA grid. Mark the selected transaction/transactions to be synced, select &#39;Sync with ERP&#39; as _Action_ and press &#39;Submit&#39;:

![](RackMultipart20210209-4-1hab68o_html_27b85f0022e5bb8a.png)

A confirmation is received, in this example that the order was successfully created in M3 – and the _Status_ is also updated accordingly. If the RMA was successfully added in M3, the actual M3 order number will also be displayed in the &#39;Final Ord #&#39; field.

![](RackMultipart20210209-4-1hab68o_html_c08edddd001f57fa.png)

For further details on the final order# and other fields on this screen, please refer to section [**2.2.1.2**](#_heading=h.3whwml4) earlier in this document.

#### 2.2.2.3 M3 Processing of Exchange

Please refer to section **2.2.1.3** for some comments regarding the processing of RMAs in general in M3. It&#39;s true also for the Exchange that there are multiple different ways this can be configured within M3, so what is covered in this section is one possible way to handle this.

With regards to Exchanges, a few things are specifically worth mentioning. Also please refer to section **2.0.2** for applicable Assumptions/Limitations.

- An Exchange is defined as the exact replacement (one-to-one) of a product at the same price.
- For an exchange, there are always two orders generated &amp; processed within M3:
  - One _Credit_ order to manage the return of the product.
  - One _Debit_ order to manage the dispatch of the new replacement product to the customer.
- The Debit &amp; Credit order types are defined within the LeanSwift Magento extension configuration (see section [**2.1.4.1**](#_heading=h.z337ya) for more details).

With the M3 setup for this example, the resulting Debit order in M3 is created in a status &#39;44&#39; (i.e. &quot;Pending receipt):

![](RackMultipart20210209-4-1hab68o_html_1c2036d0336b046c.png) To process through the receipt in this case, a &#39;Confirm Issues&#39; is performed for the applicable number of units (just one in this example). Please note that also here it is possible to receive fewer that expected, as long as the delivery line is closed.

The Exchange will move to a status of &#39;66&#39; (Received) after this.

![](RackMultipart20210209-4-1hab68o_html_825b9310a1c2d66c.png)

The final step [for any RMA in M3] is Invoicing. This can be done in a number of different ways, normally in batch and scheduled to run with a certain frequency. It&#39;s also possible to have the order automatically invoice right after it reaches a received (66) status.

To describe the complete process for an Exchange, it&#39;s crucial that this step is performed – and the order synchronized with Magento after that. This final synchronization will check if the transaction is of an Exchange type and if it&#39;s been invoiced. If that&#39;s the case, the final synchronization will generate the _Debit_ order – i.e. the new &quot;normal&quot; sales order that in M3 will be used to ship out the replacement product to the customer.

If manually performed, invoicing is initiated from &#39;CO Invoice. Print&#39; (OIS180). Enter in the sales order number in both the &#39;From&#39; and &#39;To&#39; CO no fields and press _ENTER/NEXT_. The [Credit] Exchange order in M3 will move to status &#39;77&#39; (Invoiced).

![](RackMultipart20210209-4-1hab68o_html_1ae7e39bf3b5747f.png)

Perform one final synchronization (manually in this example, but this would normally be handled automatically by the associated cron job in Magento):

And once the RMA in Magento has reached a &#39;Processed &amp; Closed&#39; status, the final Debit order to ship out the replacement product in M3 has been generated.

![](RackMultipart20210209-4-1hab68o_html_af81f089cc7741e4.png)

The Debit order can be found by looking for one of the last &quot;normal&quot; sales orders based on the applicable number sequence defined in M3. In this case, no additional sales orders have been processed since the one used to initiate this example – so it will be the next number following the original sale orders (which was 0001113237) i.e. **0001113238**.

![](RackMultipart20210209-4-1hab68o_html_de767a36090ebb6d.png)

This then concludes the Exchange process. The Debit order will be processed following whatever routines are configured for that order type in M3, which [since it&#39;s a separate order type] can be different from other types of sales orders.

1.
# APPENDIX A – Status mapping

In order to properly handle the case where only a part of an RMA should be received, the synchronization between M3 and Magento needs to be based on line level order statuses.

LeanSwift&#39;s synchronization within eConnect ensures that that the RMA line status is updated correctly based on the M3 order line status, and the RMA header status is then updated appropriately by Magento.

![](RackMultipart20210209-4-1hab68o_html_21709e6ec9569183.jpg)

**User Manual Page** 5
