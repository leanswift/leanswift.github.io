
# Add-on for eConnect for M3

## **Multi-Warehouse**

## **Version 4.1.0**

**Table of Contents**


  - [**Overview**](#overview)
  - [**Environment Details**](#environment-details)
  - [**Standard Features**](#standard-features)
  - [**Enhancement**](#enhancement)
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
| eConnect | 2.3.0 |
| eConnect Base | 5.0.0 |
| Rabbitmq | 3.8.3 |
| ION Desk | 12.0 |
| PHP | 7.4.12 |

## **Standard Features**

Functionality remains the same as in the previous version.

**Add-on MWH** for eConnect provides synchronization of inventory from multiple warehouses in M3 and enables the warehouses to be used within Magento

- Synchronize on page load, on add to cart and on checkout
- Display stock in each warehouse in product detail page.


## **Enhancement**

- With 20.3.0, there is a major technical architectural change in the solution. BODs from ION are now configured to be sent to a REST API in Magento, which in turn sends them to RabbitMQ for storage and processing by eConnect. In the previous versions, ION sends BODs to RabbitMQ directly.

## **Pre-requisites**

- LeanSwift eConnect 20.3.0 must be installed on Magento 2.4.1 or greater.
- Wyomind Advanced Inventory extension for Magento 2 Version 7.7.6
Wyomind extension will support only with default source and not with multiple sources.

**Note :**
 When multiple stock zones are configured for same warehouse, mwh updates the stock as below:

When the stock is updated in stock zone YB, a BOD gets generated with value in YB which gets updated in eConnect.

When the stock is updated in stock zone Y9, a BOD gets generated with the value from MMS002&#39;s &#39;On-hand approve&#39; (YB+Y9). This value will get updated in eConnect in the Y9 zone

Now if YB is again updated with stock, ((new value in Y9) +YB) gets updated in the Y9 zone in econnect and so on.

_NOTE: This might be based on StockZone-Location settings in M3. If only one stock zone-warehouse is configured, the value that comes in BOD for that respective stock zone gets updated._


## **Point of Contacts**

- [niranjan.b@leanswift.com](mailto:niranjan.b@leanswift.com)
- [nanthini.muralidaran@leanswift.com](mailto:nanthini.muralidaran@leanswift.com)
- [deepthi.tadikamalla@leanswift.com](mailto:deepthi.tadikamalla@leanswift.com)
- [nrithya.rajagopalan@leanswift.com](mailto:nrithya.rajagopalan@leanswift.com)



