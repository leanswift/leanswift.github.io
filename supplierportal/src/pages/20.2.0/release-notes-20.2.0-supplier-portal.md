![Supplier portal banner](../../../../images/banner-supplier-portal.jpg)

# **Supplier Portal**

# **20.2.0**

## **Release Notes**

**Table of Contents**

- [Overview](#overview)

- [Environment Details](#environment-details)

- [Standard Features](#standard-features)

- [New Features](#new-features)

- [Add-ons](#add-ons)

- [Enhancements](#enhancements)

- [Limitations](#limitations)

- [Known Issues](#known-issues)

- [Validated Versions](#validated-versions)

- [Point of Contact](#point-of-contact)



## **Overview**

**LeanSwift Supplier Portal** for Infor M3 CloudSuite is a supplier self-service portal that enables efficient online communication with vendors. It is seamlessly integrated with Infor M3 Cloudsuite via ION. Supplier Portal helps automate the entire purchase-to-pay process for the customer.

## **Environment Details**

| _ **Software Name** _ | _ **Version** _ |
| --- | --- |
| Magento Open Source | 2.3.5 |
| eConnect Base Module Version | 4.0.0 |
| IDM Module version | 3.2.0 |
| RabbitMQ | 3.8.3 |
| ION Desk | 12.0.0 |
| Infor M3 | 16.1 |
| Infor ION Grid | 2020-10.135425.10 |



## **Standard Features**

This version includes all the standard features from 20.1.2 as mentioned below:

**Account**
  - Registration and Login
  - View Supplier Information
  - User Date Format Setting

**Purchase Orders**
  - View Purchase Orders
  - Search/Filter/Sort on Purchase Orders
  - Confirm Purchase Orders 
  - Download Purchase Orders Information
  - Upload documents into IDM against Purchase Orders
  - This is available ONLY if additional functionality for IDM integration is included as part of license
  
**Purchase Proposals/Forecasts**
  - View Purchase Forecasts
  - Search/Filter/Sort on Purchase Forecasts
  
**Performance Metrics**
  - View Quality metrics based on rejected quantity
  - View Delivery Performance metrics
  - View Purchase Price Variance metrics

## **New Features**

From Supplier Portal 20.2.0 , the following features will be available

**Advise / Advise All** 

This Add-on is used to Advise PO on line level or header level (status 40 ) and should be used along with Supplier Portal.

**Notify / Notify All**

This Add-on is used to Notify PO on line level or header level (status 45 ) and should be used along with Supplier Portal.

**Notify by Delivery Number**

This Add-on is used to Notify PO lines of different purchase orders based on the delivery number and should be used along with Supplier Portal.

**Confirm, Advise and Notify multiple PO**

This feature is to confirm or advise or notify multiple purchase orders. Separate buttons are available at global level in My Purchase Orders page.

**IDM upload for suppliers**

Upload or fetch supplier specific documents into IDM on the ‘My Documents’ section in the ‘My Accounts’ page.

**My Deliveries**

This Add-on is used to display deliveries and corresponding invoice matching status for all the lines that are goods received.

**User Management**

This Add-on is to manage sub-accounts (users) and their roles and permissions.

**Bell Notification**

This feature is to notify both supplier admin and users about the new updates on purchase order lines or forecast.

**Email Notifications**

Email is sent to supplier admin and the sub-accounts (based on user permissions) when a new PO / forecast is added or an existing purchase order / forecast is modified.

**My Invoices**

This Add-on is used to display all the  invoices associated with the supplier's PO  and also other details such as outstanding amount, due date and open/paid.

**User Tracking**

This Add-on is to configure the allowed number of Registrations (supplier admin ) and allowed sub-account users per supplier admin. 

**Refresh button on ‘My Purchase Orders’ page**

## **Add-ons**

- Advise/Notify - Advise/Notify Supplier PO`s
- My Invoices - Supplier Invoices
- My Deliveries - Supplier Deliveries

In addition econnect-base, IDM, User Management and User Tracking are supporting modules.

## **Enhancements**

- Forecast: 
  My Forecast will display only the Planned purchase orders that don't have status as Auto-Error 00 or Auto- Warning 05. Also, the Status column is removed from display.
- Confirm PO:
  Confirmed Purchase order line can be re-confirmed by modifying confirmed quantity or confirmed date any number of times as long as the status is 35. 
- My Documents :
  The Purchase order  Upload column is now modified as My Documents and supports both upload and download of documents. This makes it possible to fetch the document uploaded in   m3 for the particular PO using refresh icon.
  
## **Limitations**
 
 - Enter more than 3 characters in search field for appropriate results in PO page.
 - If multiple(more than 5) conditions are added or removed in a non-sequential manner, Filters may not fetch appropriate results.
 - During Advise All, if some error message is displayed Ex. Delivery number must be entered, Click refresh button for the input to be cleared before choosing another order to     Advise.
 - Similarly Input entered in Advise/Notify window gets cleared only if the action is complete or page is refreshed. 
 - Upload/Download Documents work only when IDM is Enabled
 - Order type ADN (Automatic Deliverynote Generation) flag value saved in Magento only once during reg ( assuming Order type configurations will not be changed in m3 ).

## **Known Issues**

- When SHAC is kept as 2 , and Automatic dely note generation is enabled , advise and notify is done  for a delivery note number  PPS360 / TransNotifyHead is called .
  when the SHAC is disabled for the same supplier and I advise a line with same delivery note number ( line is not added in PPS360 ) but since the delivery note number is         available  in pps360 during notify  the PPS360 / TransNotifyHead is called and the PPS001MI/NotifyDelNot is not called. This causes the line to remain in processing state.

- When one line of PO is advised  with a delivery note number (where Automatic dely note generation is enabled ) and  Advise all / Advise multiple po’s is tried for same PO       with delivery note number ,error message ‘Shipment advice is not allowed - the order is already advised with delivery note' is displayed.


## **Validated Versions**

- Chrome Version 86.0.4240.111
- Firefox Version 80.0.1 


## **Point of Contact**

[prabhu.mano@leanswift.com](mailto:prabhu.mano@leanswift.com)

[niranjan.b@leanswift.com](mailto:niranjan.b@leanswift.com)

[deepthi.tadikamalla@leanswift.com](mailto:deepthi.tadikamalla@leanswift.com)

[srinidhi.narayanan@leanswift.com](mailto:srinidhi.narayanan@leanswift.com)

[nrithya.rajagopalan@leanswift.com](mailto:nrithya.rajagopalan@leanswift.com)
