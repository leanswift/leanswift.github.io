# **For Multi-tenant/CloudSuite environment**

Login into your Multi-tenant CloudSuite environment to get the following details:

### ION API Service URL

Click on “App Menu” and choose “Infor ION API”.

<kbd><img alt="Infor ION API" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/ecommerce/images/econnect-sxe-connection-info/MT/Infor_IONAPI_Menu.png"></kbd>

Click on the “Available APIs” menu from the left side menus and search for "Infor Distribution SX.e" in the search text box. You will get the two similar results but with different source. Click on the one which has the source as "Infor Provisioned" as shown in the image.

<kbd><img alt="Infor ION API" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/ecommerce/images/econnect-sxe-connection-info/MT/Search_InforDistribution_SXe.png"></kbd>

Search for "SX API REST Service" in the description box. Then click on the arrow mark under the Details column in the row which has description as "SX API REST Service".

<kbd><img alt="Search for Infor M3" style="width: 100%" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/ecommerce/images/econnect-sxe-connection-info/MT/Search_SXAPIRESTService.png"></kbd>

Refer to the below image and note down the ION API Service URL.

<kbd><img alt="Infor ION API Service Url" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/ecommerce/images/econnect-sxe-connection-info/MT/ION_API_ENDPOINT_URL.png"></kbd>


### OAuth Token URL and Credentials

Go to the Infor ION API menu, Click on the “Authorized Apps” then click on the “+” icon as shown in the below image.

<kbd><img alt="Create Credentials" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/ecommerce/images/econnect-sxe-connection-info/MT/CreateCredential.png"></kbd>

Mention the Name, Description, choose the Type as “Backend Service” and click on Save.

<kbd><img alt="Generate Credentials" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/ecommerce/images/econnect-sxe-connection-info/MT/GenerateCredentials.png"></kbd>

After clicking on “Save”, Click on the “Download Credentials” button.

<kbd><img alt="Download Credentials Button" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/ecommerce/images/econnect-sxe-connection-info/MT/DownloadCredentialsButton.png"></kbd>

In the “Download Credentials" dialog box, do the below steps.

- Enable “Create Service Account” to get the Username and Password in the ".ionapi" file
- Choose “User Name”
- Click on “Download”
		

<kbd><img alt="Download Credentials" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/ecommerce/images/econnect-sxe-connection-info/MT/DownloadCredentials.png"></kbd>

On clicking “Download”, an “ionapi” file will get downloaded. Open the file with a text editor and get the credential details with the below image as a reference.

<kbd><img alt="IONAPI File Details" src="https://github.com/leanswift/leanswift.github.io/blob/UserGuide/ecommerce/images/econnect-sxe-connection-info/MT/eConnect-ionapi-file.png"></kbd>




### Basic Data

Basic Data includes 

- Company
- Division
- Facility
- Warehouse
- Order Type
- Price List
- M3 Customer # TEMPLATE
- Charge ID
- Freight
