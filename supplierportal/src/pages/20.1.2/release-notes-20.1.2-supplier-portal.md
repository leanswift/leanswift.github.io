
![Supplier portal banner](../../../../images/banner-supplier-portal.jpg)

# **Supplier Portal**

# **20.1.2**

## **Release Notes**

**Table of Contents**

- [Overview](#overview)

- [Environment Details](#environment-details)

- [Features](#features)

- [Highlights](#highlights)



## **Overview**

**LeanSwift Supplier Portal** for Infor M3 CloudSuite is a supplier self-service portal that enables efficient online communication with vendors. It is seamlessly integrated with Infor M3 Cloudsuite via ION. Supplier Portal helps automate the entire purchase-to-pay process for the customer.



## **Environment Details**

| _ **Software Name** _ | _ **Version** _ |
| --- | --- |
| Magento Open Source | 2.3.5 |
| eConnect Base Module Version | 2.0.0 |
| IDM Module version | 3.0.0 |
| RabbitMQ | 3.8.3 |
| ION Desk | 12.0.0 |
| Infor M3 | 16.1 |
| Infor ION Grid | 12.0.2.0.20180308-135417.2 |
| ION Package Number | SupplierPortal-ION-1.0.1 |




## **Features**
This is a patch release and contains all the standard features of 20.1.0 and 20.1.1

- My Account

- Purchase Orders

- Forecasts

- Performance Metrics

## **Highlights**

- When the Supplier email is not a valid hostname or when the Email is already registered, page redirects to LUMA theme. This is modified to retain the supplier portal theme.

- Company (CONO) is sent as parameter in ION Buyer approval request so that approval will be sent to the buyer (M3 user )irrespective of default company of the M3 user.
