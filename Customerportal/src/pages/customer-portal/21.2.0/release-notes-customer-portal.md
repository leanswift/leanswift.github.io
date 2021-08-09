![Customer portal banner](/Customerportal/src/images/customer-portal/front-end-user/CP_banner.jpg)

# **LeanSwift Customer Portal**

# **21.2.0**

## **Release Notes**

**Table of Contents**

- [Overview](#overview)

- [Environment Details](#environment-details)

- [Standard Features](#standard-features)

- [Highlighted Features](#highlighted-features)

- [Technical Changes](#technical-changes)

- [Pre-Requisites](#pre-requisites)

- [Limitations](#limitations)

- [Validated Versions](#validated-versions)

- [Point of Contact](#point-of-contact)

## **Overview**

**LeanSwift Customer Portal** is a customer self-service web portal that enables users to get instance access to information about their orders, invoices, and payments. With additional add-ons, users can also make e-payments directly via the portal. It is seamlessly integrated with Infor M3 Cloud Suite using ION. Customer Portal offers a single point of access to structured information about customer transactions and self-service functionality such as pay invoices, user management and much more.



## **Environment Details**

| **Software Name**  |  **Version**  |
| --- | --- |
| Magento Open Source | 2.4.2 |
| LeanSwift eConnect Base | 6.1.0 |
| LeanSwift M3 Login | 1.1.0 |
| LeanSwift Customer Portal | 21.2.0 |
| LeanSwift Payment Portal | 2.0.0 |
| LeanSwift IDM | 4.0.0 |
| RabbitMQ | 3.8.3 |
| ION Desk (CloudSuite) | 12.0.0 |
| Infor M3 (CloudSuite) | 16.1 |
| Infor ION Grid (CloudSuite) | 2020-10.135425.10 |



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

## **Highlighted Features**

- Uploading supporting document for short pay invoices
- Download Order Confirmation documents 
- Email Order Confirmation documents to customer
- Download Customer Invoice documents
- Email Customer Invoice documents to customer
- Download Delivery documents

## **Technical Changes**

- Upgraded IDM add-on to be compatible with latest eConnect-base
- Modified CustomerPortal and PaymentPortal to fit Magento Standards

## **Pre-Requisites**

- Internal users should be active users on Mingle / Infor OS in order to be able to log into and use the portal.

- Internal users should have at least one valid user role assigned in ‘m3 user roles’ configuration to login.

- Internal users should have permissions granted in both ‘m3 user roles’ section and the customer panel.

- CyberSource is the default payment gateway. Hence a CyberSource account is required for taking payments from the portal. If any other payment gateway is required to be supported, that can be done only by additional, customized development and is not available out-of-the-box.


## **Limitations**


- Multiple currency support is not supported at the customer level.

- When importing customer data (update multiple customer information via csv), fields like view sections, ‘is admin’ and ‘make payments’ are mandatory and cannot be empty.

- Only Payments by Credit Card are supported via the portal in this version.
	
- Customers will not be able to edit payment and billing information on CyberSource payment pages.

- Import Order History data is limited to 10,000 records per M3 customer number.

- Clears the downloaded files from IDM and Cron/Real time configurations in IDM upload and download is not supported.


## **Validated Versions**

Chrome Version 92.0.4515.131


## **Point of Contact**


[niranjan.b@leanswift.com](mailto:niranjan.b@leanswift.com)

[oleksii.solonenko@leanswift.com](mailto:leksii.solonenko@leanswift.com)

[srinidhi.narayanan@leanswift.com](mailto:srinidhi.narayanan@leanswift.com)

[henrik.refsnes@leanswift.com](mailto:henrik.refsnes@leanswift.com)

