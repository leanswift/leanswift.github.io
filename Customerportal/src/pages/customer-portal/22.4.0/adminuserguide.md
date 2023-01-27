![](RackMultipart20230127-1-vnvvxy_html_8e85754fa92f0167.jpg)

# **Version 22.4.0- User Manual - Customer Portal - Admin User**

# **Table of contents**

- [Overview](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#Overview)
  - [Architecture](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#Architecture)
  - [Features](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#Features)
  - [Point Of Contact](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#Point-Of-Contact)
- [User Manual for Customer Portal - Admin User](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#User-Manual-for-Customer-Portal-Admin-User)
  - [Login](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#Login)
  - [Configuration](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#Configuration)
    - [General](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#General)
    - [Customer Add/Sync Configuration](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#Customer-Add/Sync-Configuration)
    - [Cron](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#Cron)
  - [M3 User Roles](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#M3-User-Roles)
    - [Add New Role](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#Add-New-Role)
      - [Edit Role](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#Edit-Role)
      - [Delete Role](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#Delete-Role)
      - [Search/Filter](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#Search/Filter)
      - [Visible Columns](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#Visible-Columns)
      - [Pagination](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#Pagination)
  - [Sub Account User Management](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#Sub-Account-User-Management)
    - [Export](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#Export)
    - [Import](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#Import)
    - [Import Settings](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#Import-Settings)
    - [Import Behaviour](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#Import-Behaviour)
    - [File to Import](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#File-to-Import)
    - [Check Data](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#Check-Data)
  - [Customer User Permissions](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#Customer-User-Permissions)
  - [Upload supporting document on Short Pay invoices](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#upload-supporting-document-on-short-pay-invoices)
  - [Email IDM documents](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#email-idm-documents)

# **User Manual – Customer Portal Admin User**

# **Overview**

LeanSwift Customer Portal is a customer self-service web portal that enables users to get instance access to information about their orders, invoices and payments. With additional add-ons, uses can also make e-payments directly via the portal. It is seamlessly integrated with Infor M3 CloudSuite using ION. Customer Portal offers a single point of access to structured information about customer transactions and self-service functionality such as pay invoices, user management and much more.

# **Architecture**

![](RackMultipart20230127-1-vnvvxy_html_47799d23ad036281.jpg)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#toc)

**Features**

Account

- Registration and Login of External User
- Import and Login of Internal User
- View User Account Information
- Customer Selection by logged in user
- Switch Customer Account

Orders

- View Order History
- Synchronization of Order Status in real-time
- Search by Order#, Order Date
- Filter by Order Status
- Sort by Order Date

Invoices

- View Invoice History
- Synchronization of Invoice Status in real-time
- Search by Invoice#, Invoice Date
- Filter by Invoice Status
- Sort by Invoice Date

Payments

- Pay Invoices by CC
- Pay Invoices by Credit Memos
- Pay on Account by CC
- Support for both Full & Partial Payments
- Synchronization of Payment Status in real-time

Admin

- Settings and Configuration for Portal and M3 Connectivity
- M3 User Roles Configuration, User Permissions and sub-account management

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#toc)

**Point Of Contact**

This document and the software it describes are provided by LeanSwift Solutions Inc. For additional information regarding support, licensing, functionality etc. please contact LeanSwift Solutions Inc. via contact form at http://www.leanswift.com or email info@leanswift.com.

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#toc)

# **User Guide for Customer Portal Admin**

**Login**

Logging to Customer Portal Configuration:

- Login using Magento admin credentials.
- Go to LeanSwift tab (from left panel) - Customer Portal - Settings.

![](RackMultipart20230127-1-vnvvxy_html_3d539a363766d01c.png)

![](RackMultipart20230127-1-vnvvxy_html_5a8465311770a2bd.jpg)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#toc)

**Configuration**

- The Configuration module allows the administrator to configure Settings of Customer Portal.
- Administrator can view, add and edit configurations.
- Go to LeanSwift – Customer Portal – Configuration.
- Save the configuration by clicking the Save Config button.

![](RackMultipart20230127-1-vnvvxy_html_c2df2f6742ef449d.jpg)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#toc)

**General**

- General configurations section allows the admin to configure general settings of Customer Portal such as Customer Selection, Internal User allowed Sections, Restricted Customer groups, CRON configurations of Order and Invoice.

![](RackMultipart20230127-1-vnvvxy_html_986248a31abb4339.jpg)

- Customer Selection
  - Customer Selection Configuration of General section allows admin to select the type of customer to be listed after logging to Customer Portal.
  - Specify Customer Selection, Payer or Customer.
  - If customer type is selected as Customer, all customers associated with the user are listed in the Customer Portal home page.
  - If customer type is selected as Payer, customers who are payers are listed for the logged in user.

![](RackMultipart20230127-1-vnvvxy_html_fc42dc68f8660229.png)

![](RackMultipart20230127-1-vnvvxy_html_63671540202be03e.png)

- Internal User Allowed Section
  - Admin users can configure the Internal User Allowed Section, to limit/add sections allowed for Internal User, add or delete the section.
  - The main menus and their related Section names are listed in the table below.

| **Main Menus** | **Section Name** |
| --- | --- |
| Accounts | \<p\>Account Summary\</p\>\<p\>- Addresses\</p\> |
| --- | --- |
| Order History | View Order History |
| Invoice History | View Invoice History |
| Payments | \<p\>View Pay Invoices\</p\>\<p\>- View Pay in Account\</p\>\<p\>- Process Pay invoices\</p\>\<p\>Process Pay on Account\</p\> |

![](RackMultipart20230127-1-vnvvxy_html_1200390260546309.jpg)

- To add or delete the internal user allowed section click on Add or delete button.

![](RackMultipart20230127-1-vnvvxy_html_bd9d70a95f48ca9b.jpg)

- Restrict Customer Group
  - To restrict access to Customer Portal based on M3 Customer group, Admin user can configure Restrict Customer Group - Specify customer groups as per M3 system.
  - If a user's customer group is restricted, external customers with valid credentials will be unable to register or access the Customer portal.
  - To restrict multiple customer groups, specify the customer groups as Comma separated. E.g. Y10, Y20.

![](RackMultipart20230127-1-vnvvxy_html_29a17489075e5d21.jpg)

- Order History CRON
  - To import Order history via Cron, configure Order History CRON – Select Yes.
  - When the Order History CRON setting is set to NO, the user is not allowed to run the Order History CRON job.
- From Date to Fetch Orders
  - To set the from date to fetch Order history, configure From Date to Fetch Orders – Specify the date.
  - Enabling Use System Value sets the from date to fetch orders to 180 days behind the current date as the default value.

![](RackMultipart20230127-1-vnvvxy_html_148c0c4078e2aa14.png)

- Invoice History CRON
  - To import Order history via Cron, configure Invoice History CRON – Select Yes.
  - When the Invoice History CRON setting is set to NO, the user is not allowed to run the Invoice History CRON job.
- From Date to Fetch Invoices
  - To set the from date to fetch Order history, configure From Date to Fetch Invoices – Specify the date.
  - Enabling Use System Value, sets the from date to fetch Invoices as default value, 180 days behind the current date.
- Invoice/Order History Max Records
  - To limit the maximum number of records retrieved while executing Invoice/Order History CRON, configure Invoice/Order History Max Records – Specify the number of records.
  - Enabling Use System value sets the maximum invoice/order records to default value, 10000.

![](RackMultipart20230127-1-vnvvxy_html_bfac780909715ad0.png)

**Customer Add/Sync Configuration**

Customer Add/Sync Configurations section allows admin to configure customer add/sync settings such as Add/Sync Customers, Add/Sync Customers with STAT Id, Free Field filters, Additional filters and the last updated timestamp.

- Enable Add/Sync Customer
  - To allow import of data through CRON and Sync from M3 to Portal Database, configure Enable Add/Sync Customer – Select Yes.
  - Configuring Enable Add/Sync Customer setting to No, restricts the user from importing data via CRON and Sync from M3 to Portal Database.
- Add Sync Customer with STAT ID
  - After the Add/Sync Customer option is enabled, in order to restrict Sync Customer feature only for customers with STATID, configure Add Sync Customer with STAT ID – Select Yes.
  - Configuring Add Sync Customer with STAT ID to No, allows Sync Customer feature for both Customers with STAT ID and Customers without STAT ID.

![](RackMultipart20230127-1-vnvvxy_html_f6a5a85f0bad1503.jpg)

- Free Field Filter
  - To filter customers based on free field value from OCUSMA in M3 system, configure Free Field Filter – Specify the filter with free field values. Ex: CFC5=1 or CFC=5

![](RackMultipart20230127-1-vnvvxy_html_97de6fe0ed54a12.jpg)

![](RackMultipart20230127-1-vnvvxy_html_7d47a863ae0f70c3.jpg)

![](RackMultipart20230127-1-vnvvxy_html_d1a4371cde34b9b2.png)

- Additional Filter(s)
  - To add additional filters to filter customers, configure Additional Filter(s) – Add conditions. Ex: OKSTAT = 20 AND OKWHLO = 001.
  - Additional filters are applied to CRON jobs executed.
- Time Stamp
  - To configure the last updated time stamp – configure Time Stamp – Mention the timestamp.
  - The time stamp configuration is updated after every CRON import with its successful execution timestamp.

![](RackMultipart20230127-1-vnvvxy_html_1e9f6e05da961000.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#toc)

**Cron**

- To configure CRON job details of Customer portal as admin, go to LeanSwift –\> Customer Portal –\>Settings –\> General –\> CRON.
- To disable the CRON job, the configuration for CRON shall be empty.
- The CRON job details can be configured for:
  - Import Customer
  - Import Order History
  - Import Invoice History
- After Initial import, cron job run based on the last updated timestamp for regular sync.

For detailed understanding of CRON configurations refer to cron [- Wikipedia](https://en.wikipedia.org/wiki/Cron#Predefined_scheduling_definitions).

┌─────────────minute (0 - 59)

│┌─────────────hour (0 - 23)

││┌─────────────day of the month (1 - 31)

│││┌─────────────month (1 - 12)

││││┌─────────────day of the week (0 - 6) (Sunday to Saturday).

│││││7 is also Sunday on some systems)

│││││

│││││

\* \* \* \* \*

| **Field** | **Required** | **Allowed values** | **Allowed special characters** |
| --- | --- | --- | --- |
| Minutes | Yes | 0–59 | \* , - |
| --- | --- | --- | --- |
| Hours | Yes | 0–23 | \* , - |
| Day of month | Yes | 1–31 | \* , - ? L W |
| Month | Yes | 1–12 or JAN–DEC | \* , - |
| Day of week | Yes | 0–6 or SUN–SAT | \* , - ? L # |
| Year | No | 1970–2099 | \* , - |

![](RackMultipart20230127-1-vnvvxy_html_2e54c7e40d836549.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#toc)

**M3 User Roles**

- To access Customer Portal M3 User Roles, Admin user can login to the Magento system with credentials, go to LeanSwift-\> Customer Portal -\> M3 User Roles.

![](RackMultipart20230127-1-vnvvxy_html_83e148683461748c.jpg)

- Admin user can view the list of M3 User Roles, add new roles, edit roles and delete roles.

![](RackMultipart20230127-1-vnvvxy_html_fa8d12effd25fa21.png)

- To know the User Roles available in M3, Open program MNS410. This gives you list of user roles for M3 user.

![](RackMultipart20230127-1-vnvvxy_html_74a2b966f30401c.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#toc)

**Add New Role**

- The Admin user can click the Add New Role button to create a new role.
- By adding a new role, Admin users can configure permissions to perform processes such as payments and modules to be displayed for the M3 User role.

![](RackMultipart20230127-1-vnvvxy_html_af6e1f9f0cbd04bd.jpg)

- Select the M3 user role, the processes that should be authorised, and the modules that should be displayed.
- Click on Save button to add a new Role.
- Incorrect configuration of user roles will lead to authorization failure while logging.

Note: To deselect an option, hold down the Ctrl key while selecting it.

![](RackMultipart20230127-1-vnvvxy_html_aa96ad7905ced66b.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#toc)

**Edit Role**

- To edit M3 User Roles, click on the edit option next to M3 user roles.
- Modify the permissions and Click on Save.

![](RackMultipart20230127-1-vnvvxy_html_a0a4d210300c738a.jpg)

![](RackMultipart20230127-1-vnvvxy_html_ecac8e92b10c664e.jpg)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#toc)

**Delete Role**

- To delete an existing M3 User Role, admin user can Click on delete option next to the user role displayed.

![](RackMultipart20230127-1-vnvvxy_html_e772bffea9a8a539.jpg)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#toc)

**Search/Filter**

- The Search by Keyword option allows admin to search for M3 User Roles using a keyword.
- Filter option helps to filter the M3 user roles based on M3 Role, Process, Display, No Access.
- Specify the fields to be filtered and apply filters.

![](RackMultipart20230127-1-vnvvxy_html_b50ffe1dc4431b6b.jpg)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#toc)

**Visible Columns**

- Click on columns and select the columns to be displayed to configure the viewable columns on the M3 User Roles screen.

![](RackMultipart20230127-1-vnvvxy_html_795ecf301535ac63.jpg)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#toc)

**Pagination**

- The pagination menu can be used to change the number of records displayed each page.
- Custom option allows admin to enter the number manually.
- 999 records is the maximum number of records per page.

![](RackMultipart20230127-1-vnvvxy_html_436fb39b7580e55e.jpg)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#toc)

**Sub Account User Management**

**Export**

- To export Customers' Main File, go to Settings –\>Data Transfer –\> Export.

![](RackMultipart20230127-1-vnvvxy_html_9b78bb13ea8a84c3.jpg)

- Select the entity type from export settings, as Customers Main File.
- Currently Supported export file format is CSV.
- Fields enclosure.

![](RackMultipart20230127-1-vnvvxy_html_3608497889585c98.jpg)

- Admin can search the entity attributes and apply attribute-level exclude filters.

![](RackMultipart20230127-1-vnvvxy_html_6d873acf0c62a107.png)

- Click on continue button, to export customers main file with search and exclude filter conditions applied.
- The admin can use the Reset filter option to return to the default filter configurations.
- Export requests will be added to the message queue if the export file Cron job is active.

"_Message is added to queue, wait to get your file soon. Make sure your Cron job is running to export the file."_

![](RackMultipart20230127-1-vnvvxy_html_75edb89a69b84ac9.jpg)

- Admin can download or delete the exported file from the action menu.

![](RackMultipart20230127-1-vnvvxy_html_c8ab9f740230d942.jpg)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#toc)

**Import**

- To import the Customer's Main file, Customer portal Admin user can go to Settings –\> Data Transfer –\> Import.
- Update Fields:
  - IsAdmin - Specifying yes to IsAdmin provides admin privilege to user.
  - Make Payment - Specifying yes to make payment provides payment privilege to user.
  - View Sections - Specify the sections with view permission for users.
  - Assigned customers field - Verify the list of customers, add or delete to limit access for users.

![](RackMultipart20230127-1-vnvvxy_html_1c2a5c7d33389353.jpg)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#toc)

**Import Settings**

- The maximum size of the import file for Customers Main File is 1536MB.
- Select the Entity type as Customers Main File.

![](RackMultipart20230127-1-vnvvxy_html_b9c4cc6e5ed1be32.png)

- Admin can download Sample file to understand the expected file format and field values.
- Is Admin, Make Payment and Allow Section are all mandatory and not null fields.

![](RackMultipart20230127-1-vnvvxy_html_e6e56b2a6601393a.jpg)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#toc)

**Import Behaviour**

- Choose the expected Import behaviour
  - Add/Update Complex Data - Modify the exported file and click on add/update complex data, upload the modified file.
  - Delete entities.
  - Custom Action.
- Choose the Validation Strategy for the system when error occurs during import.
  - Stop on Error – Configuring Stop On error instructs the system to not proceed when an error occurs during import.
  - Skip Error entities – Configuring Skip Error entities instructs the system to skip those entities with error and complete import action.
- Allowed Error count
  - The maximum number of errors accepted while importing.
  - In case there are more errors than allowed error count, the system shall stop the import process.
- Field separator – Specify the separator as used in the import file.
- Multiple value separator – Specify the separator when there are multiple values in one field value.
- Empty attribute value constant.

![](RackMultipart20230127-1-vnvvxy_html_b3dfa0f85c4d5ce9.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#toc)

**File to Import**

- Select File to Import: Choose the file to be imported, file must be of UTF-8 encoding for proper import.

![](RackMultipart20230127-1-vnvvxy_html_ee7c7de691dbde77.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#toc)

**Check Data**

- Once Import settings, Import behaviour and Files to import are provided, admin can check data in import file, by clicking on Check Data button.
- System validates the import file and displays Validation results.
- Error messages displayed helps admin to understand the issues with the import file.
  - Eg: Data validation failed, please check the below errors and upload the file.

![](RackMultipart20230127-1-vnvvxy_html_dc499ed3662a44b2.jpg)

![](RackMultipart20230127-1-vnvvxy_html_9fa64b01eafbe651.jpg)

- When the import file is valid, the data is validated and the choice to import is provided in the validation results section.
- Click on the Import button.

![](RackMultipart20230127-1-vnvvxy_html_cd75237f7e6dfb03.jpg)

- Confirmation on import status is displayed with information on the number of records created, updated or deleted.

![](RackMultipart20230127-1-vnvvxy_html_2f5037b3a98c54d9.jpg)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#toc)

**Customer User Permissions**

- Users must have roles assigned to them in Magento, and they can only log in to the frontend based on the rights they have been allowed.
- **Default permission for External User**

![](RackMultipart20230127-1-vnvvxy_html_b0f0106d1a20eaf7.png)

- **Internal User Permission**

![](RackMultipart20230127-1-vnvvxy_html_800141207b929e12.png)

- **STAT Admin Permission**

![](RackMultipart20230127-1-vnvvxy_html_85a68ad1c5212399.png)

- **STAT Sub Account Permission**

![](RackMultipart20230127-1-vnvvxy_html_1ce3423782f98fb9.png)

- M3 USER Role
  - Internal User permissions are leveraged at M3 user Role configuration.
  - Customers of Magento have permissions by default.
  - Users should have access configured both in Customers Portal Settings and M3 user role settings.
- Configuration of Customer Logo
  - To configure the Logo of Customer Portal, go to Content -\> Design -\> Configuration -\> Header.
  - Click on the particular website which need to be edited.
  - Provide the Logo image, Alternate Logo Image and additional details like width height of the logo.

![](RackMultipart20230127-1-vnvvxy_html_13052769adc20a45.png)

- Configuration of Email Templates
  - To configure Email Templates, go to Stores –\> Configuration – \>Customers -\>Customer configuration.
  - Configure Default welcome email without password.

![](RackMultipart20230127-1-vnvvxy_html_a3034d549fab2962.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#toc)

**Upload supporting document on Short Pay invoices**

IDM module needs to be installed in magento to support document upload for short pay invoices. The Upload configuration in the IDM module needs to be enabled. User can mention the allowed file types that can be uploaded. Documents are uploaded when _paymentportal\_invoice\_payment\_sync_ is executed.

![](RackMultipart20230127-1-vnvvxy_html_d86e2fa2cdf02f6f.jpg)

![](RackMultipart20230127-1-vnvvxy_html_b146314e273dd0ca.png)

**Email IDM documents**

When Email IDM document is enabled, the option to select _Send Email from M3 IDM_ and _Email Documents Cron_ is displayed in admin.

- **Send Email from M3 IDM as Yes**

When _Send Email from M3 IDM_ is selected as Yes, /items/search API call is made to IDM to retrieve the Customer invoice or Order confirmation document. Along with it, /email API is called to directly send documents from M3 IDM based on when _Email Documents Cron_ is triggered. The documents are not saved in magento db.

![](RackMultipart20230127-1-vnvvxy_html_5c7376f331e0e895.png)

The Search configuration needs to be updated when this option is selected.

![](RackMultipart20230127-1-vnvvxy_html_ea64f0c2a7cd8128.png)

- **Send Email from M3 IDM as No**

When _Send Email from M3 IDM_ is selected as No, two additional configuration is enabled to configure the Email sender and Email template. When _Email Documents Cron_ is triggered the items/search API call is made to IDM to retrieve the Customer invoice or Order confirmation document. The document is stored in magento db, mail is sent to customer with the configured sender and email template based on when _Email Documents Cron_ is triggered.

![](RackMultipart20230127-1-vnvvxy_html_783b9256d41c8f73.png)

Download idm configuration needs to be updated when the Send Email from M3 IDM is set as No

![](RackMultipart20230127-1-vnvvxy_html_baf902a28e2c810e.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-admin-user.html#toc)

![Shape1](RackMultipart20230127-1-vnvvxy_html_8364f73a6574c228.gif)

Internal to Wipro
