![Supplier portal banner](../../../../images/banner-supplier-portal.jpg)

# **Supplier Portal**

# **23.3.0**

## **Release Notes**

**Table of Contents**

- [Overview](#overview)

- [Environment Details](#environment-details)

- [Standard Features](#standard-features)

- [Enhancements](#enhancements)

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
| Magento Open Source | 2.4.6 |
| eConnect Base Module Version | 6.3.0 |
| IDM Module version | 4.2.0 |
| ION Package Version | 23.3.0 |
| PHP  | 8.1.0 |
| RabbitMQ | 3.7.28 |
| ION Desk | 2022.01.03 |
| Infor M3 | 10.4.1.20220810_084103_01 |
| Advise and Notify | 22.4.0 |
| Supplier Invoices | 22.4.0 |
| Supplier Deliveries | 22.4.0 |
| Supplier User Tracking | 22.4.0 |
| User Management | 22.4.0 |
| Supplier Item Management | 22.4.0-P1 |


## **Standard Features**

This version includes all the standard features from **21.1.0** as mentioned below:

**Account**

- Registration and Login

- View Supplier Information

- User Date Format Setting

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

- View Purchase Forecasts

- Search/Filter/Sort on Purchase Forecasts

**Performance Metrics**

- View Quality metrics based on rejected quantity

- View Delivery Performance metrics

- View Purchase Price Variance metrics


## **Enhancements** 

- Existing Supplier Items from M3 is imported to Database during Supplier Registration2.
- Provided backend configuration for Supplier Onboarding My Information form submission message.
- TAX ID field characters can be configured from Magento Admin.
- Confirmation email will be sent to Supplier once onboarded to portal.


## **Pre-Requisites**

IDM add-on should be configured for My Purchase orders data to be displayed in supplier portal

## **Limitations** 

- Enter more than 3 characters in search field for appropriate results in PO page.
- If multiple (more than 5) conditions are added or removed in a non-sequential manner, Filters may not fetch appropriate results.
- During Advise All, if some error message is displayed Ex. Delivery number must be entered, Click refresh button for the input to be cleared before choosing another     order to Advise.
- Similarly, Input entered in Advise/Notify window is cleared only if the action is complete or page is refreshed.
- Upload/Download Documents work only when IDM is Enabled
- Order type ADN (Automatic Deliverynote Generation) flag value saved in Magento only once during reg (assuming Order type configurations will not be changed in m3). 
- Default configuration that comes with installation cannot be deleted. 
 

## **Known Issues** 

- When SHAC is kept as 2, and Automatic dely note generation is enabled , advise and notify is done for a delivery note number PPS360 / TransNotifyHead is called .       when the SHAC is disabled for the same supplier and I advise a line with same delivery note number (line is not added in PPS360) but since the delivery note number     is available in pps360 during notify the PPS360 / TransNotifyHead is called and the PPS001MI/NotifyDelNot is not called. This causes the line to remain in processing   state. 

- When one line of PO is advised with a delivery note number (where Automatic dely note generation is enabled) and Advise all / Advise multiple po’s is tried for same   PO with delivery note number, error message ‘Shipment advice is not allowed - the order is already advised with delivery note' is displayed. 

## **Recommendation**

- It is recommended to use eConnect and Supplier portal in separate instances.
 
## **Validated Versions** 

-  Chrome Version 115.0.5790.171

## **Point of Contact** 


- [silambarasan.kj3@wipro.com](mailto:silambarasan.kj3@wipro.com )

- [vaithiyanathan.paramasivam@wipro.com](mailto:vaithiyanathan.paramasivam@wipro.com )

- [ketankumar.zanzarukiya@wipro.com](mailto:ketankumar.zanzarukiya@wipro.com )

- [prabhu.manoharan3@wipro.com ](mailto:prabhu.manoharan3@wipro.com )

- [deepthi.tadikamalla@wipro.com ](mailto:deepthi.tadikamalla@wipro.com )

- [challa.anjana@wipro.com](mailto:challa.anjana@wipro.com )

- [alam.sreevidya@wipro.com ](mailto:alam.sreevidya@wipro.com )

- [narayanan.gurusamy@wipro.com](mailto:narayanan.gurusamy@wipro.com )


 
