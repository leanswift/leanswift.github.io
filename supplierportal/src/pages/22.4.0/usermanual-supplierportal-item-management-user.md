![Supplier portal banner](../../../../images/banner-supplier-portal.jpg)

# Version 22.4.0 - User Manual - Supplier Item Management - User

# Table of contents

<div id=toc></div>

- [Supplier Item Management](#supplier-item-management)
 	- [My Items](#my-items)	 
  - [Create New](#create-new)	 
  - [Item Update](#item-update)
  - [Stock Update](#stock-update)
  - [Submitted Status](#submitted-status)

# User Manual - Supplier Item Management

<div id = "Supplier Item Management"> </div> 

# Supplier Item Management

This will be an Add-on to Supplier Portal. With this Supplier can create a new supplier item/ M3 Item, Update item and Connect supplier item to existing M3 item.
M3 Buyer decides to approve or reject the above requests from the supplier based on the real time data provided by him.

## My Items

To enable My Items feature in Supplier Portal, Item Management add on should be installed.
My Items has below submenus,
1.	Submitted status
2.	Create New
3.	Item Update
4.	Stock Update


<kbd>
<kbd><img alt="Supplier_Invite" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/Menus.png"></kbd>
</kbd>


## Create New

Supplier can create a new Supplier item or connect Supplier Item with existing M3 item.

All input fields are mandatory in **Basic and Purchase information** section. 

Supplier must provide **Supplier Item Number, Supplier Item Name and Supplier Item Description** details under Basic information.

Valid information must be provided for **Purchase Price, Purchase Price Qty, Minimum Order Quantity, Order Multiple, Country of Origin, Supplier Stock Qty, Valid From and Valid To** under Purchase information.


<kbd>
<kbd><img alt="CreateNewForm" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/CreateNewForm.png"></kbd>
</kbd>


Once the request is submitted, page navigates to submitted status page with success message as below. Initially, item creation request will be in **‘Submitted’** status.


<kbd>
<kbd><img alt="CreateNewItemStatus" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/CreateNewItemStatus.png"></kbd>
</kbd>


Verification Task will be assigned to Buyer with all Item Details submitted by Supplier for approval.

Buyer may approve, connect or reject the approval request

If approved, new item will be created in M3 and item will be connected to the supplier.   	
  
 ->  The status changes to **‘Created’**.
  
If rejected, item will not be created in M3
	
  -> The status changes to **‘Rejected’**.
  
If Buyer Connects the existing M3 item with supplier, 
  
  -> The status changes to **‘Connected’**.
  
If Item creation process fails in M3,
  
  -> The status changes to **‘Failed’**.
  
Supplier will receive Bell Notification for each item status update with error message or notes sent by Buyer.

Supplier can also create new item with Additional Information attributes. These input fields will be configured by portal admin.
Additional Information fields are optional.


<kbd>
<kbd><img alt="CreateNewwithAdditionalInfo" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/CreateNewwithAdditionalInfo.png"></kbd>
</kbd>


<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

## Item Update

Supplier can update existing supplier item created via portal or Infor M3.

Items are searched using Supplier Item Number. Search opens the editable form with all details.

Item with status **Submitted, Failed and Rejected** cannot be updated.


<kbd>
<kbd><img alt="ItemUpdateRejectedStatus" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/ItemUpdateRejectedStatus.png"></kbd>
</kbd>



<kbd>
<kbd><img alt="SupplierItemUpdateSearch" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/SupplierItemUpdateSearch.png"></kbd>
</kbd>



<kbd>
<kbd><img alt="SupplierItemUpdateForm" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/SupplierItemUpdateForm.png"></kbd>
</kbd>


Once the page is submitted with additional information (if required), page navigates to submitted status with success message and Item status will be in **‘Submitted’** status.


<kbd>
<kbd><img alt="ItemUpdateMessage" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/ItemUpdateMessage.png"></kbd>
</kbd>


Verification Task is assigned to Buyer with item details submitted by supplier for approval.

-> If Buyer approves, item details will be updated in M3 and status changes to **‘Updated’**.

-> If Buyer rejects, status changes to **‘Rejected’**.

-> If Item update process in M3 fails, the status changes to **‘Failed’** with error message displayed in bell notification.

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

## Stock Update

Supplier can update stock of supplier item created via portal or Infor M3, by searching ‘Supplier Item Number’.

Stock cannot be updated for Item with status **Submitted, Failed and Rejected**.

Supplier Item Number Search will display current stock (existing stock) and revised stock fields.

Revised Stock of the supplier item is updated in RealTime.



<kbd>
<kbd><img alt="StockUpdate" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/StockUpdate.png"></kbd>
</kbd>



<kbd>
<kbd><img alt="StockUpdateMessage" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/StockUpdateMessage.png"></kbd>
</kbd>



<kbd>
<kbd><img alt="StockAfterUpdate" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/StockAfterUpdate.png"></kbd>
</kbd>


<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

## Submitted Status

This page displays all item requests with respective status.

Items can be filtered using **Supplier Item number, Supplier Item Name, Supplier item Description and Status**.


<kbd>
<kbd><img alt="CreateNewForm" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/SubmittedAllstatus.png"></kbd>
</kbd>


 **Status and Actions**

**Submitted** -> When Item Creation request is submitted. Supplier can view the item details by clicking Eye icon.

**Created** -> When Item Creation request is approved by Buyer. Supplier can view the item details and upload image for Item.

**Connected** -> When Item Creation request is connected by Buyer with existing M3 Item. Supplier can view the item details and upload image for Item.

**Updated** -> When Item Update request is approved by Buyer. Supplier can view the item details and upload image for Item.

**Rejected** -> When Item Creation/ Item Update request is rejected by Buyer. Supplier can edit and re-submit the item request. Verification Task is assigned to the Buyer for approval.

**Failed** -> When Item Creation/ Item Update request process failed in Infor M3. Supplier can edit and re-submit the item request. Verification Task is assigned to Buyer for approval.

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

## Item Image Upload

Item Image can be uploaded by clicking **Camera** Icon for Item request with status as **Created, Connected and Updated** in the Submitted Status page.



<kbd>
<kbd><img alt="ImageUpload" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/ImageUpload.png"></kbd>
</kbd>



<kbd>
<kbd><img alt="ImageUploadMesage" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/ImageUploadMesage.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>
