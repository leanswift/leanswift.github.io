# Add-on for eConnect for M3

# **IDM**

## **Version 3.2.1-p1**


## Table of contents

  - [**Overview**](#overview)
  - [**Environment Details**](#environment-details)
  - [**Standard Features**](#standard-features)
  - [**Highlights**](#highlights)
  - [**Pre-requisites**](#pre-requisites)
  - [**Limitations**](#limitations)
  - [**Bug Fix**](#bug-fix)
  - [**Points of Contact**](#points-of-contact)
  
## **Overview**

 **LeanSwift eConnect for Infor M3** is a Magento extension that provides simple yet powerful integration between Magento eCommerce platform and Infor M3.

Extends standard Magento functionality and offers several transactions to ensure your eCommerce websites contain up-to-date information from your M3 ERP.

 **LeanSwift eConnect for Infor M3** is available for Magento Open Source and Magento Commerce and for Infor M3 version 7.x and above. It is also compatible with multi-tenant cloud editions of Infor M3 (Cloudsuite).

 **Add-on IDM** for eConnect provides capability to upload, download or search documents in Infor Document Management that can be leveraged in the web front-end.

## **Environment Details**

| **Environment** | **Version** |
| --- | --- |
| Magento Open source | 2.4.1 |
| Magento Community | 2.4.1 |
| eConnect | 20.3.0 |
| eConnect Base | 5.0.0 |
| Rabbitmq | 3.8.3 |
| ION Desk | 12.0 |
| PHP | 7.4.12 |

## **Standard Features**

Functionality remains the same as in the previous version.
Provides integration to Infor Document Management and allows access to attributes and documents in it that can be leveraged in the web front-end. Features include functions made available to build front-end functionality for the following operations,

- Upload to IDM
- Download from IDM
- Search in IDM

Download Invoices from IDM on the &quot;My Invoices&quot; page.
Options available for both scheduled as well as real-time access to IDM.

## **Pre-requisites**

- LeanSwift eConnect Base 5.0.0 must be installed on Magento 2.4.1 or greater
- If &quot;ION&quot; is selected as M3 connection protocol, ION API Service URL must be configured in order to access IDM ION APIs

## **Limitations**

- eConnect and hence the IDM add-on, can be set to work with only ONE of the two options, exclusively
- LeanSwift eLink or
- ION Document Flows and ION APIs
- In the eLink version, everytime user clicks on download, it downloads all the files.

## **Bug Fix**

- Downloading IDM files by clicking on 'download' will work even if there are multiple stores per website.

## **Points of Contact**

- [niranjan.b@leanswift.com](mailto:niranjan.b@leanswift.com)
- [nanthini.muralidaran@leanswift.com](mailto:nanthini.muralidaran@leanswift.com)
- [deepthi.tadikamalla@leanswift.com](mailto:deepthi.tadikamalla@leanswift.com)
- [nrithya.rajagopalan@leanswift.com](mailto:nrithya.rajagopalan@leanswift.com)

