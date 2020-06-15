![](RackMultipart20200604-4-58zvro_html_5749ee4c7fdc9cd3.png)

# **USER MANUAL**

**LeanSwift eConnect** 

**for Infor M3 &amp;Magento** 

**Part II – Standard Transactions &amp; Processes**

**Product Version 20.2.0**

**ECONNECT 20.2.0 USER MANUAL**


# TABLE OF CONTENTS

- [**USER MANUAL**](#user-manual)
- [Table of Contents](#table-of-contents)
- [System Overview](#system-overview)
  - [Architecture](#architecture)
  - [Points of Contact](#points-of-contact)
  - [Organization of the Manual](#12-organization-of-the-manual)
  - [Acronyms and Abbreviations](#13-acronyms-and-abbreviations)
- [Standard Transactions](#20-standard-transactions)
  - [Summary](#summary)
  - [Assumptions/Limitations](#assumptionslimitations)
- [Product Setup &amp; Information](#product-setup-amp-information)
- [Price](#price)
  - [Single Price List](#single-price-list)
  - [Customer Specific Price](#customer-specific-price)
- [Inventory](#inventory)
  - [Inventory Value Selection](#inventory-value-selection)
  - [InventorySync](#inventorysync)
- [Customer Registration](#customer-registration)
- [Customer Addition/Synchronization](#customer-additionsynchronization)
- [Customer Information Sync](#customer-information-sync)
  - [Transaction Overview](#transaction-overview)
  - [Synchronization Process](#synchronization-process)
- [Order Creation](#order-creation)
  - [Transaction Overview](#transaction-overview)
  - [Order Creation –B2B](#order-creation-b2b)
  - [Order Creation –B2C](#order-creation-b2c)
  - [ShipComplete](#shipcomplete)
  - [Gift Wrapping](#gift-wrapping)
  - [Credit Card Management](#credit-card-management)
  - [Order Charges](#order-charges)
  - [Line Charges](#line-charges)
- [Order Information](#order-information)
  - [Transaction Overview](#transaction-overview)
  - [Magento &amp; M3 Order Status Relation](#magento-amp-m3-order-status-relation)
- [Shipment](#shipment)
  - [Shipments in Magento](#shipments-in-magento)
  - [Deliveries in M3](#deliveries-in-m3)
  - [Tracking Numbers](#tracking-numbers)
- [Invoice](#invoice)
- [Orderhistory](#orderhistory)

#

# 1.0 System Overview

- **LeanSwift eConnect for Infor M3** _ provides a powerful, seamless integration between Magento and Infor M3 ERP. The product consists of a base Magento extension that extends standard Magento functionality and offers several transactions to ensure your eCommerce websites contain up-to-date information from your M3 ERP. There exist a number of optional add-on extensions too for additional functionality

- **LeanSwift eConnect for Infor M3** _ is available for Magento Open Source and Magento Commerce and for Infor M3 version 7.x and above. It is also compatible with multi-tenant cloud editions of Infor M3 (CloudSuite).

- **LeanSwift eConnect for Infor M3** _ employs a layered architecture to allow flexibility in supporting different versions of Magento and Infor M3 and to allow independent upgrades.

### Architecture

 The part of eConnect functionality dealing with connectivity to Infor OS and

 data processing has been moved out of eConnect extension into a new extension named

 **eConnect-base**.

 From 20.1.0 onward, eConnect will require the eConnect-base extension to function.

 eConnect 20.1.0 is compatible with eConnect-base 2.0.0.

**eConnect-base v2.0.0**

- It provides the connectivity to eLink and/or Infor systems with the use of a generic function which decides whether to call the eLink / ION APIs based on the M3 Connection Protocol chosen in the backend
- Acts as the communication layer for RabbitMQ Message consumption
- Acts as a core module for following LeanSwift Magento Extensions

  - eConnect
  - IDM
  - Supplier Portal
- eConnect add-ons depend on both eConnect-base and eConnect. eConnect and its Add-ons works only with eConnect-base configured

- IDM can now work without eConnect

econnect-user-manual-ion-part2

**Architecture with ION for multi-tenant Cloud M3**



<kbd><img alt="architecture-with-ebase" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/architecture-with-ebase.png"></kbd>



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
- Initial Load / Import
- BOD Mapping
- Manual Sync for Customer
- Manual Sync for Product
- Manual Sync for Order

### User Interface

During setup, the Magento Admin panel is used to configure which transactions should be used and how they should function.

### Validated Versions

- Magento Commerce 2.3.4
- Magento Open Source 2.3.4
- Infor M3 16.1
- LeanSwift eLink 7.6.3
- RabbitMQ 3.8.3
- Infor ION Grid 12.0.2.0.20180308-135417.2
- ION Desk 12.0.0

## Points Of Contacts

This document and the software details are provided by LeanSwift Solutions Inc. For additional information regarding support, licensing, functionality etc. please contact LeanSwift Solutions Inc via contact form at [http://www.leanswift.com](http://www.leanswift.com/)or email info@leanswift.com

## Organization Of The Manual

This manual is not intended to cover any standard Magento functionality or user experience. The Magento user experience is customized and slightly different in each eCommerce implementation – though the general workflow is similar.

Section 2 of this manual describes the various standard transactions included in the base offering of LeanSwift eConnect for Infor M3.

## Acronyms And Abbrevations

ERP – Enterprise Resource Planning B2B – Business to business

B2C – Business to consumer

RMA – Return Materials (Merchandise) Authorization

[Go to Top](#table-of-contents)

# Standard Transactions

LeanSwift eConnect comes with a number of standard transactions included. This section provides a detailed walkthrough of each of them.

Please refer to **Part I** of the User Manual for the required configuration behind each of the transactions.

   
### Summary

LeanSwift always uses two key principles as guiding lights when we develop new features for eConnect.

- Infor M3 is the system of record.
- Always adhere to Magento's core standard functionality wherever possible.

This sometimes leads to certain limitations being imposed due to the simple fact that Infor&#39;s M3 ERP by nature is a far more versatile and complex system by definition being an ERP, especially in areas such as order processing, dispatch management etc.

There are of course also examples where Magento&#39;s functionality is more specific, and similar limitations have to be put in on the M3 side. Gift cards, Coupons, Cross &amp; Up-sells are great examples of functionality that within Magento is far more tailored for a B2C environment.

    
### Assumptions And Limitations


This section provides a listing of all key assumptions that form the basis for LeanSwift eConnect 20.1.0

- Order changes

If any changes at all need to be made to an order placed via Magento, the order needs to be cancelled and re-entered. The corresponding order in M3 needs to be cancelled separately. There is no validation within Magento that the order in M3 is eligible cancellation/change, this needs to be manually verified.

- Additional charges

No additional charges (such as Freight) are added within M3 once the order has been created. If this is done, eConnect won&#39;t synchronize this additional amount to Magento and as a result the invoice amount will differ between the two systems. Furthermore – if the freight isn&#39;t added upfront within Magento and the order is paid via credit card, the freight will not be included in the amount that&#39;s authorized against the customer&#39;s card.

[Go to Top](#table-of-contents)

  
## Product Setup &amp; Information

From a product perspective, eConnect relies on the &#39;External Item#&#39; value. This value must be equal to the corresponding M3 item number for all of the eConnect transactions to function as they should.

<kbd><img alt="product set up information" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/product-setup-information.png"></kbd>

The Product Information transaction offers the ability to sync select fields from the M3 Item

master (MMS001/MITMAS) to Magento&#39;s Product attributes.

The synchronization is initiated when there is change on the product&#39;s attribute/details in M3. Whenever there is a Add/Update/delete operation\* performed on the product in M3, Sync.ItemMaster, Sync.LS\_ItemMasterDetails BOD gets generated. The BOD is received by magento and the new information gets updated to the respective product.

\*Refer smart rules to know which change in field triggers BOD.

With this transaction it is possible to keep in sync discrete values within M3&#39;s Item Master (MMS001/MITMAS) with Magento&#39;s product attribute. Examples of applicable fields are Name, Description and any of the item categorizations such as Item Group, Product Group etc.

### Manual Sync Process

This feature enables manual sync of Products with M3. We can choose multiple products that require sync with M3 and choose &#39;Sync Items with M3&#39;. Clicking on Manual sync triggers &#39;Show&#39; BODs. Once the BOD reaches Magento, the information gets updated in respective tables in the DB. Multiple products can be chosen to sync with M3.

<kbd><img alt="product set up information" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/manual-sync-process.png"></kbd>

[Go to Top](#table-of-contents)

  
## Price

Depending on the situation and configuration within Magento and M3, two different types of prices that serve two different purposes can be synchronized:

- Price from a single M3 price list (normally used for a MSRP/ListPrice)
- Customer specific price for certain product

    
### Single Price List

This price synchronization is normally used to bring over a single MSRP/List price value per product from M3 to Magento. This is in Magento stored in the regular &#39;Price&#39; field within the Product Information \&gt; Prices section.

A different M3 price list can be defined for each website View via Magento Admin.

The _Price list_ &amp; _Currency_ that should be used are defined [per website View or on Default Config] within the **Basic Data** section of the eConnect configuration.

<kbd><img alt="product set up information" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/single-price-list.png"></kbd>


The item price in M3 for this example in price list &#39;02&#39; is $59.00:

<kbd><img alt="Price list in m3" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/single-price-m3.png"></kbd>

Whenever there is an Addition/Update/deletion of price in M3, Sync.LS\_ItemMasterDetails BOD gets triggered and the same gets updated in magento.

Once the information is received, the correct price from M3 is also displayed within Magento Admin.

<kbd><img alt="Price in magento" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/single-price-magento.png"></kbd>

    
### Customer Specific Price

The customer specific price transaction is normally used in a B2B scenario, when individual negotiated prices for different customer/item combination need to be displayed within the web shop.

Whether or not to enable this transaction is controlled within the LeanSwift Magento extension

LS > eConenct_ION > Configuration > Price Synchronization

<kbd><img alt="Price Synchronization" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/price-synchronisation.png"></kbd>

1. Setting &#39;Enable&#39; to &#39;Yes&#39; enables the Customer specific price transaction in frontend
2. Setting &#39;Enable in Admin&#39; to &#39;Yes&#39; enables the Customer specific price transaction in backend.

Customer specific price is carried by Sync.LS\_PriceList BOD. Like other BOD&#39;s this BOD gets triggered when there is an update or new entry in OIS017 table in M3, provided the corresponding customer has price associated to him

Please note that the price that is displayed by default upon product detail page load is the &#39;Price&#39; value for the Store view in question from within the product details in Magento. In a Fashion environment with Styles &amp; SKU&#39;s (Configured and Simple products connected in Magento), the detailed SKU specific price won&#39;t be displayed in a product detail page until all applicable options have been selected by the user.

For a Customer specific price, the price displayed on the product detail page is always the price for 1 unit of the product in question.

User can choose to send or not, Price to M3

<kbd><img alt="Sales" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/sales.png"></kbd>

When the &#39;Allow Item Price&#39; is set to Yes, Price will be sent to M3 from magento

When the &#39;Allow Item Price&#39; is set to No, Price will not be sent to M3 from magento

[Go to Top](#table-of-contents)

  
## Inventory

Inventory synchronization with M3 is done via Sync.LS\_ItemStock BOD.

    
### Inventory Value Selection

eConnect now offers a possibility to select which quantity value from M3 should be used as &#39;Quantity&#39;. The setting can be found under the &#39;Inventory Synchronization&#39; section of the eConnect configuration:

<kbd><img alt="Inventory Synchronization" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/inventory-syncronization.png"></kbd>

The available options are:

1. AllocatableNet
2. On-handbalance
3. Availableinventory

Where &#39;Allocatable Net&#39; is the default setting with the eConnect install.

    
### Inventory Sync

When there is an Add/Update/delete in stock for an item in M3, Sync.LS\_ItemStock BOD gets generated. If there is a corresponding item in Magento, the stock gets updated based on the BOD information.


[Go to Top](#table-of-contents)

  
## Customer Registration

The Customer registration feature was specifically added to cater for a B2B scenario where new customer sign-ups are accepted from the front-end.

The functionality is enabled via _LS \&gt; econnect-ION \&gt; Configuration \&gt; Customer General Configuration \&gt; ERP Customer Registration_:

<kbd><img alt="Customer general configuration" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/customer-general-configuration.png"></kbd>

1. &#39;Enable Registration&#39; set to &#39;Yes&#39; enables the functionality.
2. &#39;Customer Template Id&#39; contains the value of the M3 customer number that the new

customer creation should be based on.

Please note that the &#39;Customer Template Id&#39; field is only visible when &#39;Enable Registration&#39; is set to &#39;Yes&#39;.

For each successful customer signup from the front-end, a new customer record will be added within both Magento and M3. The customer in Magento is tied to the M3# via the External customer# as usual.

Within M3, the customer is created in a preliminary status (10). The process to approve the customer within M3 is manual, i.e. a user would [outside of the system] perform any required validations, credit checks etc. of the new customer. Once completed and if the new customer is approved as a new B2B account – the status would manually be changed to &#39;20&#39; within M3.

On the Magento front-end, the customer will be able to log in, shop around, add products to the cart and save the cart without being approved. They will however not be able to complete the check-out process and place the order unless the corresponding M3 customer number has been approved first, as a real-time check of the M3 customer status is performed.

[Go to Top](#table-of-contents)

 
## Customer Addition/Synchronization

The Customer Addition feature is designed to fetch the customers from M3 into Magento.

The functionality is enabled via _LS \&gt; eConnect-ION \&gt; Configuration \&gt; Customer Addition/Synchronization_:

<kbd><img alt="Customer addition/synchronization" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/customer-addition-sync.png"></kbd>

1. &#39;Enable&#39; set to &#39;Yes&#39; enables the Module.
2. &#39;Enable Customer sync&#39; set to &#39;Yes&#39; to enable Customer Sync
3. &#39;Enable Customer Addition&#39; set to &#39;Yes&#39; to enable Customer Addition
4. &#39;Customer Group Id&#39; contains the value of the M3 customer group that the

customer creation is based on.

1. &#39;New Account Email Notification&#39; This feature will send an e-mail notification when a new customer gets added into magento from M3
2. Customer Master Mapping
3. Customer Address Mapping

This feature imports all the customers from M3 into Magento irrespective of customer status in M3. A default email address is created if there is no email address associated to a customer in M3. Customer&#39;s email address will get updated only once from dummy email to valid email address. Once valid email address([xxx@leanswift.com](mailto:xxx@leanswift.com)) gets updated, any further changes to email address will not make an update in our eConnect

When a customer is created in M3, Customer gets added into magento if &#39;Customer Addition&#39; is enabled.

This process triggers Sync.CustomerPartyMaster and Sync.LS\_CustomerDetails.

If customer has addresses added in M3, it triggers Sync.BillToPartyMaster and Sync.ShipToPartyMaster BODs.

[Go to Top](#table-of-contents)

  
## Customer Information Sync

    
### Transaction Overview

This functionality enables customer details and addresses to be synced over to Magento from M3.

In this version, the functionality assumes that the Customer exists in both M3 &amp; Magento as active &amp; approved customers. With this pre-requisite fulfilled, type 1 &amp; 3 of customer address that&#39;s defined within M3 can be synchronized over to Magento.

The following information is available to synchronize between M3 &amp; Magento:

1. Basic&amp; financial customer details from &#39;Customer. Open&#39;(CRS610):

<kbd><img alt="Transaction overview" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/customerdetail-crs610.png"></kbd>

1. Any customer address defined in &#39;Customer. Connect Addresses&#39;(OIS002). Note that only address type 1 and 3 will be synced

<kbd><img alt="Customer address" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/customer-address.png"></kbd>

    
### Synchronization Process

The synchronization of the customer information is done with the help of multiple BOD&#39;s.

The Customer details (basic- &amp; financial data) (OCUSMA) comes from Sync.CustomerPartyMaster and Sync.LS\_CustomerDetails

The Customer Addresses (OCUSAD) comes from Sync.BillToPartyMaster and Sync.ShipToPartyMaster

**Customer Master Details:** Whenever there is an update in OCUSMA table i.e CRS610, Sync.CustomerPartyMaster and/or Sync.LS\_CustomerDetails gets triggered. When there is a corresponding customer in Magento, the changes will get synced from M3 to Magento via BOD&#39;s

**Customer Addresses Mapping** handles the synchronization of address of type 1 &amp; 3 from Customer. Connect Addresses (OIS002), OCUSAD.

Similar to CustomerPartyMaster BOD, when there is Add/Update operation in OCUSAD,

Sync.CustomerPartyMaster, Sync.BillToPartyMaster and Sync.ShipToPartyMaster BODs triggers\* and the same gets synced into Magento

Depending on which address/detail gets updated in M3, corresponding BOD gets triggered.

The **Address** tab within the **Customer Information** in Magento has two additional fields to store the origin of the address in M3.

**ERP Address Type** contains values such as:

_DEFAULT_: The main address from the Customer master (CRS610/E) is now not available in ION version.

_01\_DELIVERY_: The shipping address from &#39;Customer. Connect Addresses&#39; _03\_INVOICE_: The billing address from &#39;Customer. Connect Addresses&#39; (OIS002)

**ERP Address ID** contains the actual sequence#/ID for the address in question as defined within

M3 (also in &#39;Customer. Connect Addresses&#39; – OIS002).

Account information tab saves the Variation ID, BOD Timestamp and BOD ID for future reference.

<kbd><img alt="Synchronization process addresstype1" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/sync-process.png"></kbd>

<kbd><img alt="Synchronization process addresstype3" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/sync-process2.png"></kbd>


### Manual Sync Process

This feature enables manual sync of customer with M3. We can choose multiple customers that require sync with M3 and choose &#39;Sync customers with M3&#39;. Clicking on Manual sync triggers &#39;Show&#39; BODs. Once the BOD reaches Magento, the information gets updated in respective tables in the DB.

<kbd><img alt="Manual Sync Customers" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/manual-sync-process2.png"></kbd>

[Go to Top](#table-of-contents)

  
## Order Creation

Alongside Price &amp; Inventory, the Order Creation transaction is one of the core transactions within eConnect. LeanSwift have then on top of this added a number of features to be able to better manage the creation of sales orders within M3 when initiated from Magento.

    
### Transaction Overview

There are multiple steps involved in creating an order in M3, and these are covered later on in this section. The B2B order creation section provides details of the order process from both Magento front-end as well as Magento Admin. The differences in the B2C scenarios are discussed in the related sections.

At the beginning of the process, a check is always made to ensure the order hasn&#39;t previously

been created in M3 in order to avoid the risk of duplicates.

The order creation process can be initiated in a number of different ways – both manual and automated background (cron) jobs.

To manually initiate the order creation in M3 following the creation of an order from the Magento front-end (or from within Admin), the action &#39;Sync Order with M3&#39; should be used. This option can be found within the Sales order grid (_Sales \&gt; Orders_).

<kbd><img alt="Transaction overview" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/sync-order-with-m3.png"></kbd>

**Sync Order with M3**

This option performs the steps required to push the sales order from Magento in to M3&#39;s batch order entry. Provided that there are no errors [and with the correct supporting configuration within M3], the order would be created as a final customer order.

The validation within Magento consist of feedback of what the temporary [batch] order number is ( **Temp Ord#** ), the final M3 customer order number ( **Final Ord#** ) as well as the order status ( **Status** ).

This option also creates any new Shipments &amp; Invoices in Magento based on what&#39;s in M3. For more information on status, shipment &amp; invoice synchronization in this version of eConnect, please refer to sections **2.7** – **2.9**.

The verification message displayed to the user also contains a wealth of information [besides the temporary order number] such as

- the final M3 customer order number
- the number of Shipments added in Magento since the last sync
- the number of Invoices added in Magento since the last sync
- the number of tracking numbers added in Magento since the last sync

To schedule order creation via the background jobs, make sure to configure the following cron job to run with appropriate intervals under LS \&gt; eConnect ION \&gt; Configuration \&gt; Cron:

<kbd><img alt="cron setting to send ERP" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/cron.png"></kbd>

    
### Order Creation–B2B

The order creation in a B2B scenario assumes the customer in Magento is already associated with an approved (status 20) M3 customer number via the &#39;External Customer number&#39; connection.

**Please note**

This process can still result in a sales order that&#39;s not fully created within M3. In cases where some additional error/warning is found when the order details are being processed through the batch order entry function – a manual check &amp; validation step (or multiple steps) need to be performed within &#39;Batch Customer Order. Open&#39; (OIS275).

If the order was manually synchronized as described in the previous section, the confirmation message displayed to the user will indicate that the complete order creation in M3 was unsuccessful and direct the user to &#39;Batch Customer Order. Open&#39; (OIS275)

**Order entry-Magento Frontend**

Please note that orders normally are synchronized between Magento &amp; M3 via the background cron job, but that the manual option used in this example can be used whenever needed on individual orders.

In this example, a test customer with e-mail ID [deepthi.tadikamalla@leanswift.com](mailto:deepthi.tadikamalla@leanswift.com)is used. This customer is associated to a test B2B site and to M3 customer# **LEAN000399** :

<kbd><img alt="Customer details" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/order-entry.png"></kbd>


After logging in on the front-end, and order is placed for 1 EA of item 200200 is added to cart. The customer specific price is already applied at this point (based on 1 EA of the item in question):

<kbd><img alt="order addition" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/order-entry-pdt-addtion.png"></kbd>

Proceeding to checkout we at the last step get to order summary information regarding subtotal for items, Shipping &amp; Handling and Tax:

<kbd><img alt="order Placement" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/order-entry-place-order.png"></kbd>

In this example, eConnect has been configured to transfer Sales tax, and a line charge &#39;TAX1&#39; will be used. In the same way, Shipping &amp; Handling should be added as an order header charge using charge ID &#39;SHIP&#39;.

<kbd><img alt="order charges" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/order-charges.png"></kbd>

After pressing &#39;Place Order&#39; at the final step of the checkout process, a confirmation is received

detailing the Magento order#.

<kbd><img alt="order placed" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/order-entry-orderplaced.png"></kbd>

In Magento Admin, the order can now be found in the Order grid (_Sales \&gt; Orders_), and the most recent order is at the top of the list.

<kbd><img alt="orders page" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/order-entry-order.png"></kbd>

To manually initiate the order sync, select the order/orders (1) and under **Actions** on the upper

right hand side of the grid header select &#39;Sync Orders with M3&#39;.

<kbd><img alt="orders page" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/order-entry-order-sync.png"></kbd>

Once a manual synchronization is complete, the user is presented with a confirmation message in the header of the order grid. The confirmation contains information on temporary- &amp; final order numbers as well as whether any shipments or invoices were added to Magento (more details on the Shipment and Invoice sync can be found in sections 2.8 &amp; 2.9).

<kbd><img alt="Temp order number generated" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/order-entry-temp-order.png"></kbd>

The temporary (batch) order number ( **Temp Order #** ) is brought back from M3 as soon as the order has been successfully sent to M3. If some validation fails in M3 that leads to the final order not being fully created, this can be related to missing/incorrect information within M3. As such, the temporary order number is displayed in Magento along with a message to the user to review the errors in M3&#39;s batch order entry (OIS275).

If the order creation progresses successfully [as in the example above], the final customer order number from M3 is also populated and displayed right in the order grid in the **Final Ord #** field.

    
### Order Creation–B2C

Order creation in a B2C environment can be handled in two different ways within eConnect, and they differ with regards to how the Customer is managed from an M3 perspective.

Which Customer approach is used is handled via the eConnect configuration within _LS \&gt; eConnect-ION \&gt; Configuration \&gt; Customer General Configuration_.

**Common Customer**

Common customer is used when all orders from a Store view/Site should be created in M3 under a single Customer number.

The **Create New Customer** parameter is then set to &#39;No&#39;, and the parameter below it ( **Common Customer ID** ) then contains which [common] customer# to use for all orders.

**Discrete Customer**

Discrete customer is the opposite. In this case, each order created within M3 should be added with a unique customer number.

For this scenario, the **Create New Customer** parameter is then set to &#39;Yes&#39;, and the parameter below it (now called **Customer Template ID** ) then contains which M3 customer# to use as a template to create new customers from (via an additional Copy function preceding the creation of each order).

In the Discrete Customer scenario, eConnect always as a first step validates whether the customer has placed an order previously. If so, the already existing customer# is used.

Besides the customer creation step when discrete customer is used in a B2C scenario, the additional parts of the order creation process are the same as for the B2B scenario.

   
### Shipcomplete

The Ship Complete functionality offers customers an option to allow end-customers to during

ordering select to have the entire order shipped &quot;complete&quot;, i.e. in a single shipment.

This functionality is enabled in _LS \&gt; eConnect-ION \&gt; Configuration \&gt; Sales_, by setting **Enable Ship Complete** to &#39;Yes&#39;. If this has been enabled, the customers on the site/store in question will have the option to during the checkout process select &#39;Ship Complete&#39; for their order:

<kbd><img alt="Enable ship complete" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/ship-complete.png"></kbd>


This will with the correct setup in M3 (parameter 290 in &#39;Dispatch Policy. Open&#39; – MWS010/G must be set to &#39;1&#39;) ensure that a picking list isn&#39;t released for the order until all of the lines are fully allocated. To enable this, eConnect will ensure each order line is created with the same &quot;Joint Delivery Code&quot; value:

<kbd><img alt="Joint delivery code added in m3" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/joint-delivery-code.png"></kbd>

    
### Gift Wrapping

The first step in adding this support focuses on the detailed information on order- and/or line level charges for Gift Wrapping, as well as information regarding what type of gift wrapping should be applied.

Magento Enterprise Edition is required to take advantage of the Gift Wrapping functionality in eConnect as Magento Community Edition doesn&#39;t contain any Gift Wrapping functionality.

Within the eConnect configuration (_LS \&gt; eConnect-ION \&gt; Configuration \&gt; Order Charges_), it&#39;s possible to turn on or off the transfer of Gift Wrapping charges to M3 – as well as decide whether any resulting charges should be added as charges or non-stock items.

Pre-requisites

- Gift Wrapping on Order &amp; Product level have been enabled in Magento under _System \&gt; Configuration \&gt; Sales \&gt; GiftOptions_.
- A cost for the Giftwrapping is[optionally]assigned to the products in the &#39;GiftOptions&#39;

section of the Product Information.

- All applicable Gift Wraps are defined in Magento under _Stores \&gt; GiftWrapping_.
- The setup in M3 for the intended solution has been configured (i.e. Header- &amp;Line charges in OIS030/CRS275 or non-stock items inMMS001).

**\*\*** In this version, costs assigned to printed cards in Magento as well as gift wrapping messages are not supported and will as such not be transferred to M3.

For the example in this section, eConnect has been configured to use order header &amp; line charges to represent the Gift Wrapping within M3.

<kbd><img alt="Gift wrap configurations" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/order-charges-gift-wrap.png"></kbd>

Furthermore, at least one Gift Wrap needs to be defined for the website under _Stores \&gt; Gift Wrapping_:

<kbd><img alt="Gift wrap" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/gift-wrapping.png"></kbd>

To illustrate the functionality, an order is placed for two test items.

<kbd><img alt="Gift wrap" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2giftwrap-chargeanditem-.png"></kbd>

In the &#39;View and Edit cart&#39; page, we can choose the gift options:

<kbd><img alt="Gift wrap" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/giftcard-cart.png"></kbd>

Magento offers the ability to gift wrap the entire order and/or individual items only, as well as send a gift receipt and include a printed card with the order. As noted earlier – if the Printed card setup in Magento carries a cost, this cost will in this version not be reflected in M3.

For this example, we&#39;ll add gift wrapping to both the entire order as well as one product on the order:

<kbd><img alt="Giftwrap header and line level charges" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/giftwrap-chargeatheadandline.png"></kbd>


Once the Gift options is chosen, click on &#39;Update&#39; button for changes to reflect on the order. On the Order Review panel, a summary of the order is provided – where the Gift Wrapping for the order and items are shown.


<kbd><img alt="Giftwrap viewcart" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/giftwrap-items.png"></kbd>

Click on &#39;Go to Checkout&#39;, choose the shipping address and shipping method and click &#39;Next&#39;. Choose the payment option and press &#39;PLACE ORDER&#39; in the checkout page yields the confirmation panel with the Magento order#.

<kbd><img alt="Giftwrap viewcart" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/giftwrap-ordernumber.png"></kbd>

Validation of the order within Magento Admin reflects the correct situation as well:

<kbd><img alt="Giftwrap magento" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/giftwrap-magento.png"></kbd>

Order is manually synchronized with M3:

<kbd><img alt="Giftwrap ordersync" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/giftwrap-ordersync.png"></kbd>

<kbd><img alt="Giftwrap temporder" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/giftwrap-temporder.png"></kbd>

A review of the order in M3 validates that the $26.00 order level gift wrap charge, as well as the

$26.00 line gift wrap charge for the  line item are both in place correctly. The name of the Gift wrap charge is also transferred to the name of the corresponding charge.

<kbd><img alt="Giftwrap Charges" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/giftwrap-charges.png"></kbd>

<kbd><img alt="Giftwrap Charges" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/giftwarp-linecharge.png"></kbd>

Should eConnect have been configured to instead use non-stock items, the result in M3 would instead have been the following:

<kbd><img alt="Giftwrap Charges" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/giftwrap-nonstockitem.png"></kbd>

The current logic places the non-stock item for each line-related gift-wrapping charge right after the line it belongs to, and the order total gift wrapping item at the very bottom.

<kbd><img alt="Giftwrap Charges" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/giftwrap-nonstockitem-details.png"></kbd>

The configuration with non-stock items might be preferable should there be a need to info warehousepersonneltoinclude/performcertaingiftwrappinginconnectionwithpicking&amp; packing the order.

   
### Credit Card Management

A key component of any B2C [and most B2B] implementation/s is the processing of credit card payments.

The authorization performed by Magento is transferred over to eConnect without the need to perform any additional reference authorization from within M3.

It&#39;s still possible to configure Magento to perform a &quot;Direct sale&quot;, i.e. to both authorize &amp; capture

the funds as a single step when the order is placed if that&#39;s the desired.

There is no credit card related information (i.e. transaction verification/authorization numbers, security codes, tokens etc.) passed from Magento to M3. All interaction with the payment gateway of choice (any of those supported by Magento), is handled by Magento.

This means that the standard M3 credit card functionality is not utilized.

The single credit card related configuration option within the Lean Swift extension can be found under _LS \&gt; eConnect-ION \&gt; Configuration \&gt; Sales_-Capture Payment online

<kbd><img alt="Credit card management-sales" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/creditcard-management.png"></kbd>

The authorization of the customer&#39;s card takes place as usual upfront when the order is placed.

Once the entire (or part of) the order has been picked, packed, shipped &amp; invoiced – an invoice will be generated within Magento. Once the invoice is created, the capture transaction (depending on the setting above) will be initiated from within Magento.

It is also possible to opt to handle the capture from within M3 via the standard batch process that can be initiated following invoicing of the order. In this case, the above &#39;Capture Payment Online&#39; parameter should be set to &#39;No&#39; within Magento.

    
### Order Charges

Base eConnect comes with support for three types of order charges:

1. Freight (Shipping)
2. Invoice fees
3. Giftwrapping

Each of these are in M3 added as an order header charge (i.e. can in M3 be found within

&#39;Customer Order. Connect Charges&#39; (OIS103).

The following order provides an example of where all these three charges are present within Magento, and how they are represented within M3 (note – the Invoice fee setup is a backend configuration within eConnect):

![](RackMultipart20200604-4-58zvro_html_d6f8e115b964e061.gif)

![](RackMultipart20200604-4-58zvro_html_940d6062000946db.png)

**Freight(Shipping)**

The configuration for which charge ID (defined in &#39;CO Charge. Open&#39; – OIS030) to use for the total freight amount per order is now defined as a configurable charge code.

User can choose to send or not, the shipping charges to M3, which is controlled by a Yes/No option

<kbd><img alt="Freight charge" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/freight.png"></kbd>

The freight (Shipping &amp; Handling) amount within Magento is always invoiced in full on the first invoice issued for the order in question. M3 offers different configuration options for how to invoice freight (and other charges) to for example repeatedly invoice the same freight charge multiple times. Please note that if a configuration within M3 is used that would invoice the same freight charge more than once – the invoice amount in M3 will not correspond to the invoice amount in Magento. The Shipping information/details are available in Sync.SalesOrder BOD.

**Invoice Fees**

The configuration for which charge ID (defined in &#39;CO Charge. Open&#39; – OIS030) to use for an Invoice fee (if applicable). An Invoice fee charge code can be connected to a Magento Payment method.

**Gift Wrapping**

An order level charge corresponding to the Gift-Wrapping price is added when Order-level Gift wrapping is applied to an order [and Gift Wrapping has been configured to be transferred over to M3]. The charge ID for these charges is also defined within &#39;CO Charge. Open&#39; – OIS030).

    
### Line Charges

Base eConnect comes with support for two types of order line charges:

1. Sales Tax

1. Giftwrapping

The following order provides an example of where these two charges are present within Magento, and how they are represented within M3:

![](RackMultipart20200604-4-58zvro_html_ff0e2fa2d837c450.gif)
 ![](RackMultipart20200604-4-58zvro_html_1b5c345316e7ad5d.png)

![](RackMultipart20200604-4-58zvro_html_2ad2e4e358f58820.png)


**Sales Tax**

As of this version of eConnect, Sales Tax is passed as a line charge per order line.

Whether or not to pass Sales Tax to M3 is controlled via _LS \&gt; eConnect-ION \&gt; Configuration \&gt; Order Charges_.

&#39;Tax Transfer&#39; controls whether to pass tax amounts to M3. Setting this value to &#39;Yes&#39;

enables the transfer and opens the second related field below.

**Gift Wrapping**


If Gift Wrapping has been enabled to be sent to M3 within _LS \&gt; eConnect-ION \&gt; Configuration \&gt; Order Charges_, and charges have been selected to be used – any line-level Gift Wrapping cost in Magento will be passed over as a line charge to the corresponding order line in M3.

### Manual Sync Process

This feature enables manual sync of orders with M3. We can choose multiple orders that require sync with M3 and choose &#39;Sync orders with M3&#39;. Clicking on Manual sync triggers &#39;Show&#39; BODs. Once the BOD reaches Magento, the information gets updated in respective tables in the DB. The order is sent to M3, once order is created, order status is updating on receiving respective Bods.

![](RackMultipart20200604-4-58zvro_html_72b9d16719fdd93.png)

[Go to Top](#table-of-contents)

  
## Order Information

This section and the following two contain details on the synchronization of order statuses, deliveries &amp; invoices from M3 to Magento. All the order information is carried in Sync.SalesOrder and Sync.LS\_SalesOrderDetails BODs.

   
### Transaction Overview

The synchronization of the status of the customer order within M3 with the corresponding order in Magento is one of the basic features needed to properly be able to follow the progress of an order within Magento Admin.

The following provides a brief background on _order statuses_ within the two systems.

**Magento**

A Magento order has a _state_. The order _state_ is what defines the position of the order in the order processing workflow. Order statuses are assigned to order states. There can be more than one status assigned to a state, but one of these statuses is set to be the default one. When the _state_ of an order changes the default, status assigned to it is displayed. **Status** could be user defined, while _state_ is used by Magento internally for processing order.

The state is used to define/drive Magento functionality and new states cannot be added using simple configuration.

<kbd><img alt="Order Management in Magento" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/order-management-magento.png"></kbd>

**Source** : Magento via [www.magentocommerce.com](http://www.magentocommerce.com/)

The following Magento states &amp; statuses exist in a new standard installation (Statuses &amp; States listed independently):

<kbd><img alt="Statuses in Magento" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/magento-status.png"></kbd>

**Initial Load/ Import**

This feature allows to import data from M3 into Magento. Data can be imported for the following:

- Configuration
- Customer (Show.CustomerPartyMaster, Show.LS\_CustomerDetails, Show.BillToPartyMaster, Show.ShipToPartyMaster)
- Products Show.LS\_ItemMasterDetails, Show.ItemMaster)
- Price list (Show.LS\_PriceList)
- Inventory (Show.Ls\_ItemStock)
- Order (Show.LS\_SalesOrderDetails, Show.SalesOrder)
- Invoice (Show.invoice, Show.ReceivableTransaction)

<kbd><img alt="Initial load/import" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/initial-load-import.png"></kbd>

Import can be based on certain filter conditions.

<kbd><img alt="Import Invoices" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/import-invoices.png"></kbd>

**From Date:**

Date from which data has to be imported

**To Date:**

Date upto which data has to be imported

**Number of actions:**

Restricts the number of records returned from import

**Query:**

Any conditions can be mentioned here

Once import is done, the last imported date is displayed

**Import History**

This displays the history of imports done in the system. Clicking on this will navigate to a page that displays information on which module was imported and the corresponding conditions that were used.

<kbd><img alt="Import History" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/import-history.png"></kbd>

**M3**

M3 has a similar, but different approach to order statuses. Each customer order has two different statuses; _Highest_- &amp; _Lowest_ status.

Simply put, the _Highest_ status for an order illustrates the status of the order line that&#39;s been processed the _furthest_ while the _Lowest_ status illustrates the status of the order line that&#39;s been processed the _least_.

The sales order process includes these major steps:

- Reservation – Status22
  - Order has been accepted in M3 without errors, ready to be processed.
- Allocation – Status33
  - Specific inventory balances have been committed to the order.
- Pick list printed – Status44
  - The physical/electronic trigger to the DC to start the picking process.
- Delivered – Status66
  - Order (Delivery) has been reported as &quot;Shipped&quot;.
- Invoiced – Status77
  - Order (Delivery) has been fully invoiced.

Each Order Line has a two-position Line status field, that indicates the state of the order line. Since an order line can be partially processed throughout each stage, a single line can have multiple states.

The following is part of the order line status help text in M3:

**Alternatives**

05 = Quotation
10 = Preliminary
22 = Reserved
33 = Allocated - location and lot number selected 44 = Picking list printed
66 = Delivered
77 = Invoiced
99 = Flagged as completed, without delivery.
2 = Quantity remains to be allocated. This is displayed in field Remaining quantity.
3 = Allocated quantity exists.
4 = Picking list for the quantity is printed.
6 = Delivered quantity exists.
7 = Invoiced quantity exists.
9 = Quantity is manually flagged as completed when the picking list is reported.

The order status codes contain two positions. When the status is higher than 20, the first position indicates how far a partial quantity has progressed in the earliest stage of the order flow. The second position indicates how far a partial quantity has progressed in the latest stage of the orderflow.

**Example** :

If a customer order line has status 33, it only contains allocated quantity. If a customer order line has status 77, it only contains invoiced quantity. If a customer order line has status 37, it contains both allocated and invoiced quantities.

If a customer then has one partially allocated &amp; invoiced line (status 37), and one fully invoiced line (status 77) – the Highest/Lowest status for the entire order will be 77/37

[Go to Top](#table-of-contents)

    
### Magento &amp; M3 Order Status Relation

Since Magento only supports order statuses on order level (not order line level), eConnect can only update the Magento order status based on the M3 order header status.

Magento also only support a single order status for each order (not lowest/highest status as in M3). Due to this, Lean Swift has chosen to use the _Highest order status_ in M3 when updating the Magento order status.

When the _Highest status_ is changed in M3 – the Magento order status will be updated per the following table:

| M3 Highest Status | Should update Magento status to | Magento State | Status Text |
| --- | --- | --- | --- |
| 22 | erp\_sts22 | Processing | 22-Order sent to warehouse |
| 23 | erp\_sts23 | Processing | 23-Order sent to warehouse |
| 24 | erp\_sts24 | Processing | 24-Order being packed |
| 26 | erp\_sts26 | Processing | 26-Order partially shipped |
| 27 | erp\_sts27 | Processing | 27-Order partially invoiced |
| 33 | erp\_sts33 | Processing | 33-Order sent to warehouse |
| 34 | erp\_sts34 | Processing | 34-Order being packed |
| 36 | erp\_sts36 | Processing | 36-Order partially shipped |
| 37 | erp\_sts37 | Processing | 37-Order partially invoiced |
| 44 | erp\_sts44 | Processing | 44-Order being packed |
| 46 | erp\_sts46 | Processing | 46-Order partially shipped |
| 47 | erp\_sts47 | Processing | 47-Order partially invoiced |
| 66 | erp\_sts66 | Shipped | 66-Order shipped |
| 67 | erp\_sts67 | Processing | 67-Order partially invoiced |
| 77 | erp\_sts77 | Complete | 77-Order invoiced |

The installation of eConnect adds all of the custom statuses listed in the second column above. Please note that all of these statuses are required to be used within Magento, i.e. it&#39;s not possible to selectively choose not to map certain statuses.

The value of the &#39;Status Text&#39; can be changed within each Magento installation.

Magento standard functionality will then change an order from state _Processing_ to _Complete_

when all order lines have been shipped andinvoiced.

[Go to Top](#table-of-contents)

  
## Shipment

The Shipment synchronization is the second key within eConnect to within Magento be able to properly reflect the complete state of the order as it is in M3. The shipment details are carried in Sync.SalesOrder BOD.

    
### Shipments In Magento

Each Magento order can have multiple shipments associated with it.

<kbd><img alt="Shipments" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/shipments.png"></kbd>

Each shipment can have several tracking numbers associated to it.

<kbd><img alt="Shipment Handling Information" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/shipping-handling-info.png"></kbd>

Click on Track order to view the tracking info.

<kbd><img alt="Shipment Tracking Info" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/shipment-trackinginfo.png"></kbd>

The shipment includes delivery address and items delivered. When creating the delivery, only items on the order can be selected. Order comments can be added. A new shipment can automatically generate an email notification to the customer.

Shipment information is carried in &#39;Sync.Shipment&#39; BOD.

    
### Deliveries In M3

Within M3, each order is broken down in one or multiple _deliveries_. These deliveries act as more manageable &quot;sub orders&quot; from a logistics perspective. Any pick, pack and other dispatch activity within M3 is handled on the delivery level.

Deliveries for customer orders are within M3 managed in two different places – the Delivery Toolbox and the CO Deliveries function. The Delivery Toolbox has a heavy focus on Supply Chain activities. The delivery is generated by M3 here as soon as the final customer order is available in the system. The CO Deliveries doesn&#39;t get the delivery added to it until it has been reported as shipped (pick list reporting completed). This function provides a key link to for example the invoicing logic within M3, and the delivery can for example optionally be held for approval via the DO Delivery function prior to being eligible for invoicing.

A delivery is also in M3 made up of a number of the lines (or part of the lines) on the associated customer order.

**Note**

There is also in M3 a concept called &#39;Shipments&#39;, where several deliveries can be combined in to a single entity. The current version of eConnect only supports synchronization on the delivery level, and validation has not been performed with Shipments inM3.

    
### Tracking Numbers

eConnect is also prepared to also synchronize any tracking numbers that are entered on the delivery within M3. With the assumption that Shipments in M3 are not supported, tracking numbers can be entered in two different ways depending on the dispatch process used. The tracking details are carried in Sync.SalesOrder BOD.

**Delivery Tracking**

A single tracking number can be entered for the entire delivery on detail panel F of the delivery

in &#39;Delivery. Open Toolbox&#39; (MWS410).

<kbd><img alt="Shipment Tracking Info in M3" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/shipment-trackinginfo-m3.png"></kbd>

**Package Tracking#**

If a delivery contains one or multiple packages, the tracking number can also be added at the package level (if delivery is sent as small parcel for example).

![](RackMultipart20200604-4-58zvro_html_903f35494ff02852.png)

eConnect will search for tracking numbers in both of these places, starting with the delivery. A base assumption is that tracking numbers are not entered at both the delivery and the package level, but either or.

Once shipment is created, shipment BOD updates the information into magento and order gets updated with the information

Each delivery that is created within M3 will be synchronized over to Magento, and pegged with

the M3 delivery number as a reference within the &#39;Shipment History&#39; section.


<kbd><img alt="Shipments" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/shipments.png"></kbd>

 <kbd><img alt="Shipment history" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/shipment-history.png"></kbd>

The synchronization of the M3 delivery is possible only following pick reporting, i.e. after the quantity on the delivery has been issued (at corresponding status moved to &#39;6&#39; in M3) and the delivery appears in &#39;CO Delivery.Open&#39; (OIS150).

[Go to Top](#table-of-contents)

  
## Invoice

The third and final key piece related to order information is the ability to synchronize over invoices from M3 to Magento.

The same two options for performing the synchronization as described for Shipments in the previous section apply.

When invoices are synchronized from M3 to Magento, each invoice in M3 (OINVOH/OINVOL) creates a separate new invoice (billing address, Shipping address, payment info, M3 invoice #, items, charges) in Magento.

The invoice creation is limited to the functionality provided by Magento. This means that no additional charges can be added in M3 that does not exist on the Magento order, nor can changes be made within M3.

Each invoice in Magento references the corresponding invoice in M3 within the &#39;InvoiceHistory&#39;

section.

Invoice information/Details are available in Sync.Invoice Bod and in Sync.ReceivableTransaction BODs.

<kbd><img alt="Invoice tab in Orders" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/invoice-order.png"></kbd>

<kbd><img alt="Invoice display in m3" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/invoice-display.png"></kbd>

<kbd><img alt="Invoice history in orders" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/invoicehistory-order.png"></kbd>

Invoice information is carried by Sync.Invoice BOD and Sync.ReceivableTransaction BOD.

[Go to Top](#table-of-contents)

  
## Order History

The Order History section within the Magento front-end has been re-designed, and additional filter options have been added together with a simple way to separate orders that originates from Magento vs. M3.

In the case where a common customer number is used in a B2C setup, the functionality remains the same in that only order history from within Magento is displayed.

For a B2C or B2B configuration where individual (discrete) customer numbers are used, the Order History is accessed via the &#39;My Orders&#39; link in the menu on the left on the account home page after a user has logged in to the Magento front-end.

<kbd><img alt="Order history recent orders" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/orderhistory-recentorders.png"></kbd>

<kbd><img alt="Order history my orders" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/orderhistory-myorders.png"></kbd>

The new Order History view presents the users with two pre-defined views (1) _ERP Orders_ and

1. _Magento Orders_. There&#39;re also additional optional filters (3) that can be applied in the _ERP Orders_view.

<kbd><img alt="Order history erp orders" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/orderhistory-erporders.png"></kbd>

When the _ERP Orders_ view is selected, every sales order in M3 for the M3 customer number that the Magento user logged in is associated with is displayed.

The following Additional filter capabilities are available within the _ERP Orders_ view:

<kbd><img alt="Order history Filters" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/orderhistory-filters.png"></kbd>

  1. Search for a specific Magento order number
  2. Search for a specific M3 order number
  3. Filter on a range of dates the orders were created
  4. Search for a specific Customer PO/Ref# from the order inM3
  5. Filter orders with a specific status
  
[Go to Top](#table-of-contents)

## Invoice History

The invoice history view is accessed via the customer&#39;s &#39;My Account&#39; view on the front-end.

<kbd><img alt="Invoice History" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/invoice-history.png"></kbd>

Some filter capabilities exist also for the &#39;My Invoice&#39; view.

<kbd><img alt="Invoice Filters" src="https://github.com/leanswift/leanswift.github.io/blob/dev/ecommerce/images/econnect-user-manual-ion-part2/invoice-filters.png"></kbd>

1. A specific Invoice Number can be searched out
2. A specific M3 order number can be searched out
3. A From-To date range can be applied to the &#39;InvoiceDate&#39;

1. A certain Customer PO# can be filtered

In the case where a common customer number is used in a B2C setup, only invoice history from within Magento is displayed.

All orders related to customer is shown up in the page irrespective of how old the order is.

[Go to Top](#table-of-contents)

