

# Version 24.2.0 - User Manual- One-Day Deployment

<div id = "toc"></div>

# Table of contents

- [Introduction](#introduction)
- [Configuration Setup](#configuration-setup)
  - [Data Templates Packages](#data-templates-packages)
- [ION Authentication](#ion-authentication)
  - [Import History](#import-history)
- [Import IDM Configuration](#import-idm-configuration)
- [Import Supplier Portal Configuration](#import-supplier-portal-configuration)
- [Import Item Management configuration](#import-item-management-configuration)
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

# Introductio
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

<kbd>
<img alt="Data templates Packages" src="../../images/pwa/one_day_deployment/data_template_packages.png"> 
</kbd>
 

<kbd>
<img alt="Config.csv file" src="../../images/pwa/one_day_deployment/config.csv_file.png"> 
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>


# ION Authentication

- The ION API file will auto populate other API URL fields in the configuration.
- Navigate to Leanswift -> eConnect base -> Connectivity -> Authentication -> ION API Credentials file. 
- Once the ION API file is uploaded the below fields will get auto populated.

<kbd>
<img alt="ION Authentication file upload" src="../../images/pwa/one_day_deployment/ion_authentication_file_upload.png"> 
</kbd>


1. Store -> Configuration -> Leanswift -> Econnect Base -> service configuration -> API service url.

<kbd>
<img alt="ION Authentication URL Fields" src="../../images/pwa/one_day_deployment/ion_authentication_fields1.png"> 
</kbd>


2. Store -> Configuration -> Leanswift -> Econnect Base ->Authentication all field except M3 user.

<kbd>
<img alt="ION Authentication URL Fields" src="../../images/pwa/one_day_deployment/ion_authentication_fields2.png"> 
</kbd>


3. Store -> Configuration -> Leanswift -> Econnect Base ->ION Workflow Configuration -> API service Url.

<kbd>
<img alt="ION Authentication URL Fields" src="../../images/pwa/one_day_deployment/ion_authentication_fields3.png"> 
</kbd>


4. Store -> Configuration -> Supplier portal -> Settings -> Supplier onboarding -> ION ProcessUserService Url.

<kbd>
<img alt="ION Authentication URL Fields" src="../../images/pwa/one_day_deployment/ion_authentication_fields4.png"> 
</kbd>


5. Store -> Configuration -> LeanSwift -> Idm -> General Configuration -> ION Api service url.

<kbd>
<img alt="ION Authentication URL Fields" src="../../images/pwa/one_day_deployment/ion_authentication_fields5.png"> 
</kbd>


## Import History

Once the all the configuration is imported (Supplier Portal settings, Item Management, IDM Settings), history of import is recorded.

To verify the import history, navigate to Leanswift -> eConnect Base -> Import History. 

<kbd>
<img alt="Import History" src="../../images/pwa/one_day_deployment/import_history.png"> 
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>


# Import IDM Configuration

- For IDM configuration, navigate to Leanswift -> Supplier portal -> Settings.
- Expand the menu Leanswift -> Initial load / Import -> Default Config -> Import IDM Configuration -> IDM Initial Load/ Configure.

<kbd>
<img alt="IDM Import" src="../../images/pwa/one_day_deployment/idm_import.png"> 
</kbd>

- This will import/fetch Document Type and Attribute Type fields in the **Configurable Options to Upload** and **Configurable Options to Download** from IDM to configurations.

<kbd>
<img alt="IDM Upload" src="../../images/pwa/one_day_deployment/idm_upload.png"> 
</kbd>

<kbd>
<img alt="IDM Download" src="../../images/pwa/one_day_deployment/idm_download.png"> 
</kbd>

After import is clicked, import changes to “Reset” Button.

If there are any changes in Document Type and Attribute Type from IDM, click the “Reset” button, newly added or updated values will be retrieved from IDM.

<kbd>
<img alt="IDM Reset" src="../../images/pwa/one_day_deployment/idm_reset.png"> 
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>


# Import Supplier Portal Configuration

- Import Supplier Portal configuration is website specific.
- Navigate to Leanswift -> Supplier portal -> Settings.
- Expand the menu Leanswift -> Initial load / Import -> Main Website -> Import Supplier Portal configuratio ->Supplier Portal Initial Load/ Configure.

<kbd>
<img alt="Supplier portal Configuration Import" src="../../images/pwa/one_day_deployment/supplier_portal_comfiguration_import.png"> 
</kbd>

- When “Import” button is clicked it will fetch the M3 attributes values from Infor M3 and configure default values based on the values updated in “config.csv” file. M3 attribute fields are available in csv file.
- They list of M3 Attribute fields fetched from Infor M3 are:
	- Supplier Onboarding:
		- M3 Supplier template.
		- SP Prefix.
		- M3 Language list.
		- M3 Order Currency List.
		- M3 Payment Terms.
		- M3 Fright Terms.
		- M3 Delivery Terms list.
		- M3 Payment Method List.
		- M3 Packing Terms List.
		- M3 Monitoring Class List.
		- M3 Delivery Method List.
- By default, all other configuration values are updated in Supplier Portal settings. 


<kbd>
<img alt="Supplier portal import fields" src="../../images/pwa/one_day_deployment/supplier_portal_fields.png"> 
</kbd>

<kbd>
<img alt="Supplier portal import fields" src="../../images/pwa/one_day_deployment/supplier_portal_fields2.png"> 
</kbd>

After import is clicked, import changes to Reset Button. 

If there are any newly added M3 attributes, when the “Reset” button is clicked, the newly added values will be retrieved from Infor M3 and configure based on the values available in config.csv file.

<kbd>
<img alt="Supplier portal Reset" src="../../images/pwa/one_day_deployment/supplier_portal_comfiguration_reset.png"> 
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>


# Import Item Management configuration

- Import Item Management Configuration is website specific.
- Navigate to Leanswift -> Supplier portal -> Settings.
- Expand the menu Leanswift -> Initial load / Import -> Main Website -> Import Item Management configuration -> Item Management Initial Load/ Configure.


<kbd>
<img alt="Item Management Import" src="../../images/pwa/one_day_deployment/item_management_import.png"> 
</kbd>

- Item Type and Quality Class attribute values are fetched from Infor M3 and update based on the default values given in the config.csv file.
- Creation Responsible, Workflow Distribution Username need to have the user specified values. This can be updated directly in the config.csv file. 


<kbd>
<img alt="Item Management import fileds" src="../../images/pwa/one_day_deployment/item_management_imported_fields.png"> 
</kbd>

<kbd>
<img alt="Item Management import fileds" src="../../images/pwa/one_day_deployment/item_management_imported_fields2.png"> 
</kbd>

After import is clicked, import changes to Reset Button.

If there are any newly added values in Item type or quality class in Infor M3, then click the “Reset” button, new values will be retrieved from Infor M3 and configure according to config.csv file.

<kbd>
<img alt="Item Management Reset" src="../../images/pwa/one_day_deployment/item_management_reset.png"> 
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>


# Upload ION components

The ION components can be configured in two different ways:

## 1.Configuration Setup 

At the time of Supplier Portal installation, the Connection Point file (Json), Data Flows file(zip), Work Flows file(zip) should be given under "root_folder/template" in the server.

### Connection Point Packages

- Navigate to Leanswift -> eConnect-base -> Connectivity -> Configuration Setup -> Connection Point Packages.
- Once “Upload” is clicked, success message is displayed. The Connection Point can be verified in Infor under OS -> ION -> Connect -> Connection Point.

<kbd>
<img alt="M3 Connection point" src="../../images/pwa/one_day_deployment/m3_connection_point.png"> 
</kbd>

- In OS portal, initially the connection point will be “Inactive” state, once the data flows are uploaded then the connection point will become “Active”.
- List of connection point: 
	- Supplier_Portal_API_SPQA
- An error message” There's an issue with the input, or it already exists within Infor ION for ConnectionPoint.json Connection Point.” will be displayed if there is issue in the file uploaded.


<kbd>
<img alt="Connection Point Packages" src="../../images/pwa/one_day_deployment/connection_point_packages.png"> 
</kbd>


### Data Flow Packages

- Navigate to Leanswift -> eConnect-base -> Connectivity -> Configuration Setup -> Data Flow Packages.  
- Once “Upload” is clicked in Data Flow packages, the Data flows will automatically generate in Infor OS. 
- Once the file is uploaded, a success message is displayed. The activated data flow can be verified in M3 under ION Desk -> Connect -> Data flows.

<kbd>
<img alt="M3 Data Flows" src="../../images/pwa/one_day_deployment/m3_data_flows.png"> 
</kbd>

- List of data flows are: 
	- Supplier\_Portal\_M3\_Invoice\_Show\_Sync\_BOD
	- Supplier\_Portal\_M3\_PO\_Show\_Sync\_BOD
	- Supplier\_Portal\_M3\_Supplier\_Show\_Sync\_BOD
	- Supplier\_Portal\_M3\_Sync\_BOD

<kbd>
<img alt="Data Flow Packages" src="../../images/pwa/one_day_deployment/data_flow_packages.png"> 
</kbd>


### Work Flow Packages

- Navigate to Leanswift -> eConnect-base -> Connectivity -> Configuration Setup -> Work Flow Packages.  
- Once “Upload” is clicked in Work Flow packages the Work flows will automatically generate in Infor OS. 
- Once the file is uploaded, a success message is displayed, and work flow is activated in M3. The activated work flow can be verified in Infor under ION Desk -> Monitors & Workflows -> Workflows. 

<kbd>
<img alt="M3 Work Flow" src="../../images/pwa/one_day_deployment/m3_work_flows.png"> 
</kbd>

- List of Workflows are:
	- supplier_access_approval
	- supplier_onboarding_idm_notification
	- supplier_portal_item_creation
	- supplier_portal_onboard
	- supplier_portal_onboard_document
	- supplier_portal_supplier_connect_item
	- supplier_portal_supplier_connect_item_updation
	- confirm_po_approval

<kbd>
<img alt="Work Flow Packages" src="../../images/pwa/one_day_deployment/work_flow_packages.png"> 
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>


## 2.Upload Connection Points, Data Flows, Workflows:

- Upload ION components are used to import the Connection Points, Data Flows, Workflows to ION from admin portal.
- Navigate to Leanswift -> eConnect-base -> Upload ION components.

**Prerequisites**: 
- The handy file format must be in zip or json file only.  
- Initially Proxy URL, ION connect /Process model URL, Encoded service account (to update in cp_service_account), Encoded Service Account (to update in wf_service_account) values will be "Empty". These values should be updated in config.csv file from backend before installation.

<kbd>
<img alt="Upload ION Components" src="../../images/pwa/one_day_deployment/upload_ion_components.png"> 
</kbd>

### Connection Point

- Navigate to Leanswift -> eConnect base -> Upload ION Components -> Upload Connection Point, DataFlow and WorkFlow -> Upload ION Connection Point 

<kbd>
<img alt="Upload ION Components Connection point" src="../../images/pwa/one_day_deployment/upload_ion_connection_point.png"> 
</kbd>

### Data Flows

- Navigate to Leanswift -> Econnect base -> Upload ION Components -> Upload connection point, data flow and workflow -> Upload ION Data Flow

<kbd>
<img alt="Upload ION Components Data Flows" src="../../images/pwa/one_day_deployment/upload_ion_data_flow.png"> 
</kbd>

### Workflows

- Navigate to Leanswift -> Econnect base -> Upload ION Components -> Upload connection point, data flow and workflow -> Upload ION Work Flow.

<kbd>
<img alt="Upload ION Components Work Flow" src="../../images/pwa/one_day_deployment/upload_ion_work_flow.png"> 
</kbd>


## ION Component Upload History

- To verify the upload history of ION components, navigate to Leanswift ->eConnect Base -> ION Component Upload History.   
- If the Job ID is 201 means the connection is successfully done.
- If the Job ID is 400 means invalid input work flow, workflow already exists, or workflow name is missing, and it is displayed on the configuration page also.
- If the Job ID is 500 means Server Error 
- If the Job ID is 403 means No Authorization.

<kbd>
<img alt="ION Component Upload History" src="../../images/pwa/one_day_deployment/upload_ion_history.png"> 
</kbd>


<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>
