

# Version 25.1.0 - User Manual- One-Day Deployment

<div id = "toc"></div>

# Table of contents

- [Introduction](#introduction)
- [Configuration Setup](#configuration-setup)
  - [Data Templates Packages](#data-templates-packages)
- [ION Authentication](#ion-authentication)
  - [Import History](#import-history)
- [Import IDM Configuration](#import-idm-configuration)
- [Import eConnect ION Configuration](#Import-eConnect-ION-Configuration)  
- [Upload ION components](#upload-ion-components)
  - [1.Configuration Setup](#1configuration-setup)
    - [Connection Point Packages](#connection-point-packages)
    - [Data Flow Packages](#data-flow-packages)
    - [Work Flow Packages](#work-flow-packages)
  - [2.Upload Connection Points, Data Flows, Workflows:](#2upload-connection-points-data-flows-workflows)
    - [Connection Point](#connection-point)
    - [Data Flows](#data-flows)
    - [Workflows](#workflows)
  - [ION Component Upload History](#ion-component-upload-history)

# Introduction
This is a new feature implemented to set configuration with one click and make eConnect Portal ready to use in one day.

Some of the configuration's fields are set as default values while installing the eConnect portal.
 
# Configuration Setup

## Data Templates Packages

- This will update eConnect-Base configurations at once click.
- Navigate to Leanswift -> eConnect-base -> Connectivity -> Configuration Setup -> Data Template Packages. 
- Admin users can update configuration values in the standard ‘config.csv’ template as per their environment requirements.
- When “Import” is clicked, values from the config.csv file will update the configuration field values.
- The config.csv file will be uploaded under "root_folder/template" in the server.
The list of values that are imported from the config.csv file are: 
	- Company
	- Division
	- authenticate_m3_user
	- queue_host
	- queue_port
	- queue_user
	- queue_password
	- queue_virtualhost
	- ion_workflow_logical_id
	- smtp_disable
	- smtp_transport
	- smtp_host
	- smtp_port	
	- smtp_username
	- smtp_password
	- smtp_auth
	- smtp_ssl
	- process_connect_model_url
	- cp_service_account
	- wf_service_account
	- proxy_url


![data_template_packages.png](../../../../ecommerce/images/one_day_deployment/data_template_packages.png)
 
![Config.csv file](../../../../ecommerce/images/one_day_deployment/config.csv_file.png)



<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>


# ION Authentication

- The ION API file will auto-populate other API URL fields in the configuration.
- Navigate to Leanswift -> eConnect base -> Connectivity -> Authentication -> ION API Credentials file. 
- Once the ION API file is uploaded the below fields will get auto-populated.

![ion_authentication_file_upload.png](../../../../ecommerce/images/one_day_deployment/ion_authentication_file_upload.png)


1. Leanswift -> Econnect Base -> service configuration -> API service url.

![ion_authentication_file_upload.png](../../../../ecommerce/images/one_day_deployment/ion_authentication_fields1.png)


2. Leanswift -> Econnect Base ->Authentication all field except M3 user.

![ion_authentication_file_upload.png](../../../../ecommerce/images/one_day_deployment/ion_authentication_fields2.png)


3. Leanswift -> Econnect Base ->ION Workflow Configuration -> API service Url.

![ion_authentication_file_upload.png](../../../../ecommerce/images/one_day_deployment/ion_authentication_fields3.png)


4. LeanSwift -> Idm -> Settings -> General Configuration -> ION Api service url.

![ion_authentication_file_upload.png](../../../../ecommerce/images/one_day_deployment/ion_authentication_fields5.png)


## Import History

Once the all the configuration is imported (eConnect IoN Configuration, M3 Configuration, IDM Settings), history of import is recorded.

To verify the import history, navigate to Leanswift -> eConnect Base -> Import History. 

![import_history.png](../../../../ecommerce/images/one_day_deployment/import_history.png)


<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>


# Import IDM Configuration

- For IDM configuration, navigate to Leanswift -> IDM-> Settings.
- Expand the menu Leanswift -> Initial load / Import -> Default Config -> Import IDM Configuration -> IDM Initial Load/ Configure.

![idm_import.png](../../../../ecommerce/images/one_day_deployment/idm_import.png)


- This will import/fetch Document Type and Attribute Type fields in the **Configurable Options to Upload** and **Configurable Options to Download** from IDM to configurations.

![idm_import.png](../../../../ecommerce/images/one_day_deployment/idm_upload.png)


After the import is clicked, import changes to the “Reset” Button.
If there are any changes in Document Type and Attribute Type from IDM, click the “Reset” button, newly added or updated values will be retrieved from IDM.

![idm_reset.png](../../../../ecommerce/images/one_day_deployment/idm_reset.png)


<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>


# Import eConnect ION Configuration:

- Import eConnect configuration is website-specific.
- Leanswift -> Initial load / Import -> Default website ->Import eConnect ION Configuration ->Initial Load/ Configure.

![AttributeSet_Category_Default.pang.png](../../../../ecommerce/images/one_day_deployment/AttributeSet_Category_Default.pang.png)


- When “Import” button is clicked it will fetch the M3 attributes values from Infor M3 and configure default values based on the values updated in “config.csv” file. M3 attribute fields are available in csv file.

- After the import is clicked, import changes to the Reset Button. 
![AttributeSet_Category_Default_reset.png](../../../../ecommerce/images/one_day_deployment/AttributeSet_Category_Default_reset.png)
  

If there are any newly added M3 attributes, when the “Reset” button is clicked, the newly added values will be retrieved from Infor M3 and configured based on the values available in the config.csv file.

- Leanswift -> Initial load / Import -> Main website ->Import eConnect ION Configuration ->Initial Load/ Configure.

 ![ION-inital-load.png](../../../../ecommerce/images/one_day_deployment/ION-inital-load.png)
 

  - When “Import” button is clicked it will fetch the M3 attributes values from Infor M3 and configure default values based on the values updated in “config.csv” file. M3 attribute fields are available in csv file.

  - After the import is clicked, import changes to the Reset Button.

![ION-inital-load_reset.png](../../../../ecommerce/images/one_day_deployment/ION-inital-load_reset.png)


When “Import” button is clicked it will fetch the M3 attributes values from Infor M3 and configure default values based on the values updated in “config.csv” file. M3 attribute fields are available in csv file.
- The following configurations have a RESET button during the installation of eConnect:
- Leanswift -> Initial load / Import -> Main website ->Import eConnect ION Configuration->Customer Master Mapping Configure, Customer Address Mapping Configure, Customer Address Mapping Configure.

![Default-reset.png](../../../../ecommerce/images/one_day_deployment/Default-reset.png)

When "RESET" button is clicked it will retrieves the default Configuration values for these Configuration Customer Master Mapping Configure,Customer Address Mapping Configure,Customer Address Mapping Configure..

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

# Upload ION components

The ION components can be configured in two different ways:

## 1. Configuration Setup 

At the time of eConnect Portal installation, the Connection Point file (Json), Data Flows file(zip), and Work Flows file(zip) should be given under "root_folder/template" in the server.

### Connection Point Packages

- Navigate to Leanswift -> eConnect-base -> Connectivity -> Configuration Setup -> Connection Point Packages.
- Once “Upload” is clicked, a success message is displayed. The Connection Point can be verified in Infor under OS -> ION -> Connect -> Connection Point.

![m3_connection_point.png](../../../../ecommerce/images/one_day_deployment/m3_connection_point.png)

- In the OS portal, initially, the connection point will be “Inactive” state, once the data flows are uploaded then the connection point will become “Active”.
- List of connection points: 
	- LS_CP_eConnect_SSD_API
- An error message” There's an issue with the input, or it already exists within Infor ION for ConnectionPoint.json Connection Point.” will be displayed if there is an issue in the file uploaded.

  ![connection_point_packages.png](../../../../ecommerce/images/one_day_deployment/connection_point_packages.png)


### Data Flow Packages

- Navigate to Leanswift -> eConnect-base -> Connectivity -> Configuration Setup -> Data Flow Packages.  
- Once “Upload” is clicked in Data Flow packages, the Data flows will automatically generate in Infor OS. 
- Once the file is uploaded, a success message is displayed. The activated data flow can be verified in M3 under ION Desk -> Connect -> Data flows.

![m3_data_flows.png](../../../../ecommerce/images/one_day_deployment/m3_data_flows.png)


The list of data flows are: 
	- LS_eConnect_DF_ShowToSync_BillToPartyMaster
        - LS_eConnect_DF_ShowToSync_BillToPartyMaster
        - LS_eConnect_DF_ShowToSync_CustomerPartyMaster
        - LS_eConnect_DF_ShowToSync_Invoice
        - LS_eConnect_DF_ShowToSync_ItemMaster
        - LS_eConnect_DF_ShowToSync_LSItemStock
        - LS_eConnect_DF_ShowToSync_LSPriceList
        - LS_eConnect_DF_ShowToSync_ReceivableTransaction
        - LS_eConnect_DF_ShowToSync_SalesOrder
        - LS_eConnect_DF_ShowToSync_Shipment
        - LS_eConnect_DF_ShowToSync_ShipToPartyMaster
        - LS_eConnect_DF_Sync_BODs 

![data_flow_packages.png](../../../../ecommerce/images/one_day_deployment/data_flow_packages.png)


## 2. Upload Connection Points, Data Flows, Workflows:

- Upload ION components are used to import the Connection Points, and Data Flows to ION from the admin portal.
- Navigate to Leanswift -> eConnect-base -> Upload ION components.

**Prerequisites**: 
- The handy file format must be in zip or JSON file only.  
- Initially Proxy URL, ION connect /Process model URL, Encoded service account (to update in cp_service_account), and Encoded Service Account (to update in wf_service_account) values will be "Empty". These values should be updated in the config.csv file from the backend before installation.

![upload_ion_components.png](../../../../ecommerce/images/one_day_deployment/upload_ion_components.png)


### Connection Point

- Navigate to Leanswift -> eConnect base -> Upload ION Components -> Upload Connection Point, DataFlow and WorkFlow -> Upload ION Connection Point.

![upload_ion_connection_point.png](../../../../ecommerce/images/one_day_deployment/upload_ion_connection_point.png)



### Data Flows

- Navigate to Leanswift -> Econnect base -> Upload ION Components -> Upload connection point, data flow and workflow -> Upload ION Data Flow.

![Upload ION Components Data Flows](../../../../ecommerce/images/one_day_deployment/upload_ion_data_flow.png)


## ION Component Upload History

- To verify the upload history of ION components, navigate to Leanswift ->eConnect Base -> ION Component Upload History.   
- If the Job ID is 201 means the connection is successfully done.
- If the Job ID is 500 means Server Error 
- If the Job ID is 403 means No Authorization.

![upload_ion_history.png](../../../../ecommerce/images/one_day_deployment/upload_ion_history.png)


<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>
