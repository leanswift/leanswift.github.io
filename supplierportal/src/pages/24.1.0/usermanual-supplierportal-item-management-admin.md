<img alt ="Supplier Portal Banner" src="../../images/pwa/SupplierPortal_Banner.png">

# Version 24.2.0 - User Manual - Supplier Item Management - Admin

<div id=toc></div>

# Table of contents

- [Supplier Item Management](#supplier-item-management)
  - [Item Management](#item-management)	 
  - [General Configuration](#general-configuration)	 
  - [Additional Attribute Mapping](#additional-attribute-mapping)
  - [Workflow Configuration](#workflow-configuration)
  - [Workflow Distribution](#workflow-distribution)
  - [Retrieve Configuration](#workflow-distribution)
- [Buyer Approval and Rejection Process in Mingle Portal](#buyer-approval-and-rejection-process-in-mingle-portal)

# User Manual - Supplier Item Management - Admin

<div id = "Supplier Item Management"> </div> 

# Supplier Item Management

This will be an Add-on to Supplier Portal. With this Supplier can create a new supplier item/ M3 Item, Update item and Connect supplier item to existing M3 item.

M3 Buyer decides to approve or reject the above requests from the supplier based on the real time data provided by him.


## Item Management 

Item Management configuration supports Multi Website scope.

Navigate to **Leanswift-> Supplier Portal-> Item Management**. 

Existing Supplier Items from M3 is imported using cron to Database during Supplier Registration.This can be configured in Defalut configuration.

<kbd>
<kbd><img alt="DefaultConfig" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1973/supplierportal/src/images/usermanual/supplier-item-management/DefaultConfig.png"></kbd>
</kbd>



Then Switch to respective website configured.

There are three sections
1. General Configuration
2. Workflow Configuration
3. Retrieve Configuration


<kbd>
<kbd><img alt="AdminMenu" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/AdminMenu.png"></kbd>
</kbd>



## General Configuration


<kbd>
<kbd><img alt="ItemManagement1" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/ItemManagement1.png"></kbd>
</kbd>


**Item Type:** Item will be created based on the Item type selected. Item Type is retrieved from program CRS045 (Item Type. Open)
Item type must have “Template item” and “Override with manually entered item number” fields enabled.API MMS200MI/AddItmViaItmTyp(Add Item Via Item Type) is used to create item in M3 program MMS001(Item.Open). 

**Creation Responsible:** Entered M3 User is the responsible person for the Item Creation. The value given here gets updated in the RESPONSIBLE field for the newly created item in MMS001 and PPS040.

**Lowest permitted quality Inspection:** The selected Quality Inspection level chosen here will be updated in the PPS040 (Supplier.Connect Item) for the newly created item.

**Inspection Text:** Inspection Text is mandatory for all quality Inspection, except “No Quality Inspection.” Text is prepopulated based on the selection. Portal Admin can also overwrite the existing text.

**Quality Class:** Selected Quality Class from drop down will be updated in the PPS040 (Supplier.Connect Item) for the newly created item.

Above configured values will be displayed along with Basic and Purchase Information details in the Verification Task assigned to Buyer.


<kbd>
<kbd><img alt="VerificationTask" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/VerificationTask.png"></kbd>
</kbd>


Verification Task has Override numbering Series toggle button. This is used to generate Item Number for Item Creation in MMS001. Buyer can decide whether to enable/disable override numbering series before approving/connecting the new item request.

By default, **override numbering series is Disabled**,

Numbering Rule configured for Item Type in CRS040 (Item Type. Open) is used for Item creation.

If **override numbering series is Enabled**, 

Retrieve Next Item number API is used based on the Nuber Type and Number series. By default, Number Type ‘9’ is used and Number series ‘A’ is used from program CRS165 (Number Series. Open).Number series can be updated by Buyer in the verification task.


<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>


## Additional Attribute Mapping 


<kbd>
<kbd><img alt="AdditionalAttributesMapping" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/AdditionalAttributesMapping.png"></kbd>
</kbd>


Attributes mapped here will appear in the **‘Create New’** form and **‘Update Item’** form under Additional Information section.

M3 Attributes are fetched from PPS040 (AddItemSupplier and UpdateItemSupplier)

/apiTxnList/MRS001MI/LstFields,{"MINM":"PPS040MI","TRNM":"AddItemSupplier}	/apiTxnList/MRS001MI/LstFields, MINM":"PPS040MI","TRNM":"UpdItemSupplier"}

All M3 Attributes are retrieved exclusive of mandatory fields in Create New form.

M3 Attribute Code is a readable M3 Field code.

Custom Label is the field name for additional attributes, which replaces M3 Attribute label in Create New form. If value is empty, then M3 attribute field name will appear as default in Create New form. 

Make sure Mapped Attributes are added in the workflow Input parameters manually.

Attributes Mappings can be added and removed.           


<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>


## Workflow Configuration


<kbd>
<kbd><img alt="Workflow" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/Workflow.png"></kbd>
</kbd>


**Item Creation Workflow**: Based on the workflow the item creation process will be happen. When item created Supplier_Portal_Item_Creation workflow will be triggered. Buyer can Approve or Reject or connect the item to exiting M3 item. 

**Item Update Workflow**: Based on the workflow the item update will be happen. When any item is updated by the supplier then Supplier_Portal_Supplier_Connect_Item_Updation workflow will be triggered. The buyer can Approve or Reject.  


<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>


## Workflow Distribution

**User Name**: The workflow task will be sent to the configured M3 User Name. 

**User Group**: The workflow task will be sent to the configured M3 User Group. 


<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>


## Retrieve Configuration

<kbd>
<kbd><img alt="RetrieveConfig" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/RetrieveConfig.png"></kbd>
</kbd>

Fetch Configuration will fetch the configurations from M3.

Export MI is used to fetch the list for Item Type, Additional Attribute Mapping, Quality Class, and Country of Origin (Create New form) from M3.

1. **Item Type** -> Item Type will be fetched from M3 with the condition that Template Item should be configured and Override with manually entered item number should be checked in CRS040 Program.
Transaction: /apiTxnList/EXPORTMI/Select/MITTTY ,
[{"transaction":"Select","record":{"SEPC":";","HDRS":"1","QERY":"TYTX15, TYITTY from MITTTY where TYNUMR <> “ and TYTPLI <> '' and TYOVIT = 1"}}]}

2. **Country of origin** -> List of countries from program CRS045 are fetched. 
Transaction: /apiTxnList/EXPORTMI/Select/CSYTAB,
[{"transaction":"Select","record":{"SEPC":";","HDRS":"1","QERY":"CTSTKY, CTTX15 from CSYTAB where CTSTCO = CSCD"}}]}

3. **Additional Attribute Mapping** -> Attributes from PPS040 will be fetched.
Transaction: /apiTxnList/MRS001MI/LstFields,
[{"transaction":"LstFields","record":{"MINM":"PPS040MI","TRNM":"AddItemSupplier","TRTP":"I"}}]}
Transaction: /apiTxnList/MRS001MI/LstFields,
[{"transaction":"LstFields","record":{"MINM":"PPS040MI","TRNM":"UpdItemSupplier","TRTP":"I"}}]}

4. **Quality Class** -> Quality Class list will be fetched from PPS020 (Quality Class)
Transaction: /apiTxnList/EXPORTMI/Select/CSYTAB,
[{"transaction":"Select","record":{"SEPC":";","HDRS":"1","QERY":"CTSTKY, CTTX15 from CSYTAB where CTSTCO = QUCL"}}]}

Buyer can update below values during approval task triggered for Item creation request submitted by the supplier.
1. M3 Item Type
2. Lowest Permitted Quality Inspection
3. Inspection Text
4. Creation Responsible
5. Quality Class


<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>


# Buyer Approval and Rejection Process in Mingle Portal

Buyer is assigned with verification task for item creation/ update submitted by supplier for approval. 

Login to **Mingle Portal** and click **Message** icon. 

Then navigate to **Task** option which will display list of tasks and notifications assigned to Buyer. 


<kbd>
<kbd><img alt="ListofTasks" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/ListofTasks.png"></kbd>
</kbd>


Click **Show Details** of the assigned task which displays all details. 


<kbd>
<kbd><img alt="CreateNewTaskVerify" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/CreateNewTaskVerify.png"></kbd>
</kbd>


Buyer must verify all details and can update writable field values if required. Updated Task notes updated will be notified to Supplier.

Then Buyer makes decision either to Approve or Reject or Item Connect the assigned task. 

## **Item Creation/Connect Task Actions**

### **Approve**

If Buyer approves the task, then notification is triggered with status. New M3 Item is created in MM001 and connected with supplier item in PPS040. 


<kbd>
<kbd><img alt="CreatedSuccess" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/CreatedSuccess.png"></kbd>
</kbd>


<kbd>
<kbd><img alt="CreatedTaskStatus" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/CreatedTaskStatus.png"></kbd>
</kbd>



### **Item Connect**

If Buyer decides to Connect the supplier item with existing M3 Item, then another task is assigned to enter the existing M3 Item number in the field M3 Item Number. Complete the task by clicking ‘Done’ and notification is received. 

<kbd>
<kbd><img alt="M3ItemTask" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/M3ItemTask.png"></kbd>
</kbd>

<kbd>
<kbd><img alt="AddM3ItemTask" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/AddM3ItemTask.png"></kbd>
</kbd>


<kbd>
<kbd><img alt="ConnectedTask" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/ConnectedTask.png"></kbd>
</kbd>


<kbd>
<kbd><img alt="ConnectedStatus" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/ConnectedStatus.png"></kbd>
</kbd>

### **Reject**

If Buyer decides to reject the submitted details, then notification is triggered with status. 

<kbd>
<kbd><img alt="RejectedTask" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/RejectedTask.png"></kbd>
</kbd>


<kbd>
<kbd><img alt="RejectedStatusTask" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/RejectedStatusTask.png"></kbd>
</kbd>



## **Item Update Task Actions**

 Buyer must verify details and choose to approve or reject the task. 

<kbd>
<kbd><img alt="UpdateItemTask" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/UpdateItemTask.png"></kbd>
</kbd>


<kbd>
<kbd><img alt="UpdateItemTaskDetails" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/UpdateItemTaskDetails.png"></kbd>
</kbd>


### **Approve**

If Buyer approves the task, then supplier item deatils are updated in PPS040 and notification is received as below. 

<kbd>
<kbd><img alt="UpdateItemStatusTask" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/UpdateItemStatusTask.png"></kbd>
</kbd>


<kbd>
<kbd><img alt="UpdateItemStatus" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/UpdateItemStatus.png"></kbd>
</kbd>



### **Reject**

If Buyer rejects the submitted details, then notification is triggered. 

<kbd>
<kbd><img alt="ItemUpdateRejectedTask" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/ItemUpdateRejectedTask.png"></kbd>
</kbd>


<kbd>
<kbd><img alt="UpdateItemRejectedStatus" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/UpdateItemRejectedStatus.png"></kbd>
</kbd>


## **Failed Status for Item Creation and Update Task** 

When Item Creation or Connection or Update process fails in M3 then Buyer is notified with error message. 


<kbd>
<kbd><img alt="ItemFailedTask" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/ItemFailedTask.png"></kbd>
</kbd>



<kbd>
<kbd><img alt="ItemFailedstatus" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/ItemFailedstatus.png"></kbd>
</kbd>

Add Item Error Message and Update Item Error Message displays error message thrown by Infor M3 API's.

<kbd>
<kbd><img alt="ItemFailedErrorMessage" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/ItemFailedErrorMessage.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>
