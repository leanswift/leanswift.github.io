

# User Guide - Proof Of Delivery

<img src="../../../images/banner-mobilefirst-cloudsuite.jpg" alt="banner" style="zoom:100%;" />



# Table of contents

- **[About this guide](#about-this-guide)**
  - [Intended Audience](#intended-audience)
    - [Proof of Delivery standard functionality](#std-func)
- **[Workflow, Screen Layouts & API Logic](#wrk)**
  - [Capture Driver Signature](#driver-sign)
  - [Truck Selection](#truckDeliSel)
  - [Delivery Line Items Details](#deliDetail)
  - [Capture damaged items](#editDetail)
  - [Receive Delivery](#ReceiveDel)
    - [Deliver Approval](#delApprove)
    - [Emailing POD Document](#emailPOD)
    - [Return Order](#returnOrder)



# <a name="about-this-guide"></a>About this guide

### <a name="intended-audience"></a>Intended Audience

MobileFirst Configuration User Guide provides guidance for LeanSwift customers and consultants regarding understanding the basic concept, functionality, and configuration of the Proof Of Delivery Standard App. Further information about MobileFirst standard applications can be found at [www.inform3marketplace.com](http://www.inform3marketplace.com).

#### **<a name="std-func"></a>Proof of delivery standard functionality**

The Proof of delivery for Infor M3 and make it possible for your customers to sign for deliveries electronically on a mobile device. The signed confirmation will be directly archived in IDM.

##### Features Included:-

- Retrieve and display the status of a delivery
- Capture user signature
- Generate a PDF that includes items and quantities delivered
- Infor Document Management archiving support



# **<a name="wrk"></a>Workflow, Screen Layouts & API Logic**

### <a name="driver-sign"></a>Capture Driver Signature

The driver's name and signature are captured on this screen. This is a one-time entry, In case of editing the driver information, tap the Sign button on the top right corner.

On Entering name and signature the press the tick button to save the details and proceed.

<img src="../images/POD/POD1.gif" alt="settings" style="zoom:100%;" />



### <a name="truckDeliSel"></a>Truck Selection

After successful entry of driver details, the truck list is fetched from M3.

The Truck number is represented with the warehouse and the agreement number. Each truck in the list contains delivery mapped to it separately. On selecting the truck in the truck list all its mapped delivery details will be fetched and shown.

The selection of the truck is saved and it will be the default selection whenever the module launches, in case of switching to a different truck tap the back button from the delivery list and select a new truck from the truck list

<img src="../images/POD/POD2.gif" alt="settings" style="zoom:100%;" />

Each truck will have different deliveries mapped to it. Each delivery is displayed with all the basic delivery details. The delivery list can be sorted based on its departure date.

### <a name="deliDetail"></a>Delivery Line Items Details

After choosing the delivery all the Line items under the delivery were listed, the ordered quantity and delivered quantity field will be shown for each line item.

Users can accept the delivery by tapping the accept button on the top right corner or in case of any issue with the delivered items they can edit the delivered quantities and if the delivered quantity is less than the ordered quantity the comments should be mandatory if not it’s optional.

<img src="../images/POD/POD3.gif" alt="settings" style="zoom:100%;" />

### <a name="editDetail"></a>Capture damaged items

The damaged items image can be captured by tapping the capture button provided near the accept button.

It is recommended that capturing less than 6 images for reporting damaged items. Since the these images will be attached with the signed ticket and archived in IDM.

<img src="../images/POD/POD4.gif" alt="settings" style="zoom:100%;" />



### <a name="ReceiveDel"></a>Receive Delivery

On accepting the delivery line items press accept to proceed to receive the delivery, Enter the receiver name and the receiver signature. Slide to confirm receiving the delivery. The final process of Proof of delivery contains three major tasks.

#### <a name="delApprove"></a>Delivery Approval

When slide to confirm is done. whenever the deliver line items has change in quantites delivered the changes is notified to M3 and then the Delivey approval is called from mobile.

#### <a name="emailPOD"></a>Emailing POD Document

The executed delivery order with its line items, comments and attached images comprosing of these items a PDF document will be created. Both the driver and receiver signature will be digitally signed. A mail composer screen will be shown with the customer mail as To Address and POD document as attachement. User can edit all the information presented or proceed by tapping send button to send the email confirmation. This signed document will get uploaded to IDM and archived for future reference.

#### <a name="returnOrder"></a>Return Order

If the delivery approved with discrepancy in the line items quantites, Return order will be created for such line items. A Customer order is created in M3 with the line items which has shorted quantites.



<img src="../images/POD/POD5.gif" alt="settings" style="zoom:100%;" />



On completion of all above process the final screen shows all the details of the executed process which shows the delivery completion status, the return order details and the Email confirmation status.

Tapping delivery success Tick / Fail button to return back to the Delivery list page. In case of Ship ticket missing in IDM, users will be asked to capture ship ticket if available in the delivery location or they can skip IDM process.



