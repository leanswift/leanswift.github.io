




# **eConnect for M3 19.4.0**
## Enterprise Edition



## **Magento Open source/Commerce**
## **& Infor M3 Integration**




# **Release Notes**

 

## **Table of Contents**
- [**Overview**](#overview)
- [**Environment Details**](#environment-details)
- [**Standard Features**](#standard-features)
- [**Enhancement**](#enhancement)
- [**Limitations**](#limitations)

## Overview

- LeanSwift eConnect for Infor M3 is a Magento extension that provides simple yet powerful integration between Magento eCommerce platform and Infor M3. 

- Extends standard Magento functionality and offers several transactions to ensure your eCommerce websites contain up-to-date information from your M3 ERP.

- LeanSwift eConnect for Infor M3 is available for Magento Open Source and Magento Commerce and for Infor M3 version 7.x and above. It is also compatible with multi-tenant cloud editions of Infor M3 (Cloudsuite).


## Environment Details
Multi Tenant:

| _ **Software Name** _ | _ **Version** _ |
| --- | --- |
| Infor M3 | 16.1 |
| ION Desk | 12.0.0 |
| MEC | 11.5.0.0.20190913084449 |
| M3 BOD Content Pack | 16.0.0.20190913110000 |


## Standard Features

All the standard functionalities of core eConnect (from version 19.3.0) are supported in
v19.4.0.

## Enhancement

- Manual sync option is available for Product, Customer and Order when ION is selected as mode of communication with M3
- Configurable option to limit the number of rows affected in manual sync process is available in the admin section


## Fixes

Email updates only once for a customer if existing email id is dummy


## Limitations

- Manual sync has a limit set to 200
- If more records are chosen, sync fails


