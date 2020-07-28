# User Guide - MO Creation

<img src="../../../images/banner-mobilefirst-cloudsuite.jpg" alt="banner" style="zoom:100%;" />



# Table of contents

- **[About this guide](#about-this-guide)**

  - [Intended Audience](#intended-audience)
    - [MO Creation standard functionality](#std-func)

- **[Technical details, Workflow & Screen Layouts](#tech-details)**

  - [Get Facility list](#get-facility)
  - [Get Warehouse list](#get-warehouse)
  - [Get item basic](#item-basic)
  - [Get item warehouse basic data](#whs-basic)
  - [Get item basic details](#item-details)
  - [Create manufacturing order](#crt-mo)

  

# <a name="about-this-guide"></a>About this guide

### <a name="intended-audience"></a>Intended Audience

MobileFirst Configuration User Guide provides guidance for LeanSwift customers and consultants regarding understanding the basic concept, functionality and configuration of the MO Creation Standard App. Further information about MobileFirst standard applications can be found at [www.inform3marketplace.com](http://www.inform3marketplace.com).  



#### **<a name="std-func"></a>MO Creation standard functionality**

The intended use of this app is for a user to be able to quickly and simply create a Manufacturing Order (MO) from an iOS device. The application is not intended to re-create all of the options available to the user within M3 but be a quick on-the-go option to create missing/additional Manufacturing orders manually.

# <a name="tech-details"></a>Technical details, Workflow & Screen Layouts

This section provides details on the desired workflow within the applications, rough screen layouts as well as details on back-end API/SQL logic to apply for each step.

The Warehouse field and Location field auto filled with logged in user’s default warehouse and location. 

The user Id will be fetched from MNS150MI/GetUserInfo using the user id the user data will be fetched from MNS150MI/GetUserData. 

This will happen once the user logs in. In the MO Creation module, the user facility and warehouse will be selected from the list of warehouse and facility fetched from MMS005MI/LstWarehouses and CRS008MI/ListFacility respectively. 

### <a name="get-facility"></a>Get Facility list

**API:** CRS008MI/ListFacility

Input field required:

| Field | Description |
| ----- | ----------- |
| CONO  | Company     |
| FACI  | Facility    |

### <a name="get-warehouse"></a>Get Warehouse list

**API:** MMS005MI/LstWarehouses

Input field required:

| Field | Description    |
| ----- | -------------- |
| CONO  | Company        |
| FWHL  | From Warehouse |
| TWHL  | To Warehouse   |
| DCIN  | DC info        |
| LMTS  | Time Stamp     |

/*image*/

Enter the Product number in the product Field.

Product numbers can be found in MMS001, on submitting a valid item number the product structure type will be fetched and auto populated.

### <a name="item-basic"></a>Get item basic

**API:** MMS200MI/GetItmBasic

Input field required:

| Field | Description |
| ----- | ----------- |
| CONO  | Company     |
| ITNO  | Item number |

### <a name="whs-basic"></a>Get item warehouse basic data

**API:** MMS200MI/GetItmWhsBasic

Input field required:

| Field | Description |
| ----- | ----------- |
| CONO  | Company     |
| ITNO  | Item number |
| WHLO  | Warehouse   |

### <a name="item-details"></a>Get item basic details

API: PDS001MI/List

Input field required:

| **Field** | **Description** |
| --------- | --------------- |
| CONO      | Company         |
| PRNO      | Item number     |
| FACI      | Facility        |

After Successful retrieving of product structure type add required quantity and choose the pick date and select the status.

### <a name="crt-mo"></a>Create manufacturing order

**API:** PMS001MI/CrtMO

Input field required:

| **Field** | **Description**                                 |
| --------- | ----------------------------------------------- |
| CONO      | Company                                         |
| PRNO      | Item number                                     |
| STRT      | Structure type                                  |
| ORTY      | Order type                                      |
| MAUN      | Unit of measure                                 |
| DSP1      | Warning - Date is earlier than today's          |
| DSP2      | Warning - Start date may be  earlier than       |
| DSP3      | Warning - Finish date &1  gives earliest finish |
| DSP5      | Warning - Alternative routing identity          |
| DSP6      | Warning - Ignore order multiple                 |
| WHST      | Status                                          |
| ORQA      | Order quantity                                  |
| STDT      | Start date                                      |
| FIDT      | Finish date                                     |

On slide to report the create manufacturing order call will be made and respective success/failure message will be thrown.

/*image*/

