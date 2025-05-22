![Customer portal banner](/Customerportal/src/images/customer-portal/front-end-user/CP_banner.jpg)

# **LeanSwift Customer Portal**

# **25.1.0**

## **Release Notes**

**Table of Contents**

  - [**Overview**](#overview)
  - [**Environment Details**](#environment-details)
  - [**Standard Features**](#standard-features)
  - [**Enhancements**](#enhancements)
  - [**Pre-Requisites**](#pre-requisites)
  - [**Limitations**](#limitations)
  - [**Point of Contact**](#point-of-contact)

## **Overview**

**LeanSwift Customer Portal** is a customer self-service web portal that enables users to get instance access to information about their orders, invoices, and payments. With additional add-ons, users can also make e-payments directly via the portal. It is seamlessly integrated with Infor M3 Cloud Suite using ION. Customer Portal offers a single point of access to structured information about customer transactions and self-service functionality such as pay invoices, user management and much more.

## **Environment Details**

| **Software Name**  |  **Version**  |
| --- | --- |
| Magento Open Source | 2.4.7 |
| LeanSwift eConnect Base | 6.4.1 |
| LeanSwift M3 Login | 25.1.0 |
| LeanSwift Customer Portal | 25.1.0 |
| LeanSwift Payment Portal | 25.1.0 |
| LeanSwift IDM | 4.3.0|
| RabbitMQ | 3.8.3 |
| ION Desk (CloudSuite) | 12.0.0 |
| Infor M3 (CloudSuite) | 16.1 |
| ION Package Version  |1.0.0  |

## **Standard Features**

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

## **Highlights
- The Customer Portal modules now support installation with Econnect without the need to create multiple websites.
- The features of the Customer Portal modules will remain consistent whether using Econnect or as a standalone.
- Econnect customers can access all Customer Portal features.
- We have updated the m3 login authentication  process by replacing mingle url with ifs service url
 
## **Pre-Requisites**

- Internal users must be active on Mingle / Infor OS to log into and use the portal.

- Internal users need at least one valid user role assigned in the 'm3 user roles' configuration to access the portal.

- Permissions must be granted to internal users in both the 'm3 user roles' section and the customer panel.

- CyberSource is the default payment gateway, so a CyberSource account is necessary for processing payments through the portal. Supporting any other payment gateway requires additional, customized development and is not available out-of-the-box.
## **Limitations**

- Multiple currency support is unavailable at the customer level.

- When importing customer data (updating multiple customer information via CSV), fields such as view sections, 'is admin,' and 'make payments' are mandatory and cannot be left empty.

- In this version, only credit card payments are supported via the portal.

- Customers cannot edit payment and billing information on CyberSource payment pages.

- Importing order history data is limited to 10,000 records per M3 customer number.

- Clearing downloaded files from IDM and Cron/Real-time configurations in IDM upload and download is not supported.

## **Point of Contact**

[prabhu.manoharan3@wipro.com ](mailto:prabhu.manoharan3@wipro.com )

[deepthi.tadikamalla@wipro.com ](mailto:deepthi.tadikamalla@wipro.com )

[silambarasan.kj3@wipro.com](mailto:silambarasan.kj3@wipro.com)

[saurabh.gupta77@wipro.com](mailto:saurabh.gupta77@wipro.com)

[ketankumar.zanzarukiya@wipro.com](mailto:ketankumar.zanzarukiya@wipro.com)

[kalaivani.nagarajan1@wipro.com](mailto:kalaivani.nagarajan1@wipro.com)


