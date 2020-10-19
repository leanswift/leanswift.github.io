![Supplier portal banner](../../../images/banner-supplier-portal.jpg)

# Supplier Portal-Net Change Report

## Table of contents

  - [20.1.2](#2012)
    - [Fixes:](#fixes)
  - [20.1.1](#2011)
    - [Enhancement:](#enhancement)
    - [Fixes:](#fixes)
  - [20.1.0](#2010)
    - [Features:](#features)
#

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


