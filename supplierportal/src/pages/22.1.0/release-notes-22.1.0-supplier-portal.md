![Supplier portal banner](../../../../images/banner-supplier-portal.jpg)

# **Supplier Portal**

# **22.1.0**

## **Release Notes**

**Table of Contents**

- [Overview](#overview)

- [Environment Details](#environment-details)

- [Standard Features](#standard-features)

- [New Features](#new-features)

- [Highlights](#highlights)

- [Pre-Requisites](#pre-requisites)

- [Limitations](#limitations)

- [Known Issues](#known-issues)

- [Validated Versions](#validated-versions)

- [Point of Contact](#point-of-contact)


## **Overview**

**LeanSwift Supplier Portal** for Infor M3 CloudSuite is a supplier self-service portal that enables efficient online communication with vendors. It is seamlessly integrated with Infor M3 Cloudsuite via ION. Supplier Portal helps automate the entire purchase-to-pay process for the customer.

## **Environment Details**

|  **Software Name**  |  **Version**  |
| --- | --- |
| Magento Open Source | 2.4.3 |
| eConnect Base Module Version | 6.1.2 |
| IDM Module version | 4.1.0 |
| PHP | 7.4.27 |
| RabbitMQ | 3.7.2 |
| ION Desk | 12.0.0 |
| Infor M3 | 16.1 |
| Infor ION Grid | 2022.01.03 |



## **Standard Features**

This version includes all the standard features from 21.1.0 as mentioned below:

**Account**

Registration and Login

View Supplier Information

User Date Format Setting

**Purchase Orders**

View Purchase Orders, Search/Filter/Sort on Purchase Orders and Download Purchase Orders Information

**Confirm / Confirm All**

This feature is to Confirm a PO at line level or header level (status 35).

**Advise / Advise All**

This Add-on is used to Advise PO on line level or header level (status 40 ) and should be used along with Supplier Portal.

**Notify / Notify All**

This Add-on is used to Notify PO on line level or header level (status 45 ) and should be used along with Supplier Portal.

**Notify by Delivery Number**

This Add-on is used to Notify PO lines of different purchase orders based on the delivery number and should be used along with Supplier Portal.

**Confirm, Advise and Notify multiple PO**

This feature is to confirm or advise or notify multiple purchase orders. Separate buttons are available at global level in My Purchase Orders page.

**Refresh** button on ‘My Purchase Orders’ page

**Download** button on ‘My Purchase Orders’ to download purchase order information

**Upload documents into IDM against Purchase Orders**

  - This is available ONLY if additional functionality for IDM integration is included as part of license

**Bell Notification**

This feature is to notify both supplier admin and users about the new updates on purchase order lines or forecast.

**Email Notifications**

Email is sent to supplier admin and the sub-accounts (based on user permissions) when a new PO / forecast is added, or an existing purchase order / forecast is modified. 

**IDM upload for suppliers**

Upload or fetch supplier specific documents into IDM on the ‘My Documents’ section in the ‘My Accounts’ page.

**My Deliveries**

This Add-on is used to display deliveries and corresponding invoice matching status for all the lines that are goods received.

**User Management**

This Add-on is to manage sub-accounts (users) and their roles and permissions.

**My Invoices**

This Add-on is used to display all the invoices associated with the supplier’s PO and also other details such as outstanding amount, due date and open/paid.

**User Tracking**

This Add-on is to configure the allowed number of Registrations (supplier admin ) and allowed sub-account users per supplier admin.

**Purchase Proposals/Forecasts**

View Purchase Forecasts

Search/Filter/Sort on Purchase Forecasts

**Performance Metrics**

View Quality metrics based on rejected quantity

View Delivery Performance metrics

View Purchase Price Variance metrics


## **New Features**

**Supplier Onboarding**
 
Supplier portal onboarding allows supplier creation from portal itself. New supplier account is created using the invite sent by admin to his email account.

## **Highlights**

Supplier Portal supports MultiWebsite Scope

## **Pre-Requisites**

IDM add-on should be configured for My Purchase orders data to be displayed in supplier portal

## **Bug Fixes**

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

## **Limitations**

- Enter more than 3 characters in search field for appropriate results in PO page.
- If multiple (more than 5) conditions are added or removed in a non-sequential manner, Filters may not fetch appropriate results.
- During Advise All, if some error message is displayed Ex. Delivery number must be entered, Click refresh button for the input to be cleared before choosing another order to     Advise.
- Similarly Input entered in Advise/Notify window gets cleared only if the action is complete or page is refreshed.
- Upload/Download Documents work only when IDM is Enabled
- Order type ADN (Automatic Deliverynote Generation) flag value saved in Magento only once during reg (assuming Order type configurations will not be changed in m3).


## **Known Issues**

- When SHAC is kept as 2, and Automatic dely note generation is enabled , advise and notify is done for a delivery note number PPS360 / TransNotifyHead is called . when the SHAC   is disabled for the same supplier and I advise a line with same delivery note number (line is not added in PPS360) but since the delivery note number is available in pps360     during notify the PPS360 / TransNotifyHead is called and the PPS001MI/NotifyDelNot is not called. This causes the line to remain in processing state.

- When one line of PO is advised with a delivery note number (where Automatic dely note generation is enabled) and Advise all / Advise multiple po’s is tried for same PO with     delivery note number, error message ‘Shipment advice is not allowed - the order is already advised with delivery note' is displayed.

- Default configuration that comes with installation cannot be deleted.

- Success message when more number of PO lines are advised or notified is inconsistent

## **Recommendation**

  It is recommended to use eConnect and Supplier portal in separate instances.

## **Validated Versions**

  Chrome 98.0.4758.82

## **Point of Contact**

niranjan.b@leanswift.com

prabhu.mano@leanswift.com

deepthi.tadikamalla@leanswift.com

vaithiyanathan.paramasivam@leanswift.com

narayanan.gurusamy@leanswift.com

