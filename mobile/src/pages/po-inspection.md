

# User Guide - PO Inspection

<img src="../../../images/banner-mobilefirst-cloudsuite.jpg" alt="banner" style="zoom:100%;" />



# Table of contents

- **[About this guide](#about-this-guide)**
  - [Intended Audience](#intended-audience)
    - [PO Inspection standard functionality](#std-func)
- **[M3 Setup](#m3-setup)**
  - [Set Pick Team](#set-pick-team)
- **[Workflow, Screen Layouts & API Logic](#wrk)**
  - [PO Number](#po-num)
  - [Inspecting Line Item & Choosing QI Result](#qi-res)
  - [Submit the Inpection](#confirm-demo)
- **[M3 sample workflow](#m3sample)**
  - [Create Purchase order PPS200](#crt-po)
  - [Receive the order in PPS300](#receive-po)



# <a name="about-this-guide"></a>About this guide

### <a name="intended-audience"></a>Intended Audience

MobileFirst Configuration User Guide provides guidance for LeanSwift customers and consultants regarding understanding the basic concept, functionality, and configuration of the PO Inspection Standard App. Further information about MobileFirst standard applications can be found at [www.inform3marketplace.com](http://www.inform3marketplace.com).

#### **<a name="std-func"></a>PO Inspection standard functionality**

The PO Inspection for Infor M3 provides for the ability to inspect the items received via M3 Purchase Orders into a warehouse. In M3 terms, it is the ability to inspect a PO.



# **<a name="wrk"></a>M3Setup**

### <a name="set-pick-team"></a>Set Pick Team



# **<a name="wrk"></a>Workflow, Screen Layouts & API Logic**

### <a name="po-num"></a>PO Number:

The current warehouse selection can be made using the settings icon on the top right corner of the screen.

On Entering/Scanning number it will be validated from M3. If the PO's status is greater than 50 and the goods receiving methods specified are of Quality Inspect type then the PO is valid to proceed to get line items.

The List of line items will be fetched from M3. Item details can be viewed by scrolling horizontally.

<img src="../images/PI/1.gif" alt="settings" style="zoom:100%;" />



### <a name="qi-res"></a>Inspecting Line Item & Choosing QI Result

After tapping on a line item it can be inspected by providing required values for the attributes like location, rejected reason, reject location lot number, etc.

QI results can be chosen from the available options:-

- Partially reported approved quantity.
- Fully approved.
- Approved with remarks.
- Partially rejected.
- Rejected.

<img src="../images/PI/2.gif" alt="settings" style="zoom:100%;" />

Each QI option will have different details required for submitting the inspection.

### <a name="confirm-demo"></a>Submit the Inpection

Choose the location code for the approved quantity from the drop-down, enter/scan approved quantity, and enter the remarks.

If all details have entered a slider will be shown, on sliding the slide to confirm the item inspection details will be submitted in M3.

<img src="../images/PI/3.gif" alt="settings" style="zoom:100%;" />

# **<a name="m3sample"></a>M3 sample workflow**

This section describes the Pick Reporting workflow in M3 to create a purchase order. The workflow can have variations depending on your current order processing- and dispatch settings.

The current warehouse selection can be made using the settings icon on the top right corner of the screen.

- ### <a name="crt-po"></a>Create Purchase order PPS200

  - Purchase order can be created in PPS200 by clicking [+] button.
- Enter supplier, order type and Req delivery date.
  - Supplier will be defined in CRS620 and customer will be defined in CRS610
- Add line items for the order and specify the item quantity, price and goods receiving method
  - Complete the order creation. It will be in status 15 - ready to send
  
  The Goods Receving methods will be defined in PPS345, Select Method type having quality inspect.
  
- ### <a name="receive-po"></a>Receive the order in PPS300

  - Enter the created purchase order number in the PPS300 panel.
  - Listed line items have to be received enter the received quantity and receive the items.
  - After successful receiving of order the status will be 50- Goods received.

**Note:** Orders with status 50 or above will be recognized by the Mobile App.

