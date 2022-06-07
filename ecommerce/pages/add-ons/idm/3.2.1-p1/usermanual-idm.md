# **eConnect User Manual – IDM**
![econnect_banner](../../../../../images/banner-econnect-m3.jpg)
## **LeanSwift eConnect for Infor M3 &amp; Magento** 


### **Product Version**  **3.2.1**

**eConnect version 20.3.0**

# IDM Add-on





# GENERAL INFORMATION

 
## 1.1 System Overview

LeanSwift eConnect for Infor M3 provides a seamless integration between Magento and Infor M3 ERP. The product consists of a Magento extension, and a Tomcat based server application that manages the communication with the M3 ERP system.

LeanSwift eConnect for Infor M3 employs a layered architecture to allow more flexibility in supporting different versions of Magento and Infor M3, and to allow independent upgrades. The two components are versioned individually to more easily adapt to different M3- &amp; Magento versions.

![](RackMultipart20220607-1-bgyxzv_html_c8851cdc159a2683.png)

**Transactions**

With eConnect 18.2.3, the following add-ons are available:

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

  
## 1.2 Points of Contact

   
### 1.2.1 Information

This document and the software it describes are provided by LeanSwift Solutions Inc. For additional information regarding support, licensing, functionality etc. please contact LeanSwift Solutions Inc via contact form at [http://www.leanswift.com](http://www.leanswift.com/).

 
## 1.3 Organization of the Manual

This manual is not intended to cover any standard Magento functionality or user experience. The Magento user experience is customized and slightly different in each eCommerce implementation – though the general workflow is similar.

## 1.4 Acronyms and Abbreviations

IDM – Infor Document Management

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

 
## 2.1 CONFIGURATION

The configuration required for the IDM add-on can be separated in three parts – Upload configuration, Download Configuration and Search configuration.

    
### 2.1.1 Upload Configuration

- _Enable Upload_- Option can be set to Yes or No.
- _Allowed File Types_– File extensions to be upload to IDM. This field is not mandatory.
- _Cron / Real-time_ – Documents will be uploaded to IDM based on this option. If cron is chosen, cron expression should be given to upload the files.
- _Configurable Options to Upload_– Select the Document Type, required attribute type, Used In [Should be unique to identify the configuration].
- _Clears the uploaded files to IDM_– Clears the _leanswift\_idm\_upload_ table and documents stored under _Magento\_Root/pub/media/leanswift/idm/upload/_ folder based on cron expression.

![](RackMultipart20220607-1-bgyxzv_html_94f65ae310573ab7.png)

    
### 2.1.2 Download Configuration

- _Enable Download_- Option can be set to Yes or No.
- _Cron / Real-time_ – Documents will be downloaded from IDM based on this option. If cron is chosen, cron expression should be given to download the files from IDM.
- _Configurable Options to Download_– Select the Document Type, required attribute type, Operation, Used In [Should be unique to identify the configuration].
- _Clears the downloaded files to IDM_– Clears the _leanswift\_idm\_download_ table and documents stored under _Magento\_Root/pub/media/leanswift/idm/download/_ folder based on cron expression.

![](RackMultipart20220607-1-bgyxzv_html_cfa12867c6078d6f.png)

    
### 2.1.2.0 Frontend Part – IDM Download.

- Invoice template in the eConnect module has overwritten in IDM Module.
- Clicking on the PDF Icon will download the documents for the invoice from IDM.
- If Download option is set to _Real-time_ in backend, then the file will be opened in new tab on clicking icon.
- If Download option is _Cron_, user will get a message like &quot;File will be downloaded via cron&quot;.

![](RackMultipart20220607-1-bgyxzv_html_34efe15d5d33fcc3.png)



### 2.1.3 Search Configuration

- _Enable Search_- Option can be set to Yes or No.
- _Configurable Options to Search_– Select the Document Type, required attribute type, Operation, Offset and Limit.

![](RackMultipart20220607-1-bgyxzv_html_fcdf7f6303ac5206.png)

### 2.1.4 Code Snippet

#### How to implement IDM in new custom page

- Configure options to download, upload with attribute type, operation and used in.

|
- To add IDM document add handle in custom layout page

 |
| --- |
| \&lt;update handle=&quot;econnect\_idm\_document&quot;/\&gt; |
|
 |

- To include the download in custom template included in below code

| //give custom template if needed another template$downloadData[&#39;documentName&#39;] = $dynamicNumber;//used in configured in backend should be given as document type
 $downloadData[&#39;documentType&#39;] = $documentType;echo$this-\&gt;getLayout()
 -\&gt;createBlock(&#39;LeanSwift\Idm\Block\Download&#39;)
 -\&gt;setDocumentData($downloadData)
 -\&gt;toHtml(); |
| --- |

- To include the upload in custom template included in below code

| //give custom template if needed another template//used in configured in backend should be given as document type$uploadData[&#39;documentType&#39;] = $documentType;$uploadData[&#39;documentName&#39;] = $dynamicNumber;//attribute data should match the attributes configured in backend.
 $uploadData[&#39;documentData&#39;] = [&#39;attribute\_data&#39;=\&gt;$documentType];
echo$this-\&gt;getLayout()
 -\&gt;createBlock(&#39;LeanSwift\Idm\Block\Upload&#39;)
 -\&gt;setDocumentData($uploadData)
 -\&gt;toHtml(); |
| --- |
|
 |

- Change JS if needed to support new template. Can use the [Javascript Mixin](https://devdocs.magento.com/guides/v2.3/javascript-dev-guide/javascript/js_mixins.html)

**To change the custom values In LeanSwift/Econnect/view/frontend/templates/invoice.phtml, change snippet as**

| \&lt;?php
 $invoiceNumber = $this-\&gt;getData(&#39;invoice\_number&#39;);if($invoiceNumber) {$downloadData[&#39;documentName&#39;] = $invoiceNumber;$downloadData[&#39;documentType&#39;] = &quot;Invoice&quot;;echo $this-\&gt;getLayout()-\&gt;createBlock(&#39;LeanSwift\Idm\Block\Download&#39;)-\&gt;setDocumentData($downloadData)-\&gt;toHtml();$uploadData[&#39;documentType&#39;] = &quot;Invoice&quot;;$uploadData[&#39;documentName&#39;] = $invoiceNumber;$uploadData[&#39;documentData&#39;] = [&#39;MDS\_id1&#39;=\&gt;$invoiceNumber];echo $this-\&gt;getLayout()-\&gt;createBlock(&#39;LeanSwift\Idm\Block\Upload&#39;)-\&gt;setDocumentData($uploadData)-\&gt;toHtml();}
?\&gt; |
| --- |


