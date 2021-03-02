![Supplier portal banner](../../../../images/banner-supplier-portal.jpg)

# **Supplier Portal**

# **21.1.0**

## **Release Notes**

**Table of Contents**

- [Overview](#overview)

- [Environment Details](#environment-details)

- [Standard Features](#standard-features)

- [Validated Versions](#validated-versions)

- [Point of Contact](#point-of-contact)

## **Overview**

**LeanSwift Supplier Portal** for Infor M3 CloudSuite is a supplier self-service portal that enables efficient online communication with vendors. It is seamlessly integrated with Infor M3 Cloudsuite via ION. Supplier Portal helps automate the entire purchase-to-pay process for the customer.

## **Environment Details**

|  **Software Name**  |  **Version**  |
| --- | --- |
| Magento Open Source | 2.4.1 |
| eConnect Base Module Version | 5.0.0 |
| IDM Module version | 3.2.2 |
| ION Package | 2.0.0|
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

- **LeanSwift AMQP Connection**
  - New AMQP connection to handle the eConnect related BODs in RabbitMQ.
  - Provided the option in the Backend for the same to give the RabbitMQ credentials.
  - 
- **Enterprise Connector Removal**
  - No more Enterprise Connector. All the eConnect BODs from ION will now contact eConnect REST API directly instead of sending to rabbitmq.


## **Load Testing Metrics**

**1000 Purchase orders with 3lines**

- Time taken for sending purchase order API: 35.99594783783
- Total time taken for rabbitmq processing : 12.22 mins
- Bods/sec time :  1.6/sec - 2.0/sec

**1000 purchase orders with 1000 lines(with batch)** 

- Time taken for sending purchase order API:  .(1614681393.4272-1614681392.4035) for pushing one batch with 10 purchase orders 
- Total time taken for rabbitmq processing : 31 minutes 20 secs
- Bods/sec time : 0.4/sec

**100 purchase orders with 1000 lines(without batch)**

- Time taken for sending purchase order API: 42.4717841
- Total time taken for rabbitmq processing : 3.10 mins
- Bods/sec time : 0.4/sec - 0.6/sec
  

## **Validated Versions**

 Chrome 88.0.4324.190


## **Point of Contact**

[prabhu.mano@leanswift.com](mailto:prabhu.mano@leanswift.com)

[niranjan.b@leanswift.com](mailto:niranjan.b@leanswift.com)

[srinidhi.narayanan@leanswift.com](mailto:srinidhi.narayanan@leanswift.com)

[nrithya.rajagopalan@leanswift.com](mailto:nrithya.rajagopalan@leanswift.com)
