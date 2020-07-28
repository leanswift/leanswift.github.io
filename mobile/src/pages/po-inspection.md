

# User Guide - PO Inspection

<img src="../../../images/banner-mobilefirst-cloudsuite.jpg" alt="banner" style="zoom:100%;" />



# Table of contents

- **[About this guide](#about-this-guide)**
  - [Intended Audience](#intended-audience)
    - [PO Inspection standard functionality](#std-func)
- **[Technical details](#tech-details)**
  - [List Warehouse](#list-whsl)
  - [Validate PO](#validate-po)
  - [Get Line Items](#line-items)
  - [Get Line Quantity Details](#line-qty)
  - [Get Container Info](#container-info)
  - [Get Reject Reasons](#reject-reasons)
  - [Validate Location](#retr-loc)
  - [PO Inspection](#inspect)
- **[Workflow, Screen Layouts & API Logic](#wrk)**
  - [Settings](#settings)
  - [Purchase Order](#po)
  - [Line Items](#lines)
  - [Inspecting Line Item](#line-details)
  - [Choosing QI Result](#qi-res)
  - [Fill Required Details](#fill-details)
  - [Submit the Inpection](#confirm-demo)
- **[M3 sample workflow](#m3sample)**
  - [Create Purchase order PPS200](#crt-po)
  - [Receive the order in PPS300](#receive-po)



# <a name="about-this-guide"></a>About this guide

### <a name="intended-audience"></a>Intended Audience

MobileFirst Configuration User Guide provides guidance for LeanSwift customers and consultants regarding understanding the basic concept, functionality and configuration of the PO Inspection Standard App. Further information about MobileFirst standard applications can be found at [www.inform3marketplace.com](http://www.inform3marketplace.com).

#### **<a name="std-func"></a>PO Inspection standard functionality**

The PO Inpsection for Infor M3 provides for the ability to inspect the items received via M3 Purchase Orders into a warehouse. In M3 terms, it is the ability to inspect a PO.

# **<a name="tech-details"></a>Technical details**

### <a name="list-whsl"></a>List Warehouse

**API:** MMS005MI/LstWarehouses

Input field required:

| Field | Description    |
| ----- | -------------- |
| CONO  | Company        |
| FWHL  | From Warehouse |
| TWHL  | To Warehouse   |
| DCIN  | DC info        |
| LMTS  | Time Stamp     |

### <a name="validate-po"></a>Validate PO #

**API:** PPS200MI/GetHead

Input field required:

| Field | Description    |
| ----- | -------------- |
| CONO  | Company        |
| PUNO  | Purchase Order |

### <a name="line-items"></a>Get Line Items

**API:** PPS310MI/LstReceivedPO

Input field required:

| Field | Description    |
| ----- | -------------- |
| PUNO  | Purchase Order |

Select the line item from the list. Depending on the PO's order type the items will be under single put away or two step put away.

### <a name="line-qty"></a>Get Line Quantity Details

**API:** ExportMI/Select

Query : ICWHLO,ICWHSL,ICBANO,ICCAMU,ICPUNO,ICPNLI,ICPNLS,ICSUDO,ICREPN,ICPUOS,ICNEAC,ICRPQA,ICRPQT,ICTRDT,ICRESP,ICOEND from MPLIND where ICWHLO = '%@' and ICREPN = '%@' 

### <a name="container-info"></a>Get Container Info

**API:** MMS200MI/GetItmWhsBasic

Input field required:

| **Field** | **Description**              |
| --------- | ---------------------------- |
| ITNO      | Purchase Order's Item Number |
| WHLO      | Purchase Order warehouse     |

### <a name="reject-reasons"></a>Get Reject Reasons

**API:** CRS175MI/LstGeneralCode

Input field required:

| **Field** | **Description** |
| --------- | --------------- |
| STCO      | Constant value  |

### <a name="retr-loc"></a>Validate Location

**API:** MMS010MI/GetLocation

Input field required:

| **Field** | **Description** |
| --------- | --------------- |
| WHLO      | Warehouse       |
| WHSL      | Warehouse       |

### <a name="inspect"></a>PO Inspection

**API:** PPS310MI/QualityInspPO

Input field required:

| **Field** | **Description**           |
| --------- | ------------------------- |
| REPN      | Receving number           |
| RESP      | Responsible               |
| QCRA      | Quality Inspection Result |
| AQTY      | Approved Quantity         |
| AWHS      | Approved Location         |
| OEND      | Flagged as Completed      |
| AREM      | Approved Remark           |
| ABAN      | Approved Lot Number       |
| CAMU      | Container                 |
| SCRE      | Rejection Reason          |
| RJQA      | Rejected Quantity         |
| RWHS      | Reject Location           |
| RBAN      | Reject Lot Number         |
| RREM      | Reject Remark             |



# **<a name="wrk"></a>Workflow, Screen Layouts & API Logic**

### <a name="settings"></a>Settings:

The current warehouse selection can be made using the settings icon on top right corner of the screen.

<img src="../images/PI/settings.png" alt="settings" style="zoom:50%;" />



### <a name="po"></a>Purchase Order #:

/*Image*/

On Entering/Scanning number it will be validated using [GetHeadMI](#validate-po). If the PO's status is greater that 50 and the goods receiving methods specifed is of Quality Inspect type then the PO is valid to proceed to get line items.

### <a name="lines"></a>Line Items:

The List of line items will be fetched from [Get Line](#line-items).

/*Image*/

The line items details can be viewed by scrolling horiozontally.

### <a name="line-details"></a>Inspecting Line Item:

After tapping on a line item it can be inspected by providing required values for the attributes like, loaction, rejected reason, reject location lot number etc.

/*Image*/

### <a name="qi-res"></a>Choosing QI Result

QI results can be chosen from the available options:-

- Partially reported approved quantity.
- Fully approved.
- Approved with remarks.
- Partailly rejected.
- Rejected.

/*Image*/

Each QI options will have different details required for submitting the inspection.

### <a name="fill-details"></a>Fill Required Details

Choose the location code for approved quantiy from the drop down, enter/scan approved quantity and enter the remarks.

/*Image*/

### <a name="confirm-demo"></a>Submit the Inpection

If all details were entered a slider will be shown, on slide to confirm the item inspection details will be submitted via [M3 inspect](#inspect).

/*Image*/

# **<a name="m3sample"></a>M3 sample workflow**

- This section describes the Pick Reporting workflow in M3 to create purchase order. The workflow can have variations depending on your current order processing- and dispatch settings.

  The current warehouse selection can be made using the settings icon on top right corner of the screen.

  ### <a name="crt-po"></a>Create Purchase order PPS200

  - Purchase order can be created in PPS200 by clicking [+] button.
  - Enter supplier, order type and Req delivery date.
  - Supplier will be defined in CRS620 and customer will be defined in CRS610
  - Add line items for the order and specify the item quantity, price and goods receiving method
  - Complete the order creation. It will be in status 15 - ready to send

  The Goods Receving methods will be defined in PPS345, Select Method type having quality inspect.

  ### <a name="receive-po"></a>Receive the order in PPS300

  - Enter the created purchase order number in the PPS300 panel.
  - Listed line items have to be received enter the received quantity and receive the items.
  - After successful receiving of order the status will be 50- Goods received.

**Note:** Orders with status 50 or above will be recognized by the Mobile App.

