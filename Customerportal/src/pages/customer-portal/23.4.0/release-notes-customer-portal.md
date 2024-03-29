![Customer portal banner](/Customerportal/src/images/customer-portal/front-end-user/CP_banner.jpg)

# **LeanSwift Customer Portal**

# **23.4.0**

## **Release Notes**

**Table of Contents**

  - [**Overview**](#overview)
  - [**Environment Details**](#environment-details)
  - [**Standard Features**](#standard-features)
  - [**Highlights**](#highlights)
  - [**Enhancements**](#enhancements)
  - [**Pre-Requisites**](#pre-requisites)
  - [**Bug Fixes**](#bug-fixes)
  - [**Limitations**](#limitations)
  - [**Validated Versions**](#validated-versions)
  - [**Point of Contact**](#point-of-contact)


## **Overview**

**LeanSwift Customer Portal** is a customer self-service web portal that enables users to get instance access to information about their orders, invoices, and payments. With additional add-ons, users can also make e-payments directly via the portal. It is seamlessly integrated with Infor M3 Cloud Suite using ION. Customer Portal offers a single point of access to structured information about customer transactions and self-service functionality such as pay invoices, user management and much more.



## **Environment Details**

| **Software Name**  |  **Version**  |
| --- | --- |
| Magento Open Source | 2.4.6 |
| LeanSwift eConnect Base | 6.3.0 |
| LeanSwift M3 Login | 23.4.0 |
| LeanSwift Customer Portal | 23.4.0 |
| LeanSwift Payment Portal | 23.4.0 |
| LeanSwift IDM | 4.2.0 |
| RabbitMQ | 3.8.3 |
| ION Desk (CloudSuite) | 12.0.0  |
| Infor M3 (CloudSuite) | 16.1   |
| ION Package Version  |1.0.0  |



## **Standard Features**

**Account**

- Registration and Login of External User  
- Import and Login of Internal User  
- View User Account Information  
- Customer Selection by logged in user  
- Switch Customer Account

**Orders**

- View Order History
- Synchronization of Order Status in real-time
- Search by Order#, Order Date
- Filter by Order Status
- Sort by Order Date

**Invoices**

- View Invoice History
- Synchronization of Invoice Status in real-time
- Search by Invoice#, Invoice Date
- Filter by Invoice Status
- Sort by Invoice Date
  
**Payments**

- Pay Invoices by CC
- Pay Invoices by Credit Memos
- Pay on Account by CC
- Support for both Full & Partial Payments
- Synchronization of Payment Status in real-time
  
**Admin**

- Settings and Configuration for Portal and M3 Connectivity
- M3 User Roles Configuration, User Permissions and sub-account management

## **Highlights**

### **PWA Storefront Implementation:**

- We have introduced a Progressive Web App (PWA) storefront by extending the Venia theme. This upgrade offers users a more responsive, faster, and app-like experience, ensuring seamless navigation and improved performance.

### **GraphQL Implementation:**

- Implemented GraphQL for each module, including orders, invoices, payments, and Account Information. This change enhances data fetching efficiency and provides a more flexible and streamlined experience for users.

### **Enhanced Filters:**

- We have improved the filtering capabilities for orders, invoices, and payments. The enhanced filters offer users a more intuitive and efficient way to manage and navigate through their data.

### **Lazyload Pagination:**

- To optimize the user experience, lazyload pagination has been implemented in the order, invoice, and payment sections. This ensures faster loading times and a smoother browsing experience for users with large datasets.

### **Credit Calculation Display:**

- Users can now view credit calculations conveniently at the top of the payment screen. This feature provides instant insights into their credit status during the payment process.

### **Mobile Compatibility (Responsiveness):**

- The PWA storefront is now fully compatible with all mobile devices, ensuring a responsive design that adapts to various screen sizes. Users can enjoy a consistent and user-friendly experience across different devices.

### **New Layout Implementation:**

- We've introduced a new layout to enhance the overall UI experience. The new design focuses on improved aesthetics and usability, providing a more visually appealing and intuitive interface.

### **Performance Enhancement:**

- The release includes optimizations to enhance speed, particularly within the JavaScript framework. This results in a faster and more responsive application, improving overall user satisfaction.


## **Enhancements**

- Upgraded IDM add-on to be compatible with eConnect-base version 6.3.0.

- Magento version upgraded to 2.4.6. 

-  PHP version upgraded to 8.1.25. 

- Removed SwissUp theme and created LeanSwift Portal Theme.

- Search fields added for Payments page.

- Modified CustomerPortal and PaymentPortal to fit Magento Standards.


## **Pre-Requisites**

- Internal users should be active users on Mingle / Infor OS in order to be able to log into and use the portal.

- Internal users should have at least one valid user role assigned in ‘m3 user roles’ configuration to login.

- Internal users should have permissions granted in both ‘m3 user roles’ section and the customer panel.

- CyberSource is the default payment gateway. Hence a CyberSource account is required for taking payments from the portal. If any other payment gateway is required to be supported, that can be done only by additional, customized development and is not available out-of-the-box.

## **Bug Fixes**

- Documents uploaded for Short Pay Invoices is not available in M3 Program ARS200 is resolved.

- Business context is added for the delivery note document type in IDM.

- Customer name search on Upper Cases is now working in  home page.

- Fixed Internal M3 Login authentication Issue.


## **Limitations**


- Multiple currency support is not supported at the customer level.

- When importing customer data (update multiple customer information via csv), fields like view sections, ‘is admin’ and ‘make payments’ are mandatory and cannot be empty.

- Only Payments by Credit Card are supported via the portal in this version.
	
- Customers will not be able to edit payment and billing information on CyberSource payment pages.

- Import Order History data is limited to 10,000 records per M3 customer number.

- Clears the downloaded files from IDM and Cron/Real time configurations in IDM upload and download is not supported.

- Please note that the Cybersource Payment Gateway is not fully supported in this release. We apologize for any inconvenience caused and are actively working on addressing this limitation in future updates.


## **Validated Browser Version**

Chrome version 120.0.6099.71


## **Point of Contact**


[prabhu.manoharan3@wipro.com ](mailto:prabhu.manoharan3@wipro.com )

[deepthi.tadikamalla@wipro.com ](mailto:deepthi.tadikamalla@wipro.com )

[saurabh.gupta77@wipro.com](mailto:saurabh.gupta77@wipro.com)

[shoubhik.ghosh@wipro.com](mailto:shoubhik.ghosh@wipro.com)

[kalaivani.nagarajan1@wipro.com](mailto:kalaivani.nagarajan1@wipro.com)

[narayanan.gurusamy@wipro.com](mailto:narayanan.gurusamy@wipro.com )
