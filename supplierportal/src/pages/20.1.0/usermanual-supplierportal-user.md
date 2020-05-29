![Supplier portal banner](../../../../images/banner-supplier-portal.jpg)

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

versions of various software components used in Supplier portal:

- Magento community version: 2.3.4
- eConnect Base Module Version: 2.0.0
- Supplier portal Module Version: 1.0.0
- Idm Module version: 3.0.0


## Point of Contact

This document and the software it describes are provided by LeanSwift Solutions Inc. For

additional information regarding support, licensing, functionality etc. please contact LeanSwift

Solutions Inc. via contact form at http://www.leanswift.com or email [info@leanswift.com](mailto:info@leanswift.com).

# User Guide for Suppliers

**Note** : _Images should be from an environment which has the LeanSwift logo as company logo._

_Do not show any real username, email ids wherever possible._

## Registration

Registration Page is used to register the user as supplier Supplier portal registration page is displayed looks like below

<kbd><img alt="Registration Page without econnect" src="../../images/usermanual/registationpage-without-econnect.png" width="500"></kbd>

Prerequisites to register as supplier

-To register, the supplier needs to be vendor in M3 and the supplier id needs to be in status &#39;20&#39; (approved) in M3.

-Already registered supplier id cannot be registered again.

-A user can either register as supplier or as econnect user and not as both.

Steps to register as supplier.

-Go to Home page and select &#39;Create an Account&#39;

-Based on whether econnect is installed or not , the registration portal appears with/without supplier theme.

-Once the supplier registration is completed and sent for buyer approval,user is notified with message "Thank you for registering with  us. Your request has been sent for review. It may take a few hours or days to receive a response" in the homepage

<kbd><img alt="Registration Page with econnect" src="../../images/usermanual/after-registration.png" width="500"></kbd>

**Note** : Once registration is complete, approval request is sent to buyer. Supplier can login only after the buyer has approved the registration request.Supplier will be notified with email regarding the approval/decline of the registration to registered email id.

## Log in

The Homepage/Login page has username and password. It can also be customised to incorporate CAPTCHA.

<kbd><img alt="Registration Page with econnect" src="../../images/usermanual/homepage-supplier.png" width="500"></kbd>

The homepage is customised with error messages for empty or incorrect username and password.

<kbd><img alt="Registration Page with econnect" src="../../images/usermanual/homepage-error.png" width="500"></kbd>

<kbd><img alt="Registration Page with econnect" src="../../images/usermanual/homepage-error-incorrect password.png" width="500"></kbd>


## Forgot Password

\&lt;\&lt; List image, prerequisites and steps to reclaim or reset password \&gt;\&gt;

## Log out

\&lt;\&lt; Show the profile icon and logout option \&gt;\&gt;

## My Settings

Date Format can be modified in this section.The selected date format will be displayed as *Changed Date Format* below the dropdown.

<kbd><img alt="My Accounts" src="../../images/usermanual/my-settings.png"  width="500"></kbd>

## My Account

My Accounts section contains Account information,Buyer Information and Communication channels and address section.

<kbd><img alt="My Accounts" src="../../images/usermanual/my-accounts.png"  width="500"></kbd>

<kbd><img alt="My Accounts" src="../../images/usermanual/my-accounts-address.png"  width="500"></kbd>


## My Purchase Orders

My Purchase Orders section contains all the purchase orders that belongs to the registered supplier.Based on the Purchase order (Normal or Delivery Schedule purchase orders ) indicators will be shown to differentiate.Each purchase order has one or more purchase order lines. Purchase orders are displayed along with Order date,Currency,lowest status among the order lines in a PO. A single purchase order can hold more than 1000 PO lines and it will be displayed in a single page with scroll button.

<kbd><img alt="My Accounts" src="../../images/usermanual/purchase-order.png" width="500"></kbd> 

By clicking on the side arrow in a Purchase Order,it expands to display the purchase order lines and related information corresponding to the particular purchase order.The purchase order lines have Line Number, Sub Line Number,Item,Description,Quantity,Confirmed Quantity, Received Quantity,Price, U/M,Confirmed Price, Requested Date , Confirmed Date and Status.
Single select,Multi select or select all of the purchase order lines can be done 

<kbd><img alt="My Accounts" src="../../images/usermanual/purchase-orderlines.png" width="500"></kbd>


### Paginate

Pagination is availabe to show a minimum of 10 PO  to maximum of 40 PO per page.

<kbd><img alt="My Accounts" src="../../images/usermanual/pagination.png" width="500"></kbd>


### Sort

PO number, Order date and Status can be sorted ascendingly or descendingly. By default the POs are sorted based on the status.Single click on arrow mark (symbol pointing downwards) determines that the sort is descending. Double click on the arrow mark (symbol pointing upwards) determine the sort is ascending.

<kbd><img alt="My Accounts" src="../../images/usermanual/sort.png" width="500"></kbd>


### Search

Search bar is available above the purchase order table . The Search bar is a text field and it also accomodates Filter and clear all buttons. It provides a simple text search functionality and can be used to search both at PO and PO line levels.


### Filter

Based on admin configuraion,the filter can perform Equals,Less Than, Greater Than,Contains,Starts With,Ends With. The number of filters that can be applied is configured in admin. The filters works in AND operation (if two filters f1 and f2 are added , the results will have POs that satisify f1 AND f2)

<kbd><img alt="My Accounts" src="../../images/usermanual/filter.png" width="500"></kbd>


### Filter on Status

The Status filter is a dropdown having a list of PO status such as READY, PRINTED, ACTIVATED, SCHEDULED, CONFIRMED, ASN, NOTIFIED, RECEIVED, PARTIAL REJECTED, COMPLETE, PARTIAL INVOICED, INVOICED.

<kbd><img alt="My Accounts" src="../../images/usermanual/status-filter.png" width="500"></kbd>


### Download as CSV

Download button is present in top right corner of the My Purchase Order page and My Forecast page. By default downloads all the data ,When the purchase order/forecast POs are filtered, it downloads the filtered results in CSV format. Downloaded File Name  has pre-defined format, Supplier number with Timestamp of download. For example, Y50001_1578908806.csv.

<kbd><img alt="My Accounts" src="../../images/usermanual/download-csv.png" width="500"></kbd>


### Confirm PO Line

To Confirm a PO line select a single PO line or multiple lines and click on the Confirm button.
Conf qty, Conf Price and Conf Date can be modified. By default, when a PO line is confirmed with changes, approval request is sent to ION and waiting symbol is shown as below

<kbd><img alt="My Accounts" src="../../images/usermanual/confirm-with-changes.png" width="500"></kbd>

### Confirm All Lines

<kbd><img alt="My Accounts" src="../../images/usermanual/confirm-all-lines.png" width="500"></kbd>

### Upload to IDM

<kbd><img alt="My Accounts" src="../../images/usermanual/idm-select.png" width="500"></kbd>

<kbd><img alt="My Accounts" src="../../images/usermanual/idm-view.png" width="500"></kbd>

## My Forecast

<kbd><img alt="My Accounts" src="../../images/usermanual/my-forecast.png" width="500"></kbd>

## My Performance Metrics

Currently there are three types of graphs supported, they are :
- on-Time Delivery
- Quality - Rejected Inventory
- Purchase Price Variance.
Graph can be viewed either as bar or line chart (selected from dropdown in right corner). The graph can also be plotted for Monthly , Quarterly or yearly based on the options selected.

<kbd><img alt="My Accounts" src="../../images/usermanual/my-performance-metrics.png" width="500"></kbd>


### On-Time Delivery %

This metric records the percentage of inbound deliveries received on time, that is *Requested Delivery Date* Vs *Actual Delivery Date*.

<kbd><img alt="My Accounts" src="../../images/usermanual/on-time-delivery.png" width="500"></kbd>

### Quality - Rejected Inventory

 This metric records the total number of rejected supplies in a given period of time, that is Rejected Quantity.
 
 <kbd><img alt="My Accounts" src="../../images/usermanual/quality-graph.png" width="500"></kbd>

### Purchase Price Variance

This metric records the difference between the actual price paid to buy an item and its standard price as confirmed by the supplier, multiplied by the actual number of units purchased (Confirmed Quantity), that is, Confirmed Price Vs Invoiced Price.

<kbd><img alt="My Accounts" src="../../images/usermanual/ppv.png" width="500"></kbd>


