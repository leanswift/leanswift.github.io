![](RackMultipart20201224-4-dzt8sl_html_390ba5139005650c.png)

# **eConnect 20.3.0**

# Table of contents

- [**eConnect 20.3.0**](#econnect-2030)
  - [**Internal Release Notes**](#internal-release-notes)
- [**Environment Details**](#environment-details)
- [**Standard Features**](#standard-features)
- [**New Features/Enhancements**](#new-featuresenhancements)
    - [**LeanSwift AMQP Connection**](#leanswift-amqp-connection)
    - [**Enterprise Connector Removal**](#enterprise-connector-removal)
    - [**Additional Entity Attribute Mapping**](#additional-entity-attribute-mapping)
    - [**Authentication File Upload Option**](#authentication-file-upload-option)
    - [**Update on item price**](#update-on-item-price)
- [**Highlights**](#highlights)
- [**JIRA References**](#jira-references)
- [**GitHub Links**](#github-links)
- [**Point of Contact**](#point-of-contact)


# **Environment Details**

| _ **Software Name** _ | _ **Version** _ |
| --- | --- |
| Magento version | 2.4.1 |
| PHP version | 7.4.12 |
| RabbitMQ | 3.8.3 |
| Infor M3 (ST) | 13.4 |
| Infor M3 (MT) | 16.1 |
| ION Desk | 12.0.0 |

# **Standard Features**

All the standard functionalities of core eConnect are supported in v20.3.0, which includes the following:

- Product Addition
- Product Synchronization
- Customer Price Synchronization
- Inventory Synchronization
- Customer Registration
- Customer Addition
- Customer Synchronization
- Order Creation
- Order Synchronization
- Shipment Synchronization
- Invoice History
- Order History
- Initial Load

# **New Features/Enhancements**

### **LeanSwift AMQP Connection**

New AMQP connection to handle the eConnect related BODs in RabbitMQ.
 Provided the option in the Backend for the same to give the RabbitMQ credentials.

### **Enterprise Connector Removal**

No more Enterprise Connector. All the eConnect BODs from ION will now contact eConnect REST API directly instead of sending to rabbitmq.

### **Additional Entity Attribute Mapping**

Custom BODs created for Product, Customer and Order are replaced with API calls now. Provided the backend setting to configure APIs based on the entity type. This allows to trigger the APIs when the corresponding BOD is received.

### **Authentication File Upload Option**

Uploading the .ionapi file will automatically populate the authentication details

### **Update on item price**

Provided option to choose which field can be Item Price - MMSAPR / ODSAPR

Note : The base price that updates for an item based on odsapr setting will work on website scope by picking the price list and currency based on website scope but customer specific price will update based on latest price bod 

# **Highlights**

- _maxReturnedRecords_ option in the API requestis now configurable

- Customer Default Address from the CustomerPartyMaster BOD are now added to Magento

- Table creation and Attribute creation will be done as per Magento standard

- Usage of mixins in javascript instead of _map_



# **Point of Contact**

- [prabhu.mano@leanswift.com](mailto:prabhu.mano@leanswift.com)
- [niranjan.b@leanswift.com](mailto:prabhu.mano@leanswift.com)
- [deepthi.tadikamalla@leanswift.com](mailto:prabhu.mano@leanswift.com)
- [srinidhi.narayanan@leanswift.com](mailto:prabhu.mano@leanswift.com)
- [nrithya.rajagopalan@leanswift.com](mailto:prabhu.mano@leanswift.com)


