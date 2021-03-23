# **eConnect User Manual – Order Grid**
![econnect_banner](../../../../../images/banner-econnect-m3.jpg)
## **LeanSwift eConnect for Infor M3 &amp; Magento**


**Product Version**  **2.6.0**

**eConnect version 20.3.1**


**TABLE OF CONTENTS**


# GENERAL INFORMATION

## 1.1 System Overview

LeanSwift eConnect for Infor M3 provides a seamless integration between Magento and Infor M3 ERP. The product consists of a base Magento extension as well as a number of optional add-on extensions, and a Tomcat based server application called LeanSwift eLink that manages the communication with the M3 ERP system.

LeanSwift eConnect for Infor M3 employs a layered architecture to allow more flexibility in supporting different versions of Magento and Infor M3, and to allow independent upgrades. The two components are versioned individually to more easily adapt to different M3 &amp; Magento versions.

![](RackMultipart20210323-4-14tsl8n_html_a47b2c239d934845.jpg)

The add-ons for LeanSwift eConnect provide extended functionality over the standard features available on eConnect Core.

These add-ons can, if necessary, be modified, and new add-ons can be added to fulfill specific customer requirements.

**User interface**

During setup, the Magento Admin panel is used to configure which transactions that should be used and how they should function. There is also additional configuration within the Connector to support the transactions.

**Validated versions**

Magento OpenSource 2.4.1

Magento Commerce 2.4.1

Infor M3 16x

## 1.2 Points of Contact

### 1.2.1 Information

This document and the software it describes are provided by LeanSwift Solutions Inc. For additional information regarding support, licensing, functionality etc. please contact LeanSwift Solutions Inc via contact form at [http://www.leanswift.com](http://www.leanswift.com/)or email info@leanswift.com

## 1.3 Organization of the Manual

This manual is not intended to cover any standard Magento functionality or user experience. The Magento user experience is customized and slightly different in each eCommerce implementation – though the general workflow is similar.

## 1.4 Acronyms and Abbreviations

ERP – Enterprise Resource Planning


# GIFT CARD ADD-ON

### 2.0.1 Summary

The _Gift Card_ module extends the standard Magento Enterprise functionality for selling &amp; redeeming gift cards to eConnect and hence also to M3. An unlimited number of gift cards can be sold on a separate order or together with other products. All types of Gift Cards available in Magento are supported (Physical, Virtual &amp; Combined). **This add-on is available for Magento Commerce only**.

### 2.0.2 Assumptions/Limitations

- Gift Card requires Magento Commerce.
- Up to 4 Gift coupons can be used for redemption per order

## 2.1 CONFIGURATION

The configuration for Gift Cards is made up of two parts – the standard Magento setup and the LeanSwift-specific setup to support eConnect.

### 2.1.1 Standard Magento Configuration - General

The general standard Magento configuration can be found under Stores > Configuration > Sales > Gift Cards_.

![](RackMultipart20210323-4-14tsl8n_html_3be5d1da938c5da6.png)

#### 2.1.1.1 Gift Card Email Settings

This group contains the settings related to which e-mail sender within Magento should be used for the e-mail notifications to customers related to Gift Cards, as well as which e-mail template should be applied.

![](RackMultipart20210323-4-14tsl8n_html_a957ded0b557ca05.png)

#### 2.1.1.2 Gift Card General Settings

This group contains key general settings defining the behavior of Gift Cards. Some of these settings can be overridden on Product level (see further details under section **2.1.2** ).

![](RackMultipart20210323-4-14tsl8n_html_a70ccde6b2dec244.png)

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

#### 2.1.1.4 Gift Card Account General Settings

This group contains a number of details setup to control exactly how the Gift Card Accounts within Magento should be generated up.

![](RackMultipart20210323-4-14tsl8n_html_77a374f2604e323b.png)

### 2.1.2 Standard Magento Configuration – Product

Each Gift Card is in Magento defined as a product with a product type of &#39;Gift Card&#39; which is further classified as physical, virtual and combined. This separate product type enables a number of unique settings within the product details.

![](RackMultipart20210323-4-14tsl8n_html_b811f49746ed27ee.png)

The setup for products can in Magento be found under _Catalog > Products_.

#### 2.1.2.1 Gift Card Pricing

Gift cards can be searched out by filtering on Product Type &#39;Gift Card&#39;:

![](RackMultipart20210323-4-14tsl8n_html_b88138bd865ee4a6.png)

The first part of the product details that are different from other product types is the pricing setup, which can be found under _Product Details_

![](RackMultipart20210323-4-14tsl8n_html_dc5a4bc1f181ab75.png)

The layout of the Pricing section is different from a normal product, and offers some specific information related to Gift Cards.

**Amounts**

These make up the pre-defined denominations the Gift Card is available in to a customer looking to purchase from the front-end. In the example above, the only predefined Amount available is $5.

**Allow Open Amount**

This option defines whether or not a customer can assign their own amount to the gift card during purchase. If this is set to &#39;Yes&#39;, the next two fields define the Min- &amp; Max values that can be added.

#### 2.1.2.2 Gift Card Information

The specific Gift Card settings for a product can be found under _Catalog > Manage Products > Product Information > Gift Card Information_.

![](RackMultipart20210323-4-14tsl8n_html_fcc025af12ae2e86.png)

**Card Type**

Defines whether the Gift Card product is &#39;Virtual&#39;, &#39;Physical&#39; or &#39;Combined&#39;. A Virtual gift card product bypasses the shipping-related steps during the checkout process, and only and e-mail is generated and sent to the customer with the pertinent information about their purchase. A Physical gift card acts as a regular simple product during checkout, and is assumed to be physically picked, packed &amp; shipped to the customer. A Combined gift card product acts as a Physical, with the addition of the e-mail communication of the Virtual.

The additional settings in this group have been covered in section 2.1.1.2 above, and Magento here offers the choice to override the global settings for these 4 parameters individually per product.

### 2.1.3 LeanSwift eConnect Configuration – Gift Cards

The LeanSwift-specific settings related to Gift Cards can be found under _Stores> Configuration > LeanSwift Solutions> Gift Cards_.

![](RackMultipart20210323-4-14tsl8n_html_e9f4ae469d1627a2.png)

![](RackMultipart20210323-4-14tsl8n_html_c3334e2e7d587108.png)

**Gift Card Line Charge ID (Sales)**

The line charge is used to transfer the Gift Card ID to each order line in M3, where the ID is saved as the description of the charge – and the charge amount holds the amount purchased on the gift card.

The values of the Gift Card Line Charge ID are retrieved dynamically from &#39;Order Line Charge. Open&#39; (CRS235) in M3.

**Gift Card Header Charge ID (Redeem)**

The header charge is used to hold any gift card amount that a customer redeems on an order. The total gift card amount is added to the order in M3 with this header charge, and the amount as a negative value.

## 2.2 PROCESS

Once the setup described in the previous section has been completed, Gift Cards can be purchased and redeemed by customers as described in this section.

### 2.2.1 Gift Card Sales

The process of selling gift cards is in this section described by using an example where this is done via the front-end, and the gift card purchased in a _Physical_ gift card. The only difference with ordering a _Virtual_ gift card is that the check-out process is shorter as no Ship-to information is needed. There is also full support for this process within Magento Admin.

In this example, a Physical gift card is being ordered (i.e. a Magento product that follows the same Checkout process as a Simple product for example). Accessing the product detail page reveals the unique options for a gift card, that will vary depending on the configuration of the corresponding product in Magento.

![](RackMultipart20210323-4-14tsl8n_html_776b5d28f9758e31.png)

In this example, selecting the drop-down to choose an amount reveals the following options:

![](RackMultipart20210323-4-14tsl8n_html_55f5dfae014d0379.png)

This means that both a so called &quot;open amount&quot; as well as two different fixed amounts ($100 and $300 in this case) are allowed. Selecting one of the fixed amounts will assign that value to the gift card.

Selecting &#39;Other Amount&#39; enables manual input of the value to be assigned to the gift card, within the limits defined within Magento Admin (i.e. between $5 and $5,000 in this example).

For this purpose, a gift card with a value of $450 will be purchased by entering this value in the &#39;Amount in USD&#39; field, keep the quantity at &#39;1&#39; and press &#39;Add to Cart&#39;.

![](RackMultipart20210323-4-14tsl8n_html_cf5685a9bd2daf09.png)

The cart page will show the associated information entered for the gift card product.

![](RackMultipart20210323-4-14tsl8n_html_2a033dfd123b9aa4.png)

The remaining part of the checkout process is identical to any other physical product being shipped.

![](RackMultipart20210323-4-14tsl8n_html_8bf141e5e932412e.png)

![](RackMultipart20210323-4-14tsl8n_html_423fd3a4032a848b.png)

The order in Magento Admin looks similar to other product orders

![](RackMultipart20210323-4-14tsl8n_html_df03c1700e5a0ca3.png)

_Note: To allow placing orders for multiple Gift Cards in a single order, necessary M3 setting must be configured._

