![Supplier portal banner](../../../../images/banner-supplier-portal.jpg)

# Version 22.4.0 - User Manual - Supplier Item Management - Admin

# Table of contents

<div id=toc></div>

- [Supplier Item Management](#supplier-item-management)
 	- [Item Management](#item-management)	 
  - [General Configuration](#general-configuration)	 
  - [Additional Attribute Mapping](#additional-attribute-mapping)
  - [Workflow Configuration](#workflow-configuration)
  - [Workflow Distribution](#workflow-distribution)
  - [Retrieve Configuration](#workflow-distribution)

# User Manual - Supplier Item Management - Admin

<div id = "Supplier Item Management"> </div> 

# Supplier Item Management

This will be an Add-on to Supplier Portal. With this Supplier can create a new supplier item/ M3 Item, Update item and Connect supplier item to existing M3 item.

M3 Buyer decides to approve or reject the above requests from the supplier based on the real time data provided by him.


## Item Management 

Item Management configuration supports Multi Website scope.

Navigate to **Leanswift-> Supplier Portal-> Item Management**. Then Switch to respective website configured.

There are three sections
1.	General Configuration
2.	Workflow Configuration
3.	Retrieve Configuration


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

## Workflow Configuration


<kbd>
<kbd><img alt="Workflow" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/Workflow.png"></kbd>
</kbd>


**Item Creation Workflow:** Name of the ION Workflow should be configured for New Item Creation process. This workflow is triggered when ‘Create New’ form is submitted. 

**Item Update Workflow:** Name of ION Workflow should be configured for Item Update process. This workflow is triggered when existing item update form is submitted.

## Workflow Distribution

**User Name:** Only one M3 UserName must be configured, and this field is mandatory. Verification Task is assigned to the configured username for approval when item creation or update request is submitted.

**User Group:** M3 User Group must be configured, and this field is optional. Verification Task is sent to all the users in the group configured for approval when item creation or update request is submitted.

## Retrieve Configuration

<kbd>
<kbd><img alt="RetrieveConfig" src="https://raw.githubusercontent.com/leanswift/leanswift.github.io/SP-1640/supplierportal/src/images/usermanual/supplier-item-management/RetrieveConfig.png"></kbd>
</kbd>

Fetch Configuration will fetch the configurations from M3.

Export MI is used to fetch the list for Item Type, Additional Attribute Mapping, Quality Class, and Country of Origin (Create New form) from M3.

1.	**Item Type** -> Item Type will be fetched from M3 with the condition that Template Item should be configured and Override with manually entered item number should be checked in CRS040 Program.
Transaction: /apiTxnList/EXPORTMI/Select/MITTTY ,
[{"transaction":"Select","record":{"SEPC":";","HDRS":"1","QERY":"TYTX15, TYITTY from MITTTY where TYNUMR <> “ and TYTPLI <> '' and TYOVIT = 1"}}]}

2.	**Country of origin** -> List of countries from program CRS045 are fetched. 
Transaction: /apiTxnList/EXPORTMI/Select/CSYTAB,
[{"transaction":"Select","record":{"SEPC":";","HDRS":"1","QERY":"CTSTKY, CTTX15 from CSYTAB where CTSTCO = CSCD"}}]}

3.	**Additional Attribute Mapping** -> Attributes from PPS040 will be fetched.
Transaction: /apiTxnList/MRS001MI/LstFields,
[{"transaction":"LstFields","record":{"MINM":"PPS040MI","TRNM":"AddItemSupplier","TRTP":"I"}}]}
Transaction: /apiTxnList/MRS001MI/LstFields,
[{"transaction":"LstFields","record":{"MINM":"PPS040MI","TRNM":"UpdItemSupplier","TRTP":"I"}}]}

4.	**Quality Class** -> Quality Class list will be fetched from PPS020 (Quality Class)
Transaction: /apiTxnList/EXPORTMI/Select/CSYTAB,
[{"transaction":"Select","record":{"SEPC":";","HDRS":"1","QERY":"CTSTKY, CTTX15 from CSYTAB where CTSTCO = QUCL"}}]}

Buyer can update below values during approval task triggered for Item creation request submitted by the supplier.
1.	M3 Item Type
2.	Lowest Permitted Quality Inspection
3.	Inspection Text
4.	Creation Responsible
5.	Quality Class
