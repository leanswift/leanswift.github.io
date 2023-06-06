# **eConnect User Manual – Multi-Warehouse**
![econnect_banner](../../../../../images/banner-econnect-m3.jpg)
## **LeanSwift eConnect for Infor M3 &amp; Magento** 


**Product Version**  **4.1.0**

**eConnect version 20.3.0**


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
  - [2.0 MULTIWAREHOUSE ADD-ON](#20multiwarehouse-add-on)
    - [2.0.1 Summary](#201-summary)
    - [2.0.2 Limitations](#202-limitations)
  - [2.1 CONFIGURATION](#21-configuration)
    - [2.1.1 Magento configuration-eLink](#211-magento-configuration-elink)
    - [2.1.2 Magento Configuration-ION](#212-magento-configuration-ion)
    - [2.1.3 M3 Configuration](#213-m3-configuration)
  - [2.2 PROCESS](#22-process)
    - [2.2.1 MWH in Product detail page](#221-mwh-in-product-detail-page)
      - [2.2.1.1 Simple Product](#2211-simple-product)
      - [2.2.1.2 Grouped Product](#2212-grouped-product)
      - [2.2.1.3 Configurable Product](#2213-configurable-product)



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


<kbd><img alt="eLink Architecture" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/elink_Architecture.jpg"></kbd>


### Architecture with ION for multi-tenant Cloud M3


<kbd><img alt="ION Architecture" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/ION_Architecture.jpg"></kbd>

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

MWH– Multi-Warehouse

[Go to Top](#table-of-contents)


## 2.0	MULTIWAREHOUSE ADD-ON

### 2.0.1 Summary

The MWH module extends the standard Magento functionality for displaying stock based on warehouse and stock zone by providing full integration to Infor M3 ERP.

MWH helps us discover the available stock based on the warehouse, stock zone, company, division, facility and stock id.

We can add multiple warehouses and stock zone and this information will appear for each product in the frontend.


### 2.0.2 Limitations

1.	This add-on requires Wyoming’s Advanced Inventory Magento extension to be installed. This is a pre-requisite

2.	Stock display is only available in product detail page and not in list page or cart page

3.	Only swatches are supported for configurable items wrt MWH

4.	For Configurable product, cumulative stock from all stock zones is displayed for each child item. This will be displayed only with Order Grid extension
     
5.	The warehouse created from Sales-> POS must be assigned to customer groups in order for Add to cart option to be available and for Stock to be displayed in frontend

[Go to Top](#table-of-contents)

## 2.1 CONFIGURATION

### 2.1.1 Magento Configuration-eLink

The MWH setting can be found under LEANSWIFT SOLUTIONS > eConnect
The options enable us to control MWH stock visibility in the backend and frontend.

<kbd><img alt="Magento_elink_Config" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/Magento_elink_Config.PNG"></kbd>


[Go to Top](#table-of-contents)

### 2.1.2 Magento Configuration-ION

<kbd><img alt="Magento_ION_Config" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/Magento_ION_Config.PNG"></kbd>

The only difference is ‘Sync’ option is removed.
When stock bods are received, stock gets updated in Magento.


To enable creation of warehouse on POS, Go to Sales>Point of sales>User permission and select permission to admin.

<kbd><img alt="Magento_Permission" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/Magento_Permission.PNG"></kbd>

Once necessary permissions are provided, warehouses can be created from Sales> Manage POS/WH

<kbd><img alt="Magento_Create_WH" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/Magento_Create_WH.PNG"></kbd>

Click on the Create New Point of Sale / Warehouse to create warehouses. Under General Information, enter the necessary details.

<kbd><img alt="Magento_WH_General" src="https://github.com/leanswift/leanswift.github.io/blob/ECNT-2313/ecommerce/images/add-ons/multiwarehouse/Magento_WH_General.PNG"></kbd>

Make sure necessary Customer groups are selected.

<kbd><img alt="Magento_WH_Customer" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/Magento_WH_Customer.PNG"></kbd>

Fill up the Inventory settings as required.

<kbd><img alt="Magento_WH_Inventory" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/Magento_WH_Inventory.PNG"></kbd>

Once all the tabs are filled with required information, Warehouse will now be available in the dropdown under eConnect configuration.

When multiple Stock zones are configured for the same warehouse like below:

<kbd><img alt="M3_MMS040" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/Inventory_SameWH1.PNG"></kbd>

<kbd><img alt="M3_MMS040" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/Inventory_SameWH2.PNG"></kbd>

When the stock is updated in stock zone YB, a BOD gets generated with value in YB which gets updated in eConnect.

When the stock is updated in stock zone Y9, a BOD gets generated with the value from MMS002’s ‘On-hand approve’ (YB+Y9). This value will get updated in eConnect in the Y9 zone

Now if YB is again updated with stock, ((new value in Y9) +YB) gets updated in the Y9 zone in econnect and so on.

NOTE: This might be based on StockZone-Location settings in M3. If only one stock zone-warehouse is configured, the value that comes in BOD for that respective stock zone gets updated.


[Go to Top](#table-of-contents)

### 2.1.3 M3 Configuration

Stock zone can be viewed/created in program MMS040

<kbd><img alt="M3_MMS040" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/M3_MMS040.PNG"></kbd>

These are the available stock zones for the logged in Comp/Div.

To know the product details based on warehouse, it can be viewed/created in program MMS002
where the stock zone is available in panel G

<kbd><img alt="M3_MMS002" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/M3_MMS002.PNG"></kbd>

MMS010 displays the Location-Stock Zone mapping

<kbd><img alt="M3_MMS040" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/MMS010.PNG"></kbd>


<kbd><img alt="M3_MMS040" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/MM010_StockZone.PNG"></kbd>


Note: To know stock based on zone, Program MWS060 with sort order (30) by zone can be chosen.


[Go to Top](#table-of-contents)

## 2.2 PROCESS

Once the setup described in the previous section has been completed, the MWH functionality is ready to use from within Magento.

Note: Make sure the license and activation code of Wyomind Advanced Inventory extension are entered and activated.

The following sections cover MWH display in detail page.


### 2.2.1 MWH in Product detail page

### 2.2.1.1 Simple Product

Browse the product in the frontend and click on the product to view the product detail page.

<kbd><img alt="Frontend_Stock" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/Frontend_Stock.png"></kbd>

This is where the stock based on warehouses can be seen.

Similar split up can be viewed in the admin section on Catalog> Products

<kbd><img alt="Magento_Product" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/Magento_Product.PNG"></kbd>

Open the product, and click on ‘Advanced Inventory’ hyperlink

<kbd><img alt="Magento_AdvancedInventory" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/Magento_AdvancedInventory.PNG"></kbd>

Set Manage Local Stocks to yes to see the stock split up

<kbd><img alt="Magento_Wyomind" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/Magento_Wyomind.PNG"></kbd>


### 2.2.1.2 Grouped Product

When Grouped Products are browsed in frontend and product details page appears as below.

<kbd><img alt="Magento_Wyomind" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/GroupProducts.PNG"></kbd>

To view multiple warehouse stock items for each product click ‘Know More’

<kbd><img alt="Magento_Wyomind" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/GroupedProduct_StockDetails.PNG"></kbd>


### 2.2.1.3 Configurable Product

When configurable product is browsed in the front end, Price and Quantity are displayed in the grid, where quantity value will be cumulative of all stock zones. (Value that is displayed in Qty field in product detail page)

Note: Qty is displayed for child items only if Order Grid extension is installed.

<kbd><img alt="Magento_Wyomind" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/ConfigPdt_Details.PNG"></kbd>

Price and Quantity can be switched from Dropdown grid.

<kbd><img alt="Magento_Wyomind" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/Configpdt_Quantity.PNG"></kbd>



[Go to Top](#table-of-contents)
