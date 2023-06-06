# **eConnect User Manual – IDM**
![econnect_banner](../../../../../images/banner-econnect-m3.jpg)
## **LeanSwift eConnect for Infor M3 &amp; Magento** 


### **Product Version**  **3.2.1**

**eConnect version 20.3.0**

# IDM Add-on

# Table of contents

- [GENERAL INFORMATION](#general-information)
  - [1.1 System Overview](#11-system-overview)
  - [1.2 Points of Contact](#12-points-of-contact)
    - [1.2.1 Information](#121-information)
  - [1.3 Organization of the Manual](#13-organization-of-the-manual)
  - [1.4 Acronyms and Abbreviations](#14-acronyms-and-abbreviations)
  - [Architecture](#architecture)
    - [eConnect-base v5.0.0](#econnect-base-v500)
    - [Architecture with LeanSwift eLink](#architecture-with-leanswift-elink)
    - [Architecture with ION for multi-tenant Cloud M3](#architecture-with-ion-for-multi-tenant-cloud-m3)
- [2.0 IDM ADD-ON](#20-idm-add-on)
    - [2.0.1 Summary](#201-summary)
    - [2.0.2 Assumptions/Limitations](#202-assumptionslimitations)
  - [2.1 CONFIGURATION](#21-configuration)
    - [2.1.1 General Configuration](#211-general-configuration)
    - [2.1.2 Upload Configuration](#212-upload-configuration)
    - [2.1.3 Download Configuration](#213-download-configuration)
    - [2.1.2.0 Frontend Part – IDM Download.](#2120-frontend-part--idm-download)
    - [2.1.4 Search Configuration](#214-search-configuration)
    - [2.1.5 Email IDM Document](#215-email-idm-document)
    - [2.1.6 Mapping](#216-mapping)
    - [2.1.7 Import Configuration](#217-import-configuration)
    - [2.1.8 Code Snippet](#214-code-snippet)


# GENERAL INFORMATION

 
## 1.1 System Overview

LeanSwift eConnect for Infor M3 provides a seamless integration between Magento and Infor M3 ERP. The product consists of a Magento extension, and a Tomcat based server application that manages the communication with the M3 ERP system.

LeanSwift eConnect for Infor M3 employs a layered architecture to allow more flexibility in supporting different versions of Magento and Infor M3, and to allow independent upgrades. The two components are versioned individually to more easily adapt to different M3- &amp; Magento versions.


**Transactions**

With eConnect 20.3.0, the following add-ons are available:

- Sales Rep
- RMA
- Gift Card
- Order Grid
- Material Plan
- Order Edit
- IDM

These add-ons can if necessary be modified, and new add-ons can be added to fulfill specific customer requirements.

**User interface**

During setup, the Magento Admin panel is used to configure which transactions that should be used and how they should function. There is also additional configuration within the Connector to support the transactions.

**Validated versions**

Magento Community 2.2.4 and up

Magento Enterprise 2.2.4 and up

Infor M3 13.x

[Go to Top](#table-of-contents)
  
## 1.2 Points of Contact

   
### 1.2.1 Information

This document and the software it describes are provided by LeanSwift Solutions Inc. For additional information regarding support, licensing, functionality etc. please contact LeanSwift Solutions Inc via contact form at [http://www.leanswift.com](http://www.leanswift.com/).

 
## 1.3 Organization of the Manual

This manual is not intended to cover any standard Magento functionality or user experience. The Magento user experience is customized and slightly different in each eCommerce implementation – though the general workflow is similar.

## 1.4 Acronyms and Abbreviations

IDM – Infor Document Management

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


<kbd><img alt="eLink Architecture" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/sales-rep/elink_Architecture.jpg"></kbd>


### Architecture with ION for multi-tenant Cloud M3


<kbd><img alt="ION Architecture" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/sales-rep/ION_Architecture.jpg"></kbd>

The add-ons for LeanSwift eConnect provide extended functionality over the standard features available on eConnect Core.

These add-ons can, if necessary, be modified, and new add-ons can be added to fulfill specific customer requirements.

[Go to Top](#table-of-contents)

# 2.0 IDM ADD-ON

    
### 2.0.1 Summary

The _IDM_ add-on to LeanSwift eConnect for Infor M3 provides the ability to upload, download and search documents in IDM.

Note:All settings are defined only on the Global level and not on the store level.

   
### 2.0.2 Assumptions/Limitations

- Initial configurations has to be done under LeanSwift>IDM or Stores>Configuration>LeanSwift Solutions>IDM.

For Upload,

- In Magento admin panel, Document Type, Attribute Type [Can select multiple options] and a unique name for _Used In_ field should be given when having multiple upload configurations. Used in field is mandatory.

_Note:_ Frontend part is not supported. Only function is exposed.

For Download,

- In Magento admin panel, Document Type, Attribute Type, Operator and a unique name for _Used In_ field should be given when having multiple download configurations. Used in field is mandatory.

_Note:_ Frontend part is supported.

For Search,

- In Magento admin panel, Document Type, Attribute Type, Operator, Offset and Limit can be given.

_Note:_ Frontend part is not supported. Only function is exposed.

- **775** permissions should be given to _Magento\_Root/pub/media/leanswift/idm/._

 [Go to Top](#table-of-contents)
 
## 2.1 CONFIGURATION

The configuration required for the IDM add-on can be separated in three parts – Upload configuration, Download Configuration and Search configuration.

### 2.1.1 General Configuration

ION API service URL has to be mentioned here

<kbd><img alt="general config" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/idm/ION_GeneralConfig.png"></kbd>

    
### 2.1.2 Upload Configuration

- _Enable Upload_- Option can be set to Yes or No.
- _Allowed File Types_– File extensions to be upload to IDM. This field is not mandatory.
- _Cron / Real-time_ – Documents will be uploaded to IDM based on this option. If cron is chosen, cron expression should be given to upload the files.
- _Configurable Options to Upload_– Select the Document Type, required attribute type, Used In [Should be unique to identify the configuration].
- _Clears the uploaded files to IDM_– Clears the _leanswift\_idm\_upload_ table and documents stored under _Magento\_Root/pub/media/leanswift/idm/upload/_ folder based on cron expression.


<kbd><img alt="upload config" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/idm/IDM_UploadConfig.PNG"></kbd>


    
### 2.1.3 Download Configuration

- _Enable Download_- Option can be set to Yes or No.
- _Cron / Real-time_ – Documents will be downloaded from IDM based on this option. If cron is chosen, cron expression should be given to download the files from IDM.
- _Configurable Options to Download_– Select the Document Type, required attribute type, Operation, Used In [Should be unique to identify the configuration].
- _Clears the downloaded files to IDM_– Clears the _leanswift\_idm\_download_ table and documents stored under _Magento\_Root/pub/media/leanswift/idm/download/_ folder based on cron expression.

<kbd><img alt="upload config" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/idm/Download_Configuration.png"></kbd>
    
### 2.1.2.0 Frontend Part – IDM Download.

- Invoice template in the eConnect module has overwritten in IDM Module.
- Clicking on the PDF Icon will download the documents for the invoice from IDM.
- If Download option is set to _Real-time_ in backend, then the file will be opened in new tab on clicking icon.
- If Download option is _Cron_, user will get a message like &quot;File will be downloaded via cron&quot;.

<kbd><img alt="download config" src="https://github.com/leanswift/leanswift.github.io/blob/ECNT-2313/ecommerce/images/add-ons/idm/Invoice_Download.png"></kbd>


### 2.1.4 Search Configuration

- _Enable Search_- Option can be set to Yes or No.
- _Configurable Options to Search_– Select the Document Type, required attribute type, Operation, Offset and Limit.

<kbd><img alt="search config" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/idm/Search_Configuration.png"></kbd>

### 2.1.5 Email IDM Document

This feature enables mails to be sent


<kbd><img alt="email config" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/idm/Email_IDM_config.png"></kbd>

### 2.1.6 Mapping

<kbd><img alt="mapping config" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/idm/Mapping.png"></kbd>

### 2.1.7 Import Configuration

Import configuration fetches IDM related configurable options from M3


<kbd><img alt="search config" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/idm/IDM_ImportConfig.PNG"></kbd>



### 2.1.8 Code Snippet

#### How to implement IDM in new custom page

- Configure options to download, upload with attribute type, operation and used in.


- To add IDM document add handle in custom layout page

  <update handle="econnect_idm_document"/>

- To include the download in custom template included in below code

<kbd><img alt="general config" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/idm/template1.png"></kbd>


- To include the upload in custom template included in below code

  <kbd><img alt="general config" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/idm/template2.png"></kbd>

- Change JS if needed to support new template. Can use the [Javascript Mixin](https://devdocs.magento.com/guides/v2.3/javascript-dev-guide/javascript/js_mixins.html)

**To change the custom values In LeanSwift/Econnect/view/frontend/templates/invoice.phtml, change snippet as**

<kbd><img alt="general config" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/master/ecommerce/images/add-ons/idm/template3.png"></kbd>

[Go to Top](#table-of-contents)

