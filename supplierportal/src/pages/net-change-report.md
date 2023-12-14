![Supplier portal banner](../../../images/banner-supplier-portal.jpg)

# Supplier Portal-Net Change Report

# Table of contents

  - [23.4.0_PWA](#2340_pwa)
    - [**Enhancements**](#enhancements)
  - [23.3.0](#2330)
    - [Enhancements](#enhancements)
  - [22.4.0](#2240)
    - [Features](#features)
    - [Enhancements](#enhancements)
  - [22.1.0](#2210)
    - [Features](#features)
    - [Enhancements](#enhancements)
    - [Fixes](#fixes)
  - [21.1.0](#2110)
    - [Features :](#features-)
  - [20.2.0](#2020)
    - [Features :](#features-)
    - [Enhancements :](#enhancements-)
  - [20.1.2](#2012)
    - [Fixes:](#fixes)
  - [20.1.1](#2011)
    - [Enhancement:](#enhancement)
    - [Fixes:](#fixes)
  - [20.1.0](#2010)
    - [Features:](#features)

## 23.4.0_PWA

### **Enhancements**

- Buyer can send invite to supplier directly via his Magento user login.
- Buyer will receive the Onboarding approval task notification in M3.
- Notification from Infor is sent to the Buyer's email when document uploaded by supplier reaches IDM.
- The Final onboarding Approval task is sent to the respective final approvers configured in Distribution list. After buyer approve all his tasks.
- Portal login lands on Dashboard which gives metrics of Purchase orders, invoices and deliveries.
- Supplier Item Number is now displayed in purchase order lines.
- Reconfirm All is not allowed for confirmed status of PO.
- Removed Confirm All, Advise All and Notify All button and replaced with PO# check box (which will display All lines or selected line based on selection of PO lines) under advise and notify buttons.
- The total number of purchase orders and the total number of CONFIRMED, COMPLETE, NOTIFIED/ IN TRANSIT status POs (Purchase Order) are now displayed on My Purchase Orders page.
- A graph plotted for the total number of planned orders against the requested month is displayed on My Forecasts page.
- The total number of FULLY MATCHED and PARTIALLY MATCHED status are now displayed on My Deliveries.
- The 'Create New' button is added, and 'View Item' Icon is removed from the My Items page.
- The 'Refresh' button is added for My Forecasts, My Deliveries, My Invoices and My Items.
- Password set email is sent to the Subaccount user, once main supplier creates sub account user to the portal.
- Each Notification is displayed with header.


## 23.3.0

### Enhancements 

- Existing Supplier Items from M3 is imported using cron to Database during Supplier Registration.
- Provided backend configuration for Supplier Onboarding My Information form submission message.
- TAX ID field characters can be configured from Magento Admin.
- Confirmation email will be sent to Supplier once onboarded to portal.

## 22.4.0

### Features

- **Supplier Item Management**  

  This will be an Add-on to Supplier Portal. With this Supplier can create a new supplier item OR M3 Item /Update item/Connect supplier item to existing M3 item.
  M3 Buyer makes a decision to approve or reject the above requests from the supplier based on the real time data provided by him. 

### Enhancements

- Provided backend configuration to choose Payment Terms for Onboarding Supplier.
- Added Supplier Number Length configuration at backend for Onboarding Supplier. 
- Address 2 and References fields are optional in My Information form for onboarding supplier.
- Phone Number field accepts maximum of 16 characters with special characters in My Information form.
- TAX ID field accepts maximum of 15 characters with special characters in My Information form. This value is updated in TINO attribute in M3. 
- ‘How it works’ link is displayed when My Information is submitted. Link provides steps to complete onboarding supplier process. 
- Deliveries are now exported with line level information. 
- Password rules and validation is added in Create an Account page. 
- Supplier Name can be configured with permission at backend to allow Upper Case and Special Character. 
- Packaging Terms, Delivery Method, Cash Discount Terms, Monitoring Class, Payment Terms are added to My Information form. These fields are configurable and fetched     from M3 for onboarding supplier. 
- Freight Terms, Delivery Terms, Packaging Terms, Delivery Method, Cash Discount Terms, Monitoring Class and Payment Terms fields are language specific in My -           Information form. 
- Approval for Confirm Purchase Order is sent to Buyer assoicated with Purchase Order in PPS200. 

## 22.1.0

### Features

- **Supplier Onboarding**
  
    Supplier portal onboarding allows supplier creation from portal itself. New supplier account is created using the invite sent by admin to     his email account.
    
### Enhancements
  
 -  Supplier Portal supports MultiWebsite Scope

### Fixes

- Duplicate Mail and BOD validation issue are resolved when Supplier Registration Request is Approved or Rejected
- Global Notify Dialog Box Button issue is fixed.
- Terms and Conditions/ Privacy Policy link issue is fixed when supplier is logged in.
- Download as CSV file issue for Purchase Orders and Forecast orders is resolved.
- Email and Consolidated Notification issues for new and updated Purchase orders/Forecasts are fixed.
- IDM Download functionality issue is resolved for My Purchase Orders and My Documents.
- Process indicator for Multiple Confirm/Advise/Notify PO’s has been fixed.
- Notify PO By Delivery Note issue is resolved.
- Added validation When PO with Zero quantity is Confirmed, Advised and Notified.
- Address and Buyer Info sync with new supplier registration is fixed.
- Advise and Notify Information retrieval from M3 is fixed.
- Added validation when confirmed PO is reconfirmed without changes.
- Resolved status update on PO when Confirm PO request is rejected from M3.
- Decimal value validation is added for Purchase order price.
- Supplier Address update from M3 issue is resolved.
- Added fix for Supplier portal upgrade issue on loading existing data
- My Deliveries Search Filter issue is fixed.
- Performance Metrics Page report generation issue is resolved.
- Bell Notification now displays characters close to 5000.
- Added code fix to fetch Invoice based on company configured.
- Forecast order data retrieval issues is resolved.
- Added case sensitive validation for Supplier Number field in Registration.
- Confirm, Advise and Notify Multiple PO via Cron issue is fixed.
- My Invoice data retrieval from M3 issue is fixed.
- Advise and Notify PO line processing update issue fixed.
- Data Validation added for Advise and Notify Cron for existing Purchase orders.
- Fixed cron issue in IDM module.
- Bell Notification is now mapped correctly to Main and Subaccount users.
- Updated Bell Notification’s refresh rate.
- Data retrieval issue for supplier information and Purchase order is fixed.
- Email Theme issue is fixed.
- Global Advise and Notify settings now works as per configuration.
- Data Validation is added for Confirm PO with changes.
- Invoice Cron issue is fixed.
- Show Document Upload option issue in admin configuration is fixed.
- Show Notification issue in admin configuration is fixed.
- Date Format issue in My Settings page is resolved.
- Issues on running Forecast cron are fixed.
- Cron expression path for delivery and invoices is fixed.
  
## 21.1.0

### Features :

- **LeanSwift AMQP Connection**
  - New AMQP connection to handle the eConnect related BODs in RabbitMQ.
  - Provided the option in the Backend for the same to give the RabbitMQ credentials.
- **Enterprise Connector Removal**
  -No more Enterprise Connector. All the eConnect BODs from ION will now contact eConnect REST API directly instead of sending to rabbitmq.

## 20.2.0

### Features : 

- Advise / Advise All 
- Notify / Notify All
- Notify by Delivery Number
- Confirm, Advise and Notify multiple PO
- IDM upload for suppliers
- My Deliveries
- User Management 
- Bell Notification
- Email Notifications
- My Invoices
- User Tracking
- Refresh button on ‘My Purchase Orders’ page 

### Enhancements : 

- Forecast: 
  My Forecast will display only the Planned purchase orders that don't have status as Auto-Error 00 or Auto- Warning 05. Also, the Status column is removed from display.
- Confirm PO:
  Confirmed Purchase order line can be re-confirmed by modifying confirmed quantity or confirmed date any number of times as long as the status is 35 
- My Documents
  The Purchase order  Upload column is now modified as My Documents and supports both upload and download of documents. This makes it possible to fetch the document uploaded in   m3 for the particular PO using refresh icon.
  

## 20.1.2

### Fixes:

- When the Supplier email is not a valid hostname or when the Email is already registered, page redirects to LUMA theme. This is modified to retain the supplier portal theme.
- Company (CONO) is sent as parameter in ION Buyer approval request so that approval will be sent to the buyer (M3 user )irrespective of default company of the M3 user.

## 20.1.1

### Enhancement:

- Forecast to pull orders whose status is less than 60 during first time login and subsequent changes are pulled based on last modified date field

### Fixes:

- Theme based pages will be displayed during Registration and Forgot password
- On-time Delivery metrics to display correct data for monthly chart
- Document upload done in frontend will now be mapped against the registered Supplier PO in IDM
- Names of message queue which are used for supplier portal are modified


## 20.1.0

### Features:

LeanSwift Supplier Portal for Infor M3 CloudSuite is a supplier self-service portal that enables efficient online communication with vendors. It is seamlessly integrated with Infor M3 Cloudsuite via ION. Supplier Portal helps automate the entire purchase-to-pay process for the customer.

Account

- Registration and Login
- View Supplier Information
- User Date Format Setting

Purchase Orders

- View Purchase Orders
- Search/Filter/Sort on Purchase Orders
- Confirm Purchase Orders
- Download Purchase Orders Information
- Upload documents into IDM against Purchase Orders

Purchase Proposals/Forecasts

- View Purchase Forecasts
- Search/Filter/Sort on Purchase Forecasts

Performance Metrics

- View Quality metrics based on rejected quantity
- View Delivery Performance metrics
- View Purchase Price Variance metrics


