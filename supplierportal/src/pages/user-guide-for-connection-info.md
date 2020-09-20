# **For Multi-tenant/CloudSuite environment**

Login into your Multi-tenant CloudSuitevironment to get the following details:

### ION API Service URL

Click on “App Menu” and choose “Infor ION API”

<kbd><img alt="Infor ION API" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/MT/Infor_IONAPI_Menu.png"></kbd>

Click on “Available APIs” and search for “Infor M3” in the search text box. Then click on “Infor M3” from the search result.

<kbd><img alt="Search for Infor M3" style="width: 100%" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/MT/Search_InforM3.png"></kbd>

Search for “Infor M3 MI v2” in the Description Box. Click on the arrow mark under the Details column as shown below.

<kbd><img alt="Infor M3 MI v2" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/MT/Search_ION_API_Service_URL.png"></kbd>

Refer to the below image and note down the ION API Service URL.

<kbd><img alt="Infor ION API Service Url" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/MT/ION_API_Service_URL.png"></kbd>


### OAuth Token URL and Credentials

Go to the Infor ION API menu, Click on the “Authorized Apps” then click on the “+” icon as shown in the below image.

<kbd><img alt="Create Credentials" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/MT/CreateCredential.png"></kbd>

Mention the Name, Description, choose the Type as “Backend Service” and click on Save.

<kbd><img alt="Generate Credentials" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/MT/GenerateCredentials.png"></kbd>

After clicking on “Save”, Click on the “Download Credentials” button.

<kbd><img alt="Download Credentials Button" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/MT/DownloadCredentialsButton.png"></kbd>

In the “Download Credentials" dialog box, do the below steps.

- Enable “Create Service Account” to get the Username and Password in the ".ionapi" file
- Choose “User Name”
- Click on “Download”
		

<kbd><img alt="Download Credentials" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/MT/DownloadCredentials.png"></kbd>

On clicking “Download”, an “ionapi” file will get downloaded. Open the file with a text editor and get the credential details with the below image as a reference.

<kbd><img alt="IONAPI File Details" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/MT/sp-ionapi-file.png"></kbd>


### Logical Id

Click on the “User Icon” and Go to “Admin Settings”.

<kbd><img alt="Admin Settings" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/MT/AdminSettings.png"></kbd>

After being redirected to the “Manage Applications” page, Double click on the “Infor M3”.

<kbd><img alt="Infor M3 Details" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/MT/DoubleClickOnInforM3.png"></kbd>

Double click on “Infor M3” will bring the “Application Details” page. There you can get the “Logical Id”.

<kbd><img alt="M3 Logical ID" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/MT/M3LogicalId.png"></kbd>


### M3 User

Go to “App Menu” and click on “Infor M3”.

<kbd><img alt="Infor M3 Menu" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/MT/Infor_M3_Menu.png"></kbd>

Click on CTRL + R, Type “MNS150” and click “Enter”.

<kbd><img alt="MNS150 Program" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/MT/MNS150.png"></kbd>


### Basic Data

Basic Data includes 

- Company
- Division
- Facility



### **Infor Document Management**

#### IDM ION API Service URL

Click on “App Menu” and choose “Infor ION API”.

<kbd><img alt="Infor ION API Menu" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/MT/Infor_IONAPI_Menu.png"></kbd>

Click on “Available APIs” and search for “Infor Document Management” in the search text box. Then click on “Infor Document Management” from the search result.

<kbd><img alt="Infor Document Management" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/MT/Search_InforIDM.png"></kbd>

Click on “Infor Document Management”. From the Grid, Get the ION API Service URL(Rest API) and the Token URL as shown below.

<kbd><img alt="IDM Rest and Token API URL" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/MT/IDM_Rest%20and%20Token%20API%20URL.png"></kbd>



# **For Single-tenant/On-Premise environment**

Login into your Single-tenant or On-Premise environment to get the following details:

### ION API Service URL

Click on “App Menu” and choose “Infor ION API”.

<kbd><img alt="Infor ION API" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/ecommerce/images/econnect-m3-connection-info/ST/Infor_IONAPI_Menu.png"></kbd>

Click on “Available APIs” and search for “Infor M3” in the search text box. Then click on “Infor M3” from the search result.

<kbd><img alt="Search for Infor M3" style="width: 100%" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/ecommerce/images/econnect-m3-connection-info/ST/Search_InforM3.png"></kbd>


### OAuth Token URL and Credentials

Go to the Infor ION API menu, Click on the “Authorized Apps” then click on the “+” icon as shown in the below image.

<kbd><img alt="Create Credentials" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/ecommerce/images/econnect-m3-connection-info/ST/CreateCredential.png"></kbd>

Mention the Name, Description, choose the Type as “Backend Service” and click on Save.

<kbd><img alt="Generate Credentials" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/ecommerce/images/econnect-m3-connection-info/ST/GenerateCredentials.png"></kbd>

After clicking on “Save”, Click on the “Download Credentials” button.

<kbd><img alt="Download Credentials Button" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/ecommerce/images/econnect-m3-connection-info/ST/DownloadCredentialsButton.png"></kbd>

In the “Download Credentials" dialog box, do the below steps.

- Enable “Create Service Account”
- Choose “User Name”
- Click on “Download”
  	

<kbd><img alt="Download Credentials" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/ecommerce/images/econnect-m3-connection-info/ST/DownloadCredentials.png"></kbd>

On clicking “Download”, an “ionapi” file will get downloaded. Open the file with a text editor and get the credential details with the below image as a reference.

<kbd><img alt="IONAPI File Details" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/ecommerce/images/econnect-m3-connection-info/ST/sp-ionapi-file.png"></kbd>


### Logical Id

Click on the “User Icon” and Go to “Admin Settings”.

<kbd><img alt="Admin Settings" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/ecommerce/images/econnect-m3-connection-info/ST/AdminSettings.png"></kbd>

After being redirected to the “Manage Applications” page, Double click on the “Infor M3”.

<kbd><img alt="Infor M3 Details" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/ecommerce/images/econnect-m3-connection-info/ST/DoubleClickOnInforM3.png"></kbd>

Double click on “Infor M3” will bring the “Application Details” page. There you can get the “Logical Id”.

<kbd><img alt="M3 Logical ID" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/ecommerce/images/econnect-m3-connection-info/ST/M3LogicalId.png"></kbd>


### M3 User

Login into your M3 H5 Client. Click on CTRL + R, Type “MNS150” and click “Enter”.

<kbd><img alt="MNS150 Program" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/ecommerce/images/econnect-m3-connection-info/ST/MNS150.png"></kbd>


### Basic Data

Basic Data includes 

- Company
- Division
- Facility



### **Infor Document Management**

#### IDM ION API Service URL

Click on “App Menu” and choose “Infor ION API”.

<kbd><img alt="Infor ION API Menu" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/ecommerce/images/econnect-m3-connection-info/ST/Infor_IONAPI_Menu.png"></kbd>

Click on “Available APIs” and search for “Infor Document Management” in the search text box. Then click on “Infor Document Management” from the search result.

<kbd><img alt="Infor Document Management" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/ecommerce/images/econnect-m3-connection-info/ST/Search_InforIDM.png"></kbd>

Click on “Infor Document Management”. From the Grid, Get the ION API Service URL(Rest API) and the Token URL as shown below.

<kbd><img alt="IDM Rest and Token API URL" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/ecommerce/images/econnect-m3-connection-info/ST/IDM_Rest%20and%20Token%20API%20URL.png"></kbd>

