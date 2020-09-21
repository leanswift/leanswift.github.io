# **For Multi-tenant/CloudSuite environment**

Login into your Multi-tenant CloudSuite environment to get the following details:

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

There are two ways to find the M3 Logical Id.

**Step 1:**

Click on the “User Icon” and Go to “Admin Settings”.

<kbd><img alt="Admin Settings" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/MT/AdminSettings.png"></kbd>

After being redirected to the “Manage Applications” page, Double click on the “Infor M3”.

<kbd><img alt="Infor M3 Details" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/MT/DoubleClickOnInforM3.png"></kbd>

Double click on “Infor M3” will bring the “Application Details” page. There you can get the “Logical Id”.

<kbd><img alt="M3 Logical ID" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/MT/M3LogicalId.png"></kbd>

**Step 2:**

Go to “App Menu” and click on “ION Desk”.

<kbd><img alt="ION Desk Menu" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/MT/IONDESK_Menu.png"></kbd>

Click on "Connect" menu and select "Data Flows".

<kbd><img alt="Data Flows Menu" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/MT/DataFlows_Menu.png"></kbd>

From the list of Data Flows or Document Flows, Click on any DF, which uses "M3" as the application. 

Click on the "M3" Application. Select the checkbox and then click on the "Details" icon as marked in the image.

<kbd><img alt="Edit_M3Application" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/MT/Edit_M3Application.png"></kbd>

Note down the M3 Logical Id as shown below.

<kbd><img alt="M3_Logical_Id" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/MT/IonDesk_M3_LogicalID.png"></kbd>


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

<kbd><img alt="Infor ION API" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/ST/Infor_IONAPI_Menu.png"></kbd>

Click on “Available APIs” and search for “Infor M3” in the search text box. Then click on “Infor M3” from the search result.

<kbd><img alt="Search for Infor M3" style="width: 100%" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/ST/Search_InforM3.png"></kbd>


### OAuth Token URL and Credentials

Go to the Infor ION API menu, Click on the “Authorized Apps” then click on the “+” icon as shown in the below image.

<kbd><img alt="Create Credentials" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/ST/CreateCredential.png"></kbd>

Mention the Name, Description, choose the Type as “Backend Service” and click on Save.

<kbd><img alt="Generate Credentials" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/ST/GenerateCredentials.png"></kbd>

After clicking on “Save”, Click on the “Download Credentials” button.

<kbd><img alt="Download Credentials Button" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/ST/DownloadCredentialsButton.png"></kbd>

In the “Download Credentials" dialog box, do the below steps.

- Enable “Create Service Account” to get the Username and Password in the ".ionapi" file
- Choose “User Name”
- Click on “Download”
  	

<kbd><img alt="Download Credentials" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/ST/DownloadCredentials.png"></kbd>

On clicking “Download”, an “ionapi” file will get downloaded. Open the file with a text editor and get the credential details with the below image as a reference.

<kbd><img alt="IONAPI File Details" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/ST/sp-ionapi-file.png"></kbd>

### Logical Id

There are two ways to find the Logical ID.

**Step 1:**

Go to “App Menu” and click on “ION Desk”.

<kbd><img alt="ION Desk Menu" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/ST/IONDESK_Menu.png"></kbd>

Click on "Connect" menu and select "Document Flows".

<kbd><img alt="Data Flows Menu" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/ST/DocumentFlows_Menu.png"></kbd>

From the list of Data Flows or Document Flows, Click on anything which uses "M3" as the application. 

Click on the "M3" Application. Select the checkbox and then click on the "Details" icon as marked in the image.

<kbd><img alt="Edit_M3Application" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/ST/Edit_M3Application.png"></kbd>

Note down the M3 Logical Id as shown below.

<kbd><img alt="M3_Logical_Id" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/ST/IonDesk_M3_LogicalID.png"></kbd>

**Step 2:**

Login into your Partner Administrator tool. Under the `Agreement View` Tab, you will find the list of Partner Agreements.

Click on the Partner Agreement `M3BOD` `-> M3BODs_xxxxx` and note down the value of "ionFromLogicalId" from the Control Properties section as shown in the image.

<kbd><img alt="M3_Logical_Id" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/ST/ST_PA_M3_LogicalID.png"></kbd>


### M3 User

Login into your M3 H5 Client. Click on CTRL + R, Type “MNS150” and click “Enter”.

<kbd><img alt="MNS150 Program" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/ST/MNS150.png"></kbd>


### Basic Data

Basic Data includes 

- Company
- Division
- Facility



### **Infor Document Management**

#### IDM ION API Service URL

Click on “App Menu” and choose “Infor ION API”.

<kbd><img alt="Infor ION API Menu" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/ST/Infor_IONAPI_Menu.png"></kbd>

Click on “Available APIs” and search for “Infor Document Management” in the search text box. Then click on “Infor Document Management” from the search result.

<kbd><img alt="Infor Document Management" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/ST/Search_InforIDM.png"></kbd>

Click on “Infor Document Management”. From the Grid, Get the ION API Service URL(Rest API) and the Token URL as shown below.

<kbd><img alt="IDM Rest and Token API URL" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/supplierportal/src/images/supplierportal-m3-connection-info/ST/IDM_Rest%20and%20Token%20API%20URL.png"></kbd>

