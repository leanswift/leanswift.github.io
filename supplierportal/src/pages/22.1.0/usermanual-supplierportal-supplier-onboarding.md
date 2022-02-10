

# Version 22.1.0 - User Manual - Supplier Onboarding

# Table of contents

<div id=toc></div>

- [Supplier Onboarding](#Supplier_Onboarding)
 	- [Supplier Invite](#Supplier_Invite)	 
  - [Supplier Account Creation](#Supplier_Account_Creation)	 
  - [Supplier Onboarding Configuration](#Supplier_Onboarding_Configuration)
  - [My Documents Task](#My_Documents_Task)


# User Manual - Supplier Onboarding

<div id = "Supplier Onboarding"> </div> 

# Supplier Onboarding

Supplier Onboarding feature enables user to create new supplier account from Supplier Portal itself

<div id = "Supplier Invite"> </div> 

## Supplier Invite

To onboard a new supplier, admin user will send invite to supplier usgin his email id. Invite list can be viewed in admin.

Navigate to LeanSwift->Supplier Portal->Supplier Invite.

<kbd>
<kbd><img alt="CustomerPortal_Architecture" src="../../../images/customer-portal/front-end-user/CustomerPortal_Architecture.jpg"></kbd>
</kbd>

Image

Image

Click Add New Supplier Invite and supplier Invite form will be displayed.

Image

Enter new Supplier First Name, Supplier Last Name and Supplier Email. Select Associate to Website and Send Welcome Email from the listed drop-down values.
M3 Supplier Template lists the existing supplier template from M3 based on which new supplier is created. Drop-down values can be configured in supplier onboarding under Supplier settings.

Click Save and Invite. Invite is sent to the supplier email and supplier list is created with status Invitation sent successfully.

Image

Supplier Invite list can be searched using different filters. When portal fails to send invite mail to customer then status changes to Invitation sent failed.

Image

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "Supplier Account Creation"> </div> 

## Supplier Account Creation

Supplier will receive invite mail as below to create account and open the create supplier account link.

Image

Enter Strong Password (combination of alphanumeric and special characters) and click Set a New Password.
Page will be redirected to supplier user portal website based on website chosen to send invite with status as You updated your password. Enter your supplier mail id and password to Sign In

Image

When supplier set password and signed in then status will change to Customer Created Successfully in supplier invite list table.

Image

Initially Supplier can view only My Information tab with form to be submitted with all required information as below.

Image

You can add up to three references.
Clicking on Submit button brings a confirm popup when you submit the information.

Image

After submitting My Information form, supplier status will be changed to Supplier Mapped to Customer status in Supplier Invite list table.

Image

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "Supplier Onboarding Configuration"> </div> 

## Supplier Onboarding Configuration

My Information form field values can be configured under Supplier Onboarding in Supplier Configuration settings.

Navigate to LeanSwift->Supplier Portal->Settings and switch to Multi Website Scope configuration.

Image

M3 Supplier Template - Existing supplier template from M3 can be configured with comma separated values.

M3 Supplier Prefix – New supplier ID will be created with configured prefix value

Workflow Name – Give ION workflow Name used for supplier Onboarding

Fetch Configuration – This will fetch M3 Configuration fields with dropdown values.

Selected Dropdown values for M3 Language List, M3 Order Currency List, M3 Payment Terms, M3 Freight Terms, M3 Delivery Terms List and M3 Payment Method will be prepopulated in My Information form as default values. These values can be changed by supplier before submitting.


<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "My Documents Task"> </div> 

## My Documents Task

Supplier can view My Documents tab after submitting the onboarding information.

Image

Task to be completed will be triggered and this can be viewed by clicking checkbox icon next to bell icon notification.

The list of tasks available is based on the workflow created in ION.

Image

Upload Documents for assigned tasks with document name and click Mark Complete for the respective task.

Image

Approval Task will be generated in M3 for Information submitted by supplier and Document uploads.

Image

M3 Admin will review supplier information submitted and can add notes if any changes required.

Image

Image

Image

Image

Bell Icon Notification will be triggered in portal for Task notes updated in M3 and cron is configured to get task notes from M3.

Image

Image

As and when tasks are approved in M3, the task will also be removed for the user in frontend portal
Once all tasks are approved at M3, supplier will get access to all supplier portal features and notification will be triggered as below.

Image

Now that supplier account is activated, the new supplier can perform all the functionalities available in the supplier portal.

Image

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>


