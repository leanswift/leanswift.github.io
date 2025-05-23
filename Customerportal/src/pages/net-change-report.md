![Customer portal banner](/Customerportal/src/images/customer-portal/front-end-user/CP_banner.jpg)

# Customer Portal-Net Change Report

## Table of contents

- [25.1.0](#2340)
    - [Features](#features)
    - [Enhancements](#enhancements)  
    - [Highlights](#highlights)
- [23.4.0](#2340)
    - [Features](#features)
    - [Highlights](#highlights)
    - [Enhancements](#enhancements)
    - [Bug Fixes](#bug-fixes)
 - [22.4.0](#2240)
    - [Features](#features)
    - [Bug Fixes](#bug-fixes)
    - [Enhancements](#enhancements)
- [21.1.0](#2110)
    - [Features](#features)
- [21.2.0](#2120)
    - [Features](#features)

## 25.1.0

## **Features**

**Account**

- Login of External User  
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

## **Enhancements**
- When installed with Econnect, customer registration is not required. Users can change their password using their Infor M3 email ID.
- If installed as a standalone, registration requires ERP number, order number, invoice number, and amount.
- With Econnect, the system will apply the Econnect registration restriction group, while in standalone, it will apply the Customer Portal restriction group.

## **Highlights**
- The Customer Portal modules now support installation with Econnect without the need to create multiple websites.
- The features of the Customer Portal modules will remain consistent whether using Econnect or as a standalone.
- Econnect customers can access all Customer Portal features.
- We have updated the m3 login authentication  process by replacing mingle url with ifs service url

## 23.4.0

### **Features**

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

### **Highlights**

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


### **Enhancements**

- Upgraded IDM add-on to be compatible with eConnect-base version 6.3.0.
- Magento version upgraded to 2.4.6. 
-  PHP version upgraded to 8.1.25. 
- Removed SwissUp theme and created LeanSwift Portal Theme.
- Search fields added for Payments page.
- Modified CustomerPortal and PaymentPortal to fit Magento Standards.

### **Bug Fixes**

- Documents uploaded for Short Pay Invoices not available in M3 Program ARS200 is resolved.
- Business context is added for the delivery note document type in IDM.
- Customer name search on Upper Cases is now working in  home page.
- Fixed Internal M3 Login authentication Issue.

## 22.4.0

### Features

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

### Bug Fixes

- Documents uploaded for Short Pay Invoices is not available in M3 Program ARS200 is resolved.
- Business context is added for the delivery note document type in IDM.
- Customer name search on Upper Cases is now working in  home page.

### Enhancements

- Upgraded IDM add-on to be compatible with latest eConnect-base.
- Magento version upgraded to 2.4.4. 
-  PHP version upgraded to 8.1.12. 
- Removed SwissUp theme and created LeanSwift Portal Theme.
- Search fields added for Payments page.
- Modified CustomerPortal and PaymentPortal to fit Magento Standards.


## 21.2.0

### Features

- Uploading supporting document for short pay invoices
- Download Order Confirmation documents
- Email Order Confirmation documents to customer
- Download Customer Invoice documents
- Email Customer Invoice documents to customer
- Download Delivery documents
- View Order shipment details

## 21.1.0

### Features

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

