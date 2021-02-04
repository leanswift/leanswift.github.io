# **EConnect User Manual – IDM**
![econnect_banner](../../../../../images/banner-econnect-m3.jpg)
## **LeanSwift eConnect for Infor M3 &amp; Magento** 


### **Product Version**  **3.2.0**

**eConnect-base version 5.0.0**

**eConnect version 20.3.0**


# **Table of contents**


- [GENERAL INFORMATION](#general-information)
  - [1.1 System Overview](#11-system-overview)
  - [Architecture](#architecture)
    - [eConnect-base v5.0.0](#econnect-base-v500)
  - [1.2 Points of Contact](#12-points-of-contact)
    - [1.2.1 Information](#121-information)
  - [1.3 Organization of the Manual](#13-organization-of-the-manual)
  - [1.4 Acronyms and Abbreviations](#14-acronyms-and-abbreviations)
  - [2.0 IDM ADD-ON](#20-idm-add-on)
    - [2.0.1 Summary](#201-summary)
    - [2.0.2	Assumptions/Limitations](#202-assumptions/limitations)
  - [2.1 CONFIGURATION](#21-configuration)
    - [2.1.1 Upload Configuration](#211-upload-configuration)
    - [2.1.2 Download Configuration](#212-download-configuration)
    - [2.1.3 Search Configuration](#213-search-configuration)
    - [2.1.4 Mapping](#214-mapping)
  - [2.2 My Invoices Frontend – IDM Download](#22-my-invoices-frontend--idm-download)
  - [2.3 Code Snippet](#23-code-snippet)
   

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


**Add-ons**

The add-ons for LeanSwift eConnect provide extended functionality over the standard features available on eConnect Core.

These add-ons can, if necessary, be modified, and new add-ons can be added to fulfill specific customer requirements.

**User interface**

During setup, the Magento Admin panel is used to configure which transactions that should be used and how they should function. There is also additional configuration within the Connector to support the transactions.

**Validated versions**

  Magento Open Source 2.4.1 

  Magento Commerce 2.4.1

  Infor M3 16.x


## 1.2 Points of Contact

### 1.2.1 Information

This document and the software it describes are provided by LeanSwift Solutions Inc. For additional information regarding support, licensing, functionality etc. please contact LeanSwift Solutions Inc via contact form at [http://www.leanswift.com](http://www.leanswift.com/)or email info@leanswift.com

## 1.3 Organization of the Manual

This manual is not intended to cover any standard Magento functionality or user experience. The Magento user experience is customized and slightly different in each eCommerce implementation – though the general workflow is similar.

## 1.4 Acronyms and Abbreviations

ERP – Enterprise Resource Planning

IDM – Infor Document Management

[Go to Top](#table-of-contents)

## 2.0 IDM ADD-ON

### 2.0.1 Summary

The LeanSwift IDM extension for Infor M3 provides the ability to upload, download (multiple files for ION) and search documents in IDM. Also, when the IDM extension is installed along with eConnect, eConnect provides the ability to download invoices from the “My Invoices” page. 

Note: All settings are defined only on the Global level and not on the Store level. 

### 2.0.2	Assumptions/Limitations

  ❖	A functional instance of IDM with access to its REST API is assumed to exist.

  ❖	Connection to IDM is via LeanSwift eLink. Hence appropriate configuration options with respect to IDM on eLink will have to be in place. 

  ❖	Initial configurations have to be done under LeanSwift > IDM or Stores > Configuration > LeanSwift Solutions > IDM.

  ❖	For all three, Upload, Download and Search functionality, backend functions are exposed to be accessed via code, for any use case in the frontend, as needed. 

  ❖	775 permissions should be given to Magento_Root/pub/media/leanswift/idm/ to allow DISK WRITE

[Go to Top](#table-of-contents)


## 2.1 CONFIGURATION

### 2.1.1 Upload Configuration

  ●	Enable Upload - Option can be set to Yes or No

  ●	Allowed File Types – File extensions that are allowed to be uploaded to IDM. This field is not mandatory

  ●	Cron / Real-time – Documents will be uploaded to IDM based on this option. If cron is chosen, cron expression should be provided to upload the files on a periodic basis

  ●	Configurable Options to Upload – Select the Document Type from the drop-down list, required Attribute Type(s), Used In[Should be unique to identify the configuration]. Can add as many options as necessary

  ●	Clears the uploaded files to IDM – Clears the documents stored under Magento_Root/pub/media/leanswift/idm/upload/ folder periodically based on cron expression. It’s good practice to configure suitable cron expressions here to manage disk space.

<kbd><img alt="eLink Architecture" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/ECNT-1736/ecommerce/images/add-ons/idm/IDM_UploadConfig.PNG"></kbd>


### 2.1.2 Download Configuration

  ●	Enable Download - Option can be set to Yes or No

  ●	Cron / Real-time – Documents will be downloaded from IDM based on this option. If cron is chosen, cron expression should be given to download the files from IDM on a periodic basis

  ●	Configurable Options to Download – Select the Document Type, required Attribute Type, Operation, Used In [Should be unique to identify the configuration]. Can add as many options as necessary

  ●	Clears the downloaded files to IDM – Clears the documents stored under Magento_Root/pub/media/leanswift/idm/download/ folder periodically based on cron expression. It’s good practice to configure suitable cron expression here to manage disk space


  <kbd><img alt="eLink Architecture" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/ECNT-1736/ecommerce/images/add-ons/idm/Download_Configuration.png"></kbd>



### 2.1.3 Search Configuration

  ●	Enable Search - Option can be set to Yes or No

  ●	Configurable Options to Search – Select the Document Type, required Attribute Type, Operation, Offset and Limit

  <kbd><img alt="eLink Architecture" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/ECNT-1736/ecommerce/images/add-ons/idm/Search_Configuration.png"></kbd>


### 2.1.4 Mapping

  <kbd><img alt="eLink Architecture" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/ECNT-1736/ecommerce/images/add-ons/idm/Mapping.png"></kbd>

  ●	Attribute Key refers to M3_AttributeKey Name of IDM Document Type and the Custom key is the one we name it for our reference which we will use in code to retrieve M3_AttributeKey mapped here.

  ●	M3_AttributeKeys chosen for Upload Document type may vary for the Single Tenant and Multi-Tenant environment. Since we have to use those M3_Attribute keys in our code for Upload functionality, we now map it to a common custom key.

  ●	So, instead of changing M3_AttributeKeys in code for ST & MT, updating the mapping section in the backend is enough.

[Go to Top](#table-of-contents)


## 2.2 My Invoices Frontend – IDM Download 

  ●	Invoice template in LeanSwift eConnect has been overwritten in IDM Module to support download of invoice documents from IDM

  ●	Clicking on PDF Icon will download the document for the invoice from IDM

  ●	If Download option is set to Real-time in backend, then on clicking the PDF icon, file will be downloaded immediately and opened in new tab

  ●	If Download option is set to Cron, a message “File will be downloaded via cron” will be displayed. Download of document will happen in the background as per the scheduled      cron and will be available for viewing in the frontend afterwards. 

  <kbd><img alt="eLink Architecture" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/ECNT-1736/ecommerce/images/add-ons/idm/Invoice_Download.png"></kbd>


**ION version:**

For ION version we have an additional fields 

1. Service URL for ION

2. Document Root is Pub or Not

  <kbd><img alt="eLink Architecture" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/ECNT-1736/ecommerce/images/add-ons/idm/ION_GeneralConfig.png"></kbd>

We also have an additional functionality which is importing IDM configuration using import option unlike the cron option in elink version

Once user clicks on Import button, IDM configuration will be imported from M3.

  <kbd><img alt="eLink Architecture" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/ECNT-1736/ecommerce/images/add-ons/idm/IDM_ImportConfig.PNG"></kbd>

[Go to Top](#table-of-contents)


## 2.3 Code Snippet

**How to implement IDM in new custom page**

  ●	 Configure options to download, upload with attribute type, operation and used in.

  ●	To add IDM document add handle in custom layout page

    <update handle="econnect_idm_document"/>
    
  ●	To include the download in custom template included in below code

    //give custom template if needed another template   
    $downloadData['documentName'] = $dynamicNumber;   
    //used in configured in backend should be given as document type   
    $downloadData['documentType'] = $documentType;    
    echo $this->getLayout()    
      ->createBlock('LeanSwift\Idm\Block\Download')
      ->setDocumentData($downloadData)
      ->toHtml();
    
    
  ●	To include the upload in custom template included in below code

    //give custom template if needed another template    
    //used in configured in backend should be given as document type   
    $uploadData['documentType'] = $documentType;   
    $uploadData['documentName'] = $dynamicNumber;   
    //attribute data should match the attributes configured in backend.   
    $uploadData['documentData'] = ['attribute_data'=>$documentType];
    echo $this->getLayout()
      ->createBlock('LeanSwift\Idm\Block\Upload')
      ->setDocumentData($uploadData)
      ->toHtml();


  ●	Change JS if needed to support new template. Can use the Javascript Mixin

**To change the custom values In LeanSwift/Econnect/view/frontend/templates/invoice.phtml, change snippet as**

     <?php 	
    $invoiceNumber = $this->getData('invoice_number');
    if($invoiceNumber) {
    $downloadData['documentName'] = $invoiceNumber;
    $downloadData['documentType'] = "Invoice";
    echo $this->getLayout()
        ->createBlock('LeanSwift\Idm\Block\Download')
        ->setDocumentData($downloadData)
        ->toHtml();
    $uploadData['documentType'] = "Invoice";
    $uploadData['documentName'] = $invoiceNumber;
    $uploadData['documentData'] = ['MDS_id1'=>$invoiceNumber];
    echo $this->getLayout()
        ->createBlock('LeanSwift\Idm\Block\Upload')
        ->setDocumentData($uploadData)
        ->toHtml();
    }
    ?>

[Go to Top](#table-of-contents)
