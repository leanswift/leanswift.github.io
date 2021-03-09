
# Add-on for eConnect for M3

## **Multi-Warehouse**

## **Version 4.1.1**

**Table of Contents**


  - [**Overview**](#overview)
  - [**Environment Details**](#environment-details)
  - [**Standard Features**](#standard-features)
  - [**Enhancement**](#enhancement)
  - [**Bugfix**](#bugfix)
  - [**Pre-requisites**](#pre-requisites)
  - [**Point of Contacts**](#point-of-contacts)

## **Overview**

 **LeanSwift eConnect for Infor M3** is a Magento extension that provides simple yet powerful integration between the Magento eCommerce platform and Infor M3.

Extends standard Magento functionality and offers several transactions to ensure your eCommerce websites contain up-to-date information from your M3 ERP.

 **LeanSwift eConnect for Infor M3** is available for Magento Open Source and Magento Commerce and for Infor M3 version 7.x and above. It is also compatible with multi-tenant cloud editions of Infor M3 (Cloudsuite).

 **Add-on MWH** for eConnect provides synchronization of inventory from multiple warehouses in M3 and enables the warehouses to be used within Magento.

## **Environment Details**

| **Environment** | **Version** |
| --- | --- |
| Magento Open source | 2.4.1 |
| Magento Community | 2.4.1 |
| eConnect-Community | 20.3.1 |
| eConnect-Commerce | 20.3.1 |
| eConnect Base | 5.0.0 |
| Rabbitmq | 3.8.3 |
| ION Desk | 12.0 |
| PHP | 7.4.12 |
| ION-BOD package | 3.0.0 |

## **Standard Features**

Functionality remains the same as in the previous version.

**Add-on MWH** for eConnect provides synchronization of inventory from multiple warehouses in M3 and enables the warehouses to be used within Magento

- Synchronize on page load, on add to cart and on checkout
- Display stock in each warehouse in product detail page.


## **Enhancement**

- In the Multi warehouse module, EXPORTMI to MITLOC table is used to fetch Allocatable Net and OnHandBalance stock values based on StockZone + Warehouse + Company + Item Number.

_Note: Tested only on M3-Multi-tenant_

## **Bugfix**

- Errors on running setup:di:compile has been fixed.


## **Pre-requisites**

- **LeanSwift eConnect 20.3.1 must be installed on Magento open source 2.4.1.**
- Wyomind Advanced Inventory extension for Magento 2 Version 7.7.6
_Wyomind extension will support only with default source and not with multiple sources._

**Note :**
 If stocks from multiple ware-house are required, necessary warehouse must be part of basic data configuration.

## **Point of Contacts**

- [niranjan.b@leanswift.com](mailto:niranjan.b@leanswift.com)
- [nanthini.muralidaran@leanswift.com](mailto:nanthini.muralidaran@leanswift.com)
- [deepthi.tadikamalla@leanswift.com](mailto:deepthi.tadikamalla@leanswift.com)
- [nrithya.rajagopalan@leanswift.com](mailto:nrithya.rajagopalan@leanswift.com)



