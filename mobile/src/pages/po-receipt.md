

# User Guide - PO Receipt

<img src="/Users/tamilselvan/Documents/Docs/MFCEDOCS/Docs/images/banner-mobilefirst-cloudsuite.jpg" alt="banner" style="zoom:100%;" />



# Table of contents

- **[About this guide](#about-this-guide)**
  - [Intended Audience](#intended-audience)
    - [PO Receipt standard functionality](#std-func)
- **[Technical details](#tech-details)**
  - [List Warehouse](#list-whsl)
  - [Validate PO #](#validate-po)
  - [Get Line Items](#line-items)
  - [Get Line Details](#line-details)
  - [Get Container Info](#container-info)
  - [Get Item Warehouse Balance](#balanceid)
  - [Validate Put-Away Location](#retr-loc)
  - [Get Package in Stock](#pckg-stock)
  - [Add Package in Stock](#add-pckg)
  - [PO Receipt](#receipt)
- **[Workflow, Screen Layouts & API Logic](#wrk)**
  - [Settings](#settings)
  - [Purchase order number](#po)
  - [Line Items](#lines)
  - [Line Item Details](#line-details)
    - [Fill details](#fill-details)
  - [Report Item](#confirm-details)
- **[M3 sample workflow](#m3sample)**
  - [Create Purchase order PPS200](#crt-po)



# <a name="about-this-guide"></a>About this guide

### <a name="intended-audience"></a>Intended Audience

MobileFirst Configuration User Guide provides guidance for LeanSwift customers and consultants regarding understanding the basic concept, functionality and configuration of the PO Receipt Standard App. Further information about MobileFirst standard applications can be found at [www.inform3marketplace.com](http://www.inform3marketplace.com).   

#### **<a name="std-func"></a>PO Receipt standard functionality**

The purchase order receipt for Infor M3 provides the ability to receive purchase order into a warehouse.

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

**API:** PPS200MI/LstLine

Input field required:

| Field | Description    |
| ----- | -------------- |
| PUNO  | Purchase Order |
| CONO  | Company        |

Select the line item from the list. Depending on the PO's order type the items will be under single put away or two step put away.

### <a name="line-details"></a>Get Line Item Details

**API:** MMS200MI/Get

Input field required:

| Field | Description |
| ----- | ----------- |
| ITNO  | Item Number |
| LNCD  | Language    |

### <a name="container-info"></a>Get Container Info

**API:** MMS200MI/GetItmWhsBasic

Input field required:

| **Field** | **Description**              |
| --------- | ---------------------------- |
| ITNO      | Purchase Order's Item Number |
| WHLO      | Purchase Order warehouse     |
| CONO      | Company                      |

### <a name="balanceid"></a>Get Item Warehouse Balance

**API:**MMMS235MI/GetItmLot

Input field required:

| **Field** | **Description** |
| --------- | --------------- |
| ITNO      | Item number     |
| BANO      | Lot Number      |

### <a name="retr-loc"></a>Validate Put-Away Location

**API:**MMS010MI/GetLocation

Input field required:

| **Field** | **Description** |
| --------- | --------------- |
| WHLO      | Warehouse       |
| WHSL      | Warehouse       |
| CONO      | Company         |

### <a name="pckg-stock"></a>Get Package in Stock

**API:**MMS470MI/GetPackageStk

Input field required:

| **Field** | **Description** |
| --------- | --------------- |
| PANR      | Package number  |
| SSCC      | SSCC Number     |
| CONO      | Company         |

### <a name="add-pckg"></a>Add Package in Stock

**API:**MMS470MI/AddPackStk

Input field required:

| **Field** | **Description** |
| --------- | --------------- |
| WHLO      | Warehouse       |
| PANR      | Package number  |
| SSCC      | SSCC Number     |
| PACT      | Packaging       |
| CONO      | Company         |

### <a name="receipt"></a>PO Receipt

**API:**PPS310MI/QualityInspPO

Input field required:

| **Field** | **Description**              |
| --------- | ---------------------------- |
| CONO      | Company                      |
| TRDT      | Transaction date             |
| RESP      | Responsible                  |
| PUNO      | Purchase order number        |
| PNLI      | Purchase order number line   |
| RVQA      | Received quantity            |
| WHSL      | Location                     |
| BANO      | Lot number                   |
| CAMU      | Container number             |
| PNLS      | Purchase order number status |
| OEND      | Finish mark                  |
| SUDO      | Delivery note                |
| PRDT      | Manufacturing date           |



# **<a name="wrk"></a>Workflow, Screen Layouts & API Logic**

### <a name="settings"></a>Settings:

The current warehouse can be selected from tapping the settings icon on top right corner.

<img src="../images/PORE/settings.png" style="zoom:40%;" />



By default the logged in user default warehouse will be selected.

### <a name="po"></a>Purchase #:

In the Purchase order number field enter manually using keyboard or scan from inbuilt camera.

/*Image*/

PO number entered will be sent to M3 to [head Info](#validate-po) and head details will be retrieved.

### <a name="lines"></a>Line Items:

On valid PO its line items will be fetched from [get line Items](#line-items).

/*Image*/	

### <a name="line-details"></a>Line Item Details:

On selecting a line item from the list its details will be fetched from [details](#line-details) and also line will be checked for container controller from [container Info](#container-info) or lot controllerd and the lot details will be fetched from [lot info](#balanceid).

/*Image*/

### <a name="fill-details"></a>Fill details:

The location can be entered and this will be validated against M3 using [valid location](#retr-loc). The quantity can be either scanned or entered manually using key board.

/*Image*/

### <a name="confirm-details"></a>Submit for Receipt

All the entered values will be validated and in case of container methods item then the packaging is checked using [get package](#pckg-stock) and if there is no package then the item will be added to a package using [add pack](#add-pckg).

/*Image*/

Finally the PO item will be reported for receipt using [receipt](#receipt) Service in M3.



# **<a name="m3sample"></a>M3 sample workflow**

This section describes the Pick Reporting workflow in M3 to create purchase order. The workflow can have variations depending on your current order processing- and dispatch settings.

The current warehouse selection can be made using the settings icon on top right corner of the screen.

### <a name="crt-po"></a>Create Purchase order PPS200

- Purchase order can be created in PPS200 by clicking [+] button.
- Enter supplier, order type and Req delivery date.
- Supplier will be defined in CRS620 and customer will be defined in CRS610
- Add line items for the order and specify the item quantity, price and goods receiving method
- Complete the order creation. It will be in status 15 - ready to send.

