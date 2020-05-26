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
      - [Settings](#settings)
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
        - [Filter and Search](#filter-and-search)
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

\&lt;\&lt; Show image and provide description \&gt;\&gt;

## My Purchase Orders

\&lt;\&lt; Show an image and provide description of the overall page \&gt;\&gt;

\&lt;\&lt; List images and provide description for each of the sections below \&gt;\&gt;

### Paginate

### Sort

### Search

### Filter

### Filter on Status

### Download as CSV

### Confirm PO Line

### Confirm All Lines

### Upload to IDM

(Optional Functionality)

## My Forecast

\&lt;\&lt; Show an image and provide description of the overall page \&gt;\&gt;

\&lt;\&lt; List images and provide description for each of the sections below \&gt;\&gt;

### Paginate

### Sort

### Search

### Filter

### Filter on Status

### Download as CSV

## My Performance Metrics

\&lt;\&lt; Show an image and provide description of the overall page and chart options/labels \&gt;\&gt;

### On-Time Delivery %

\&lt;\&lt; Show an image and provide description \&gt;\&gt;

### Quality - Rejected Inventory

\&lt;\&lt; Show an image and provide description \&gt;\&gt;

### Purchase Price Variance

\&lt;\&lt; Show an image and provide description \&gt;\&gt;


# User Guide for Portal Admin

## Log in

Log in to Magento Admin Panel using the URL provided to you and the applicable user

credentials.

<img alt="Admin screen" src="../../images/usermanual/adminscreen.png" width="200">


## Configuration

The Admin Panel allows the portal administrator to view and edit configuration required for the Supplier Portal to function.

**Note** : _Images for Admin should be from the restricted access menu that we would create for portal administrators and not the super admin user we usually use for ourselves._

### Menus

To access the LeanSwift Configuration, click the LeanSwift tab.

<img alt="Admin Menu" src="../../images/usermanual/admin-menu.png" width="350">

### eConnect-base Configuration

LeanSwift eConnect-base extension is a prerequisite for Supplier Portal. Provides the connectivity to eLink and/or Infor systems with the use of a generic function which decides whether to call the eLink / ION APIs based on the M3 Connection Protocol chosen in the backend

#### Service Configuration

Section enables the user to configure M3 communication and general usability related settings.

**M3 Connection Protocol** : Option to choose the M3 communication protocol either ION or eLink.eConnectBase Pick the option which is choosen.

**API Service URL:** Service URL is entered here.

**Email** : Define the e-mail address that will be used for error alerts if exceptions were to occur in

Magento and when any transaction in eConnect is not working due to service being down

**Error Email Template:** Enabled an option to choose an error email template can map over the customized template here.

**Debug/Log data:** Select &quot;Yes&quot; to log additional information in Magento. This setting is recommended in development but should be set to &quot;No&quot; in production to improve performance.

<img alt="Service Configuration" src="../../images/usermanual/serviceconfiguration.png">

#### Basic Data Configuration

The **Basic Data** section of the configuration contains key settings needed for the various transactions.


<img alt="Basic Configuration" src="../../images/usermanual/basicconfiguration.png">


#### Authentication

The section used to configure the connection parameters for connecting M3. An option to test the connection between Portal and M3.

<img alt="Basic Configuration" src="../../images/usermanual/authentication.png">


### Supplier Portal Settings

Supplier portal related settings and design configurations can be made here.
 
#### Settings

The section provides configuration for the company details and other settings which are associated for the behaviour
 of the system.
 
##### General Configuration

**Company Name:** Provide the company name.

**Company Email** : Alerts will be sent to the company email.

**Debug/Log data:** Select &quot;Yes&quot; to log additional information in Magento. This setting is recommended in development but should be set to &quot;No&quot; in production to improve performance.

<img alt="General Configuration" src="../../images/usermanual/supplier-settings/general.png">

##### ION WorkFlow Configuration

<img alt="workflow Configuration" src="../../images/usermanual/supplier-settings/workflow.png">

##### Metrics Display

<img alt="metrics display" src="../../images/usermanual/supplier-settings/metrics.png">

##### On-Time Delivery KPI

<img alt="on-time delivery" src="../../images/usermanual/supplier-settings/ontime-delivery.png">

##### Email templates

The section provides an option to choose email templates for each operation. It is configured with default email
 templates. When a new email template is created it can be changed over here. 

<img alt="Email templates" src="../../images/usermanual/supplier-settings/email-templates.png">

##### Cron

The section contains cron configuration for sending PO request to M3 and getting forecast PO from M3.

<img alt="CRON Configuration" src="../../images/usermanual/supplier-settings/cron.png">

#### Design Settings

The section provides configuration for the company images with color code configuration affecting frontend behaviour
with an option to choose different colors for each status of Purchase order and forecast. It provides
an option to create customizable filters for the purchase order and forecast pages.

##### General

The section contains information to be basic configuration for company.

**Company Logo:** Provide the company logo.

**Company Logo:** Provide the product logo.

**Homepage Banner:** Provide the homepage banner.

**Facicon Image:** Provide the Favicon for the website.

**Show Supplier Portal Homepage:** When an option selected as &quot;Yes&quot; Supplier portal homepage is shown.When
 it is set to &quot;No&quot; default homepage configured to website will be displayed.
 
 > The option wil be enabled only when LeanSwift Econnect Module is installed 

**Show document upload option:** When an option is selected as &quot;Yes&quot; upload document in
 Purchase order page will be displayed. When set to &quot;No&quot; upload document is disabled.

> The option wil be enabled only when LeanSwift IDM Module is installed

<img alt="General Configuration" src="../../images/usermanual/supplier-design/general.png">

##### Frontend Color Codes  

<img alt="Frontend color code" src="../../images/usermanual/supplier-design/frontend-color.png">

##### Logo Image size

<img alt="Logo Image size" src="../../images/usermanual/supplier-design/logo-imagesize.png">

##### Status Mapping

###### PO Status Mapping

<img alt="PO status mapping" src="../../images/usermanual/supplier-design/po-status-mapping.png">

###### Forecast Status Mapping

<img alt="Forecast status mapping" src="../../images/usermanual/supplier-design/forecast-status-mapping.png">

##### Filter and Search

###### Purchaseorder Filter Mapping

<img alt="Purchaseorder filter mapping" src="../../images/usermanual/supplier-design/filter-po.png">

###### Forecast Filter Mapping

<img alt="Forecast filter mapping" src="../../images/usermanual/supplier-design/filter-forecast.png">

### Exit System

Log out from Magento admin using the link at the top right.

\&lt;\&lt; Show image \&gt;\&gt;

## Additional Functionality

### IDM

&#39;Uploading documents into IDM against Purchase Orders&#39; requires LeanSwift IDM Magento Extension.

\&lt;\&lt; Provide link to eConnect-base Configuration page \&gt;\&gt;

## ION Workflows

\&lt;\&lt; Mention about the custom ION Workflows required for the functioning of the portal, details on functionality, prerequisites, how to set up/install, basic troubleshooting, if any. Add relevant images from MT demo environment \&gt;\&gt;

## Logging

\&lt;\&lt; Brief description of how logs are created/maintained, what information are logged and where to find/view logs \&gt;\&gt;