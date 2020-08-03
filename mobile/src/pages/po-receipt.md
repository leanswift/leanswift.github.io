

# User Guide - PO Receipt

<img src="../../../images/banner-mobilefirst-cloudsuite.jpg" alt="banner" style="zoom:100%;" />



# Table of contents

- **[About this guide](#about-this-guide)**
  - [Intended Audience](#intended-audience)
    - [PO Receipt standard functionality](#std-func)
- **[M3 Setup](#m3-setup)**
  - [Set Pick Team](#set-pick-team)
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



# **<a name="wrk"></a>M3Setup**

### <a name="set-pick-team"></a>Set Pick Team

<!-- Setting up HPTEAM for the users -->



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

