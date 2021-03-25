# **User Manual – Gift Card Add-on for eConnect**
![econnect_banner](../../../../../images/banner-econnect-m3.jpg)

**Product Version**  **2.6.0**

**eConnect version 20.3.1**


# TABLE OF CONTENTS

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
  - [2.0 GIFT CARD ADD-ON](#20-gift-card-add-on)
    - [2.0.1 Summary](#201-summary)
    - [2.0.2 Assumptions/Limitations](#202-assumptions-limitations)
  - [2.1 CONFIGURATION](#21-configuration)
    - [2.1.1 Standard Magento Configuration -General](#211-standard-magento-configuration-general)
      - [2.1.1.1 Gift Card Email Settings](#2111-gift-card-email-settings)
      - [2.1.1.2 Gift Card General Settings](#2112-gift-card-general-settings)
      - [2.1.1.3 Email Sent from Gift Card Account Management](#2113-email-sent-from-gift-card-account-management)
      - [2.1.1.4 Gift Card Account General Settings](#2114-gift-card-account-general-settings)
    - [2.1.2 Standard Magento Configuration -Product](#212-standard-magento-configuration-product)
      - [2.1.2.1 Gift Card Pricing](#2121-gift-card-pricing)
      - [2.1.2.2 Gift Card Information](#2122-gift-card-information)
    - [2.1.3 LeanSwift eConnect Configuration –Gift Card](#213-leanswift-econnect-configuration-gift-card)    
  - [2.2 PROCESS](#22-process)
    - [2.2.1 Gift Card Sales](#221-gift-card-sales)
   

# GENERAL INFORMATION

## 1.1 System Overview

- **LeanSwift eConnect for Infor M3** provides a powerful, seamless integration between Magento and Infor M3 ERP. The product consists of a base Magento extension that extends standard Magento functionality and offers several transactions to ensure your eCommerce websites contain up-to-date information from your M3 ERP. There exist a number of optional add-on extensions too for additional functionality

- **LeanSwift eConnect for Infor M3** is available for Magento Open Source and Magento Commerce and for Infor M3 version 7.x and above. It is also compatible with multi-tenant cloud editions of Infor M3 (Cloudsuite).

- **LeanSwift eConnect for Infor M3** employs a layered architecture to allow flexibility in supporting different versions of Magento and Infor M3 and to allow independent upgrades.


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

<kbd>
<img alt ="elink architecture" src="https://github.com/leanswift/leanswift.github.io/blob/ECNT-1845/ecommerce/images/add-ons/gift-card/elink_Architecture.jpg"></kbd>



### Architecture with ION for multi-tenant Cloud M3

<kbd><img alt ="ION architecture" src="https://github.com/leanswift/leanswift.github.io/blob/ECNT-1845/ecommerce/images/add-ons/gift-card/ION_Architecture.jpg"></kbd>



The add-ons for LeanSwift eConnect provide extended functionality over the standard features available on eConnect Core.

These add-ons can, if necessary, be modified, and new add-ons can be added to fulfill specific customer requirements.


[Go to Top](#table-of-contents)

**User interface**

During setup, the Magento Admin panel is used to configure which transactions that should be used and how they should function. There is also additional configuration within the Connector to support the transactions.

**Validated versions**

Magento OpenSource 2.4.1

Magento Commerce 2.4.1

Infor M3 CloudSuite

## 1.2 Points of Contact

### 1.2.1 Information

This document and the software it describes are provided by LeanSwift Solutions Inc. For additional information regarding support, licensing, functionality etc. please contact LeanSwift Solutions Inc via contact form at [http://www.leanswift.com](http://www.leanswift.com/)or email info@leanswift.com

## 1.3 Organization of the Manual

This manual is not intended to cover any standard Magento functionality or user experience. The Magento user experience is customized and slightly different in each eCommerce implementation – though the general workflow is similar.

## 1.4 Acronyms and Abbreviations

ERP – Enterprise Resource Planning

[Go to Top](#table-of-contents)

## 2.0 GIFT CARD ADD-ON

### 2.0.1 Summary

The _Gift Card_ module extends the standard Magento Enterprise functionality for selling &amp; redeeming gift cards to eConnect and hence also to M3. An unlimited number of gift cards can be sold on a separate order or together with other products. All types of Gift Cards available in Magento are supported (Physical, Virtual &amp; Combined). **This add-on is available for Magento Commerce only**.

### 2.0.2 Assumptions/Limitations

- Gift Card requires Magento Commerce.
- Up to 4 Gift coupons can be used for redemption per order

[Go to Top](#table-of-contents)

## 2.1 CONFIGURATION

The configuration for Gift Cards is made up of two parts – the standard Magento setup and the LeanSwift-specific setup to support eConnect.

### 2.1.1 Standard Magento Configuration -General

The general standard Magento configuration can be found under Stores > Configuration > Sales > Gift Cards_.

<kbd><img alt ="giftcard general" src="https://github.com/leanswift/leanswift.github.io/blob/ECNT-1845/ecommerce/images/add-ons/gift-card/giftcard-general.png"></kbd>


#### 2.1.1.1 Gift Card Email Settings

This group contains the settings related to which e-mail sender within Magento should be used for the e-mail notifications to customers related to Gift Cards, as well as which e-mail template should be applied.

<kbd><img alt ="giftcard email" src="https://github.com/leanswift/leanswift.github.io/blob/ECNT-1845/ecommerce/images/add-ons/gift-card/giftcard-email-setting.png"></kbd>

#### 2.1.1.2 Gift Card General Settings

This group contains key general settings defining the behavior of Gift Cards. Some of these settings can be overridden on Product level (see further details under section **2.1.2** ).

<kbd><img alt ="giftcard general settings" src="https://github.com/leanswift/leanswift.github.io/blob/ECNT-1845/ecommerce/images/add-ons/gift-card/giftcard-general-settings.PNG"></kbd>

**Redeemable**

Controls whether the Gift Cards issued are redeemable within the Magento store.

**Lifetime (days)**

Controls how many days an issued Gift Card is valid for. If no/zero is entered this means the cards will have no expiration.

**Allow Gift Message**

Controls whether a buyer on the front-end has the option to enter in a message in connection with their Gift Card purchase.

**Gift Message Maximum Length**

Imposes a max length on messages associated with Gift Card purchases.

**Generate Gift Card Account when Order item is**

Controls at what point in the sales process that the Gift Card Account should be generated – when the order is placed or when the invoice is issued.

#### 2.1.1.3 Email Sent from Gift Card Account Management

Contains additional details for e-mail generation for the Gift Card Accounts.

<kbd><img alt ="giftcard account management" src="https://github.com/leanswift/leanswift.github.io/blob/ECNT-1845/ecommerce/images/add-ons/gift-card/giftcard-account-management.png"></kbd>

#### 2.1.1.4 Gift Card Account General Settings

This group contains a number of details setup to control exactly how the Gift Card Accounts within Magento should be generated up.

<kbd><img alt ="giftcard account general" src="https://github.com/leanswift/leanswift.github.io/blob/ECNT-1845/ecommerce/images/add-ons/gift-card/giftcard-account-general.png"></kbd>

[Go to Top](#table-of-contents)

### 2.1.2 Standard Magento Configuration –Product

Each Gift Card is in Magento defined as a product with a product type of &#39;Gift Card&#39; which is further classified as physical, virtual and combined. This separate product type enables a number of unique settings within the product details.

<kbd><img alt ="card type" src="https://github.com/leanswift/leanswift.github.io/blob/ECNT-1845/ecommerce/images/add-ons/gift-card/cardtype.png"></kbd>

The setup for products can in Magento be found under _Catalog > Products_.

#### 2.1.2.1 Gift Card Pricing

Gift cards can be searched out by filtering on Product Type &#39;Gift Card&#39;:

<kbd><img alt ="type gift card" src="https://github.com/leanswift/leanswift.github.io/blob/ECNT-1845/ecommerce/images/add-ons/gift-card/type-giftcard.png"></kbd>

The first part of the product details that are different from other product types is the pricing setup, which can be found under _Product Details_

<kbd><img alt ="gift card ammount" src="https://github.com/leanswift/leanswift.github.io/blob/ECNT-1845/ecommerce/images/add-ons/gift-card/giftcard-amount.png"></kbd>

The layout of the Pricing section is different from a normal product, and offers some specific information related to Gift Cards.

**Amounts**

These make up the pre-defined denominations the Gift Card is available in to a customer looking to purchase from the front-end. In the example above, the only predefined Amount available is $5.

**Allow Open Amount**

This option defines whether or not a customer can assign their own amount to the gift card during purchase. If this is set to &#39;Yes&#39;, the next two fields define the Min- &amp; Max values that can be added.

#### 2.1.2.2 Gift Card Information

The specific Gift Card settings for a product can be found under _Catalog > Manage Products > Product Information > Gift Card Information_.

<kbd><img alt ="card information" src="https://github.com/leanswift/leanswift.github.io/blob/ECNT-1845/ecommerce/images/add-ons/gift-card/giftcard-information.PNG"></kbd>

**Card Type**

Defines whether the Gift Card product is &#39;Virtual&#39;, &#39;Physical&#39; or &#39;Combined&#39;. A Virtual gift card product bypasses the shipping-related steps during the checkout process, and only and e-mail is generated and sent to the customer with the pertinent information about their purchase. A Physical gift card acts as a regular simple product during checkout, and is assumed to be physically picked, packed &amp; shipped to the customer. A Combined gift card product acts as a Physical, with the addition of the e-mail communication of the Virtual.

The additional settings in this group have been covered in section 2.1.1.2 above, and Magento here offers the choice to override the global settings for these 4 parameters individually per product.

[Go to Top](#table-of-contents)

### 2.1.3 LeanSwift eConnect Configuration –Gift Cards

The LeanSwift-specific settings related to Gift Cards can be found under _Stores> Configuration > LeanSwift Solutions> Gift Cards_.

<kbd><img alt ="leanswift config" src="https://github.com/leanswift/leanswift.github.io/blob/ECNT-1845/ecommerce/images/add-ons/gift-card/leanswift-giftcard.PNG"></kbd>

<kbd><img alt ="leanswift giftcard" src="https://github.com/leanswift/leanswift.github.io/blob/ECNT-1845/ecommerce/images/add-ons/gift-card/leanswift-giftcard-config.PNG"></kbd>

**Gift Card Line Charge ID (Sales)**

The line charge is used to transfer the Gift Card ID to each order line in M3, where the ID is saved as the description of the charge – and the charge amount holds the amount purchased on the gift card.

The values of the Gift Card Line Charge ID are retrieved dynamically from &#39;Order Line Charge. Open&#39; (CRS235) in M3.

**Gift Card Header Charge ID (Redeem)**

The header charge is used to hold any gift card amount that a customer redeems on an order. The total gift card amount is added to the order in M3 with this header charge, and the amount as a negative value.

[Go to Top](#table-of-contents)

## 2.2 PROCESS

Once the setup described in the previous section has been completed, Gift Cards can be purchased and redeemed by customers as described in this section.

### 2.2.1 Gift Card Sales

The process of selling gift cards is in this section described by using an example where this is done via the front-end, and the gift card purchased in a _Physical_ gift card. The only difference with ordering a _Virtual_ gift card is that the check-out process is shorter as no Ship-to information is needed. There is also full support for this process within Magento Admin.

In this example, a Physical gift card is being ordered (i.e. a Magento product that follows the same Checkout process as a Simple product for example). Accessing the product detail page reveals the unique options for a gift card, that will vary depending on the configuration of the corresponding product in Magento.

<kbd><img alt ="giftcard frontend" src="https://github.com/leanswift/leanswift.github.io/blob/ECNT-1845/ecommerce/images/add-ons/gift-card/frontend-giftcard.PNG"></kbd>

In this example, selecting the drop-down to choose an amount reveals the following options:

<kbd><img alt ="giftcard amount" src="https://github.com/leanswift/leanswift.github.io/blob/ECNT-1845/ecommerce/images/add-ons/gift-card/frontend-ammount.png"></kbd>

This means that both a so called &quot;open amount&quot; as well as two different fixed amounts ($100 and $300 in this case) are allowed. Selecting one of the fixed amounts will assign that value to the gift card.

Selecting &#39;Other Amount&#39; enables manual input of the value to be assigned to the gift card, within the limits defined within Magento Admin (i.e. between $5 and $5,000 in this example).

For this purpose, a gift card with a value of $450 will be purchased by entering this value in the &#39;Amount in USD&#39; field, keep the quantity at &#39;1&#39; and press &#39;Add to Cart&#39;.


<kbd><img alt ="giftcard details" src="https://github.com/leanswift/leanswift.github.io/blob/ECNT-1845/ecommerce/images/add-ons/gift-card/frontend-giftcard-details.PNG"></kbd>

The cart page will show the associated information entered for the gift card product.

<kbd><img alt ="giftcard cart" src="https://github.com/leanswift/leanswift.github.io/blob/ECNT-1845/ecommerce/images/add-ons/gift-card/frontend-cart.PNG"></kbd>

The remaining part of the checkout process is identical to any other physical product being shipped.

<kbd><img alt ="giftcard payment" src="https://github.com/leanswift/leanswift.github.io/blob/ECNT-1845/ecommerce/images/add-ons/gift-card/frontend-payment.PNG"></kbd>

<kbd><img alt ="giftcard completeorder" src="https://github.com/leanswift/leanswift.github.io/blob/ECNT-1845/ecommerce/images/add-ons/gift-card/frontend-completeorder.PNG"></kbd>

The order in Magento Admin looks similar to other product orders

<kbd><img alt ="giftcard salesorder" src="https://github.com/leanswift/leanswift.github.io/blob/ECNT-1845/ecommerce/images/add-ons/gift-card/magento-salesorder.PNG"></kbd>

_Note: To allow placing orders for multiple Gift Cards in a single order, necessary M3 setting must be configured._

