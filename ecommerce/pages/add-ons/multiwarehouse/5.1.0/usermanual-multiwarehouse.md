
# **eConnect User Manual – Multi-Warehouse - V5.0.0**
![econnect_banner](../../../../../images/banner-econnect-m3.jpg)
## **LeanSwift eConnect for Infor M3 &amp; Magento** 


**Product Version**  **5.0.0**

**eConnect version 24.1.0**


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


With 20.3.0, there is a major technical architectural change in the solution.  from ION are now configured to be sent to a REST API in Magento, which in turn sends them to RabbitMQ for storage and processing by eConnect. In the previous versions, ION sends BODS to RabbitMQ directly.

### eConnect-base v6.4.0

- It provides connectivity to eLink and/or Infor systems with the use of a generic function that decides whether to call the eLink / ION APIs based on the M3 Connection Protocol chosen in the backend
- Acts as the communication layer for RabbitMQ Message consumption
- Acts as a core module for following LeanSwift Magento Extensions
  - eConnect
  - IDM
  - Supplier Portal
- eConnect add-ons depend on both eConnect-base and eConnect. eConnect and its Add-ons work only with eConnect base configured

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

Magento Community 2.4.7

Magento Enterprise 2.4.6

Infor M3 16.x

## 1.2 Points of Contact

### 1.2.1 Information

LeanSwift Solutions Inc provides this document and the software it describes. For additional information regarding support, licensing, functionality etc. please get in touch with LeanSwift Solutions Inc via the contact form at [http://www.leanswift.com](http://www.leanswift.com/)or email info@leanswift.com

## 1.3 Organization of the Manual

This manual does not cover any standard Magento functionality or user experience. The Magento user experience is customized and slightly different in each eCommerce implementation – though the general workflow is similar.

## 1.4 Acronyms and Abbreviations

ERP – Enterprise Resource Planning

MWH– Multi-Warehouse

[Go to Top](#table-of-contents)


## 2.0	MULTIWAREHOUSE ADD-ON

### 2.0.1 Summary

The MWH module extends the standard Magento functionality for displaying stock based on warehouse and stock zone by providing full integration to Infor M3 ERP.

MWH helps us discover the available stock based on the  Magento warehouse, stock zone, company, division, facility, and M3 warehouse.

We can add multiple warehouses and stock zones; this information will appear for each product in the front end.


### 2.0.2 Limitations
	
1. MSI doesn't support inventory management at the store view level.

2. Only swatches are supported for configurable items with MWH
 
3. The stock of the product is displayed only on the product detail page, and not on the list or cart page in the frontend.
    
4. For Configurable products, cumulative stock from all stock zones is displayed for each child item. This will be displayed only with the Order Grid extension.

5. Once the product inventory is synchronized with Magento, it is not possible to remove the warehouses configured in the settings.

[Go to Top](#table-of-contents)

## 2.1 CONFIGURATION

### 2.1.1 Magento Configuration-eLink

The MWH setting can be found under LEANSWIFT SOLUTIONS -> eConnect-eLink.
The options enable us to control MWH stock visibility in the backend and frontend.


<kbd><img alt="Magento_elink_Config" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/Magento_elink_Config.PNG"></kbd>


[Go to Top](#table-of-contents)

### 2.1.2 Magento Configuration-ION

Navigate to LEANSWIFT SOLUTIONS -> eConnect-ION -> Configuration -> Default Config -> Inventory Synchronization.


<kbd><img alt="Magento_ION_Config" src="https://raw.github.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/Inventory_Sync_%20Magento%20Config-%20ION.png"></kbd>


The only difference is that "Sync" Options are removed in ION and when stock BODS are received, the stock gets updated in Magento

#### Create Warehouses in Magento 

 Go to Stores->Inventory->Sources-> Manage Sources.


<kbd><img alt="Create_MWH-Sources" src="https://raw.github.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/Create_MWH-Sources.png"></kbd>


We can create a new warehouse by clicking the Add New Sources button. Enter all required information in the General, Contact Info, and Address data section. Click the Save & Continue button.

Now, the newly created warehouse will be available in the Magento Warehouse dropdown under the eConnect configuration.


<kbd><img alt="General_WH _Creation.png" src="https://raw.github.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/General_WH%20_Creation.png"></kbd>


<kbd><img alt="Contact_Info.png" src="https://raw.github.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/Contact_Info.png"></kbd>


<kbd><img alt="Address_Data.png" src="https://raw.github.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/Address_Data.png"></kbd>

 ### Create New Stock and Assign Sources for Stock
 
 Go to Stores->Inventory->Stocks-> Manage Stock.

 <kbd><img alt="Manage_Stock" src="https://raw.github.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/Manage_Stock.png"></kbd>
 

Click on ‘Add New Stock’ which allows us to create a new stock by entering the name and selecting the sales channels.


<kbd><img alt="Create_New_Stock" src="https://raw.github.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/Create_New_Stock.png"></kbd>
																					    

<kbd><img alt="sources_Stock" src="https://raw.github.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/sources_Stock.png"></kbd>


Click on ‘Assign Sources’ to view the list of sources we created under ‘Sources’. Select the desired sources and click ‘Done’.The selected sources will then appear under Assigned Sources.


 <kbd><img alt="sources_Stock" src="https://raw.github.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/Assign Sources.png"></kbd> 


<kbd><img alt="sources_Stock" src="https://raw.github.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/Assign Sources1.png"></kbd> 


 
 Multiple Stock zones can be configured for the same warehouse like below:


<kbd><img alt="Multiple_Stock Zone _Same WH.png" src="https://raw.github.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/Multiple_Stock Zone _Same WH.png"></kbd> 


When the stock is updated in stock zone YB, a BOD gets generated with value in YB which gets updated in eConnect.

When the stock is updated in stock zone Y9, a BOD gets generated with the value from MMS002’s ‘On-hand approve’ (YB+Y9). This value will get updated in eConnect in the Y9 zone

Now if YB is again updated with stock, ((new value in Y9) +YB) gets updated in the Y9 zone in reconnect and so on.

NOTE: This might be based on StockZone-Location settings in M3. If only one stock zone-warehouse is configured, the value that comes in BOD for that respective stock zone gets updated.


[Go to Top](#table-of-contents)

### 2.1.3 M3 Configuration

Stock zone can be viewed/created in program MMS040

<kbd><img alt="M3_MMS040" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/M3_MMS040.PNG"></kbd>

These are the available stock zones for the logged-in Comp/Div.

To know the stock of the product based on zone, open the Program MWS060 with sort order (30) by zone.

<kbd><img alt="M3_MMS002" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/M3_MMS002.PNG"></kbd>

MMS010 displays the Location-Stock Zone mapping

<kbd><img alt="M3_MMS040" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/MMS010.PNG"></kbd>


<kbd><img alt="M3_MMS040" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/MM010_StockZone.PNG"></kbd>


Note: To know stock based on zone, Open Program MWS060 with sort order (30) by zone can be chosen.


[Go to Top](#table-of-contents)

## 2.2 PROCESS

Once the setup described in the previous section has been completed, the MWH functionality is ready to use from within Magento.


The following sections cover the MWH Stocks display in detail page.


### 2.2.1 MWH in Product detail page

### 2.2.1.1 Simple Product

Browse the product in the frontend and click on the product to view the product detail page.


<kbd><img alt="Frontend_Stock" src="https://raw.github.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/Simple_Product.png"></kbd>


Stocks of the product based on warehouses are displayed.

A similar split up can be viewed in the Magento admin section on Catalog -> Products.


<kbd><img alt="Product_admin_view" src="https://raw.github.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/Product_Admin_View.png"></kbd>

Open the product to view the split up under sources.


<kbd><img alt="Product_admin_view_Sources" src="https://raw.github.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/Product_Admin_View_Sources.png"></kbd>








### 2.2.1.2 Grouped Product

When Grouped Products are browsed in frontend and product details page appears as below.


<kbd><img alt="Magento_Wyomind" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/GroupProducts.PNG"></kbd>

To view multiple warehouse stock items for each product click ‘Know More’.


<kbd><img alt="Magento_Wyomind" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/GroupedProduct_StockDetails.PNG"></kbd>


### 2.2.1.3 Configurable Product


When configurable product is browsed in the front end, Price and Quantity are displayed in the grid, where quantity value will be cumulative of all stock zones. (Value that is displayed in Qty field in product detail page)

Note: Qty is displayed for child items only if Order Grid extension is installed.


<kbd><img alt="Magento_Wyomind" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/ConfigPdt_Details.PNG"></kbd>


Price and Quantity can be switched from Dropdown grid.


<kbd><img alt="Magento_Wyomind" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/multiwarehouse/Configpdt_Quantity.PNG"></kbd>



[Go to Top](#table-of-contents)


