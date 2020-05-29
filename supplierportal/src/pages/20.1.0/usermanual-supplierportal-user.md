# Supplier Portal

Supplier Portal User Manual

Version 1.0

May, 2020

## Overview


# Table of contents

- [Supplier Portal](#supplier-portal)
  - [Overview](#overview)
- [Table of contents](#table-of-contents)
- [System Overview](#system-overview)
  - [Organization of the Manual](#organization-of-the-manual)
  - [Architecture](#architecture)
  - [Features](#features)
  - [User Interface](#user-interface)
  - [Validated Versions](#validated-versions)
  - [Point of Contact](#point-of-contact)
- [User Guide for Suppliers](#user-guide-for-suppliers)
  - [Registration](#registration)
  - [Log in](#log-in)
  - [Forgot Password](#forgot-password)
  - [Log out](#log-out)
  - [My Settings](#my-settings)
  - [My Account](#my-account)
  - [My Purchase Orders](#my-purchase-orders)
    - [Paginate](#paginate)
    - [Sort](#sort)
    - [Search](#search)
    - [Filter](#filter)
    - [Filter on Status](#filter-on-status)
    - [Download as CSV](#download-as-csv)
    - [Confirm PO Line](#confirm-po-line)
    - [Confirm All Lines](#confirm-all-lines)
    - [Upload to IDM](#upload-to-idm)
  - [My Forecast](#my-forecast)
    - [Paginate](#paginate)
    - [Sort](#sort)
    - [Search](#search)
    - [Filter](#filter)
    - [Filter on Status](#filter-on-status)
    - [Download as CSV](#download-as-csv)
  - [My Performance Metrics](#my-performance-metrics)
    - [On-Time Delivery %](#on-time-delivery-)
    - [Quality - Rejected Inventory](#quality---rejected-inventory)
    - [Purchase Price Variance](#purchase-price-variance)
- [User Guide for Portal Admin](#user-guide-for-portal-admin)
  - [Log in](#log-in)
  - [Configuration](#configuration)
    - [Menus](#menus)
    - [eConnect-base Configuration](#econnect-base-configuration)
      - [Service Configuration](#service-configuration)
      - [Basic Data Configuration](#basic-data-configuration)
      - [Authentication](#authentication)
    - [Supplier Portal Settings](#supplier-portal-settings)
      - [General Configuration](#general-configuration)
      - [ION WorkFlow Configuration](#ion-workflow-configuration)
      - [Metrics Display](#metrics-display)
      - [On-Time Delivery KPI](#on-time-delivery-kpi)
      - [Email templates](#email-templates)
      - [Cron](#cron)
    - [Design Settings](#design-settings)
      - [General](#general)
      - [Frontend Color Codes](#frontend-color-codes)
      - [Logo Image size](#logo-image-size)
      - [Status Mapping](#status-mapping)
        - [PO Status Mapping](#po-status-mapping)
        - [Forecast Status Mapping](#forecast-status-mapping)
      - [Filter and Search](#filter-and-search)
        - [Purchaseorder Filter Mapping](#purchaseorder-filter-mapping)
        - [Forecast Filter Mapping](#forecast-filter-mapping)
    - [Exit System](#exit-system)
  - [Additional Functionality](#additional-functionality)
    - [IDM](#idm)
  - [ION Workflows](#ion-workflows)
  - [Logging](#logging)
    
# System Overview

LeanSwift Supplier Portal is a supplier self-service web portal that enables efficient online communication with vendors. It is seamlessly integrated with Infor M3 Cloudsuite via ION. Supplier Portal helps automate the entire purchase-to-pay process for the customer.

## Organization of the Manual

This manual describes the admin configuration of LeanSwift Supplier Portal for Infor M3 and is meant for the Portal administrator.

To view the user manual for Portal Users, click here.

## Architecture

The solution is built on **Magento Open Source Platform**. It interacts with **Infor M3** via **Infor ION Platform**. **RabbitMQ** is the message queue used to send/receive messages to/from ION.

\&lt;\&lt;Insert Architecture Image\&gt;\&gt;

## Features

- Register Supplier as Portal user (existing M3 suppliers only)
- View Supplier Information
- View Purchase Orders
- Search/Filter/Sort on Purchase Orders
- Confirm Purchase Orders
- Download Purchase Orders Information
- View Purchase Forecasts
- Search/Filter/Sort on Purchase Forecasts
- View Quality metrics based on rejected quantity
- View Delivery Performance metrics
- View Purchase Price Variance metrics
- User settings to set date format
- Configurable options for Portal Admin user

## User Interface

During setup, the Magento Admin panel is used to configure the portal. Some of the images and colors used in the user interface are configurable via the admin panel. The portal is accessible via any device using a web browser.

## Validated Versions

\&lt;\&lt;List versions of various software components\&gt;\&gt;

## Point of Contact

This document and the software it describes are provided by LeanSwift Solutions Inc. For

additional information regarding support, licensing, functionality etc. please contact LeanSwift

Solutions Inc. via contact form at http://www.leanswift.com or email [info@leanswift.com](mailto:info@leanswift.com).

# User Guide for Suppliers

**Note** : _Images should be from an environment which has the LeanSwift logo as company logo._

_Do not show any real username, email ids wherever possible._

## Registration

\&lt;\&lt; List images, prerequisites and steps to register as portal user \&gt;\&gt;

\&lt;\&lt; Mention that page for registration could be one of the two based on the kind of portal set up that has been done \&gt;\&gt;

Registration Page is used to register the user as supplier. The look and feel of registration page depends on whether econnect is installed along with supplier portal.

- When supplier portal is installed and no eConnect is there - Supplier portal registration page is displayed

\&lt;image\&gt;

- When supplier portal is installed and Connect is there
 New Registration page with checkbox to check the supplier registration. If checked supplier number is show

\&lt;image\&gt;

Prerequisites to register as supplier

To register, the supplier needs to be vendor in M3 and the supplier id needs to be in status &#39;20&#39; (approved) in M3.

Already registered supplier id cannot be registered again.

A user can either register as supplier or as econnect user and not as both.

Steps to register as supplier.

Go to Home page and select &#39;Create an Account&#39;

Based on whether econnect is installed or not , the registration


## Log in

\&lt;\&lt; List image, prerequisites and steps to register as portal user \&gt;\&gt;

\&lt;\&lt; Mention that page for login could be one of the two based on the kind of portal set up that has been done \&gt;\&gt;

## Forgot Password

\&lt;\&lt; List image, prerequisites and steps to reclaim or reset password \&gt;\&gt;

## Log out

\&lt;\&lt; Show the profile icon and logout option \&gt;\&gt;

## My Settings

\&lt;\&lt; Show the profile icon and settings page and provide description \&gt;\&gt;

## My Account

My Accounts section contains Account information,Buyer Information and Communication channels and address section.
<kbd>
<img alt="My Accounts" src="../../images/usermanual/my-accounts.png">
</kbd>
<kbd>
<img alt="My Accounts" src="../../images/usermanual/my-accounts-address.png">
</kbd>

## My Purchase Orders

\&lt;\&lt; Show an image and provide description of the overall page \&gt;\&gt;

\&lt;\&lt; List images and provide description for each of the sections below \&gt;\&gt;

My Purchase Orders section contains all the purchase orders that belongs to the registered supplier.Based on the Purchase order (Normal or Delivery Schedule purchase orders ) indicators will be shown to differentiate.Each purchase order has one or more purchase order lines. Purchase orders are displayed along with Order date,Currency,lowest status among the order lines in a PO. A single purchase order can hold more than 1000 PO lines and it will be displayed in a single page with scroll button.
<kbd>
<img alt="My Accounts" src="../../images/usermanual/purchase-order.png">
</kbd>
By clicking on the side arrow in a Purchase Order,it expands to display the purchase order lines and related information corresponding to the particular purchase order.The purchase order lines have Line Number, Sub Line Number,Item,Description,Quantity,Confirmed Quantity, Received Quantity,Price, U/M,Confirmed Price, Requested Date , Confirmed Date and Status.
Single select,Multi select or select all of the purchase order lines can be done 
<kbd>
<img alt="My Accounts" src="../../images/usermanual/purchase-orderlines.png">
</kbd>
### Paginate
Pagination is availabe to show a minimum of 10 PO  to maximum of 40 PO per page .
<kbd>
<img alt="My Accounts" src="../../images/usermanual/pagination.png">
</kbd>
### Sort
PO number, Order date and Status can be sorted ascendingly or descendingly. By default the POs are sorted based on the status.Single click on arrow mark (symbol pointing downwards) determines that the sort is descending. Double click on the arrow mark (symbol pointing upwards) determine the sort is ascending.
<kbd>
<img alt="My Accounts" src="../../images/usermanual/sort.png">
</kbd>
### Search

Search bar is available above the purchase order table . The Search bar is a text field and it also accomodates Filter and clear all buttons. It provides a simple text search functionality and can be used to search both at PO and PO line levels.

### Filter
Based on admin configuraion,the filter can perform Equals,Less Than, Greater Than,Contains,Starts With,Ends With. The number of filters that can be applied is configured in admin. The filters works in AND operation (if two filters f1 and f2 are added , the results will have POs that satisify f1 AND f2)
<kbd>
<img alt="My Accounts" src="../../images/usermanual/filter.png">
</kbd>

### Filter on Status

The Status filter is a dropdown having a list of PO status such as READY, PRINTED, ACTIVATED, SCHEDULED, CONFIRMED, ASN, NOTIFIED, RECEIVED, PARTIAL REJECTED, COMPLETE, PARTIAL INVOICED, INVOICED.
<kbd>
<img alt="My Accounts" src="../../images/usermanual/status-filter.png">
</kbd>

### Download as CSV

Download button is present in top right corner of the My Purchase Order page and My Forecast page. By default downloads all the data ,When the purchase order/forecast POs are filtered, it downloads the filtered results in CSV format. Downloaded File Name  has pre-defined format, Supplier number with Timestamp of download. For example, Y50001_1578908806.csv.
<kbd>
<img alt="My Accounts" src="../../images/usermanual/download-csv.png">
</kbd>

### Confirm PO Line

<kbd>
<img alt="My Accounts" src="../../images/usermanual/confirm-with-changes.png">
</kbd>

### Confirm All Lines

<kbd>
<img alt="My Accounts" src="../../images/usermanual/confirm-all-lines.png">
</kbd>

### Upload to IDM

<kbd>
<img alt="My Accounts" src="../../images/usermanual/idm-select.png">
</kbd>

<kbd>
<img alt="My Accounts" src="../../images/usermanual/idm-view.png">
</kbd>

## My Forecast

\&lt;\&lt; Show an image and provide description of the overall page \&gt;\&gt;

\&lt;\&lt; List images and provide description for each of the sections below \&gt;\&gt;




## My Performance Metrics

\&lt;\&lt; Show an image and provide description of the overall page and chart options/labels \&gt;\&gt;

### On-Time Delivery %

\&lt;\&lt; Show an image and provide description \&gt;\&gt;

### Quality - Rejected Inventory

\&lt;\&lt; Show an image and provide description \&gt;\&gt;

### Purchase Price Variance

\&lt;\&lt; Show an image and provide description \&gt;\&gt;
