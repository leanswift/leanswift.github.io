![CustomerPortalHeader](/Customerportal/src/images/customer-portal/front-end-user/CP_banner.jpg)

# Version 21.1.0 - User Manual - Customer Portal - User

# Table of contents

<div id=toc></div>

- [Overview](#Overview)
 	- [Architecture](#Architecture)	 
    - [Features](#Features)	 
    - [Point Of Contact](#Point_Of_Contact)
- [Registration](#Registration)
    - [Registration for Internal Customer (M3 User)](#Registration_for_Internal)
    - [Registration for External Customer](#Registration_for_External)
    - [Password Policy](#Password_Policy)
    - [General guidelines/help](#Help)
- [Login](#Login)
    - [Login](#Login1)
    - [User Privileges](#User_Privileges)
- [Forgot Password](#Forgot_Password)
- [Switch Customer](#Switch_Customer)
- [Download Sub Accounts Info](#Download_Sub_Accounts_Info)
- [My Account](#My_Account)
    - [Account Summary](#Account_Summary)
    - [Addresses](#Addresses)
- [Invoices](#Invoices)
    - [Invoice Search](#Invoice_Search)
    - [Invoice Filter](#Invoice_Filter)
    - [Invoice Sort](#Invoice_Sort)
    - [Download Current Statement](#Download_Current_Statement)
- [Orders](#Orders)
    - [Order Search](#Order_Search)
    - [Order Filter](#Order_Filter)
    - [Order Sort](#Order_Sort)
- [Sign Out](#Sign_Out)

# User Manual - Customer Portal - Front end User

<div id = "Overview"> </div> 

# Overview
LeanSwift Customer Portal is a customer self-service web portal that enables users to get instance access to information about their orders, invoices and payments. With additional add-ons, uses can also make e-payments directly via the portal. It is seamlessly integrated with Infor M3 CloudSuite using ION. Customer Portal offers a single point of access to structured information about customer transactions and self-service functionality such as pay invoices, user management and much more.

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "Architecture"></div>

# Architecture

<kbd>
<kbd><img alt="CustomerPortal_Architecture" src="../../../images/customer-portal/front-end-user/CustomerPortal_Architecture.jpg"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "Features"> </div> 

## Features
Account

- Registration and Login of External User
- Import and Login of Internal User
- View User Account Information
- Customer Selection by logged in user
- Switch Customer Account

Orders

- View Order History
- Synchronization of Order Status in real-time
- Search by Order#, Order Date
- Filter by Order Status
- Sort by Order Date

Invoices

- View Invoice History
- Synchronization of Invoice Status in real-time
- Search by Invoice#, Invoice Date
- Filter by Invoice Status
- Sort by Invoice Date

Payments

- Pay Invoices by CC
- Pay Invoices by Credit Memos
- Pay on Account by CC
- Support for both Full & Partial Payments
- Synchronization of Payment Status in real-time

Admin

- Settings and Configuration for Portal and M3 Connectivity
- M3 User Roles Configuration, User Permissions and sub-account management

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "Point_Of_Contact"> </div> 

## Point Of Contact

This document and the software it describes are provided by LeanSwift Solutions Inc. For additional information regarding support, licensing, functionality etc. please contact LeanSwift Solutions Inc. via contact form at http://www.leanswift.com or email info@leanswift.com.

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "Registration"> </div> 

# Registration

<div id = "Registration_for_Internal"> </div>  

## Registration for Internal Customer (M3 User)
- Internal customers (M3 users) can utilise their Infor OS (Mingle) credentials to access the Customer Portal without having to sign up.
- The password box is disabled whenever an internal user inputs an email address with a valid internal domain.

<kbd>
<kbd><img alt="CustomerPortalRegistration" src="../../../images/customer-portal/front-end-user/CustomerPortalRegistration.png"></kbd>
</kbd>

- By clicking Sign in, the front end user is redirected to Infor OS to authenticate their credentials.
  - Note: The user must use the same credentials to login to Infor OS as used to log in to the customer portal.

<kbd>
<kbd><img alt="CustomerPortalInforLogin" src="../../../images/customer-portal/front-end-user/CustomerPortalInforLogin.png"></kbd>
</kbd>

- Following successful validation in the Infor OS, the system generates a Request for Approval, which includes the requester's information and the choice to grant or deny access.

<kbd>
<kbd><img alt="CustomerPortalInforApprove" src="../../../images/customer-portal/front-end-user/CustomerPortalInforApprove.png"></kbd>
</kbd>

- Once the internal user has authorised access, the user gets signed in to Customer Portal.

Note: After the initial successful login, the Infor OS user id is created in the Customer Portal Database.

<kbd>
<kbd><img alt="CustomerPortalLogin" src="../../../images/customer-portal/front-end-user/CustomerPortalLogin.png"></kbd>
</kbd>

- If a user is unable to log in to Infor OS, they can utilise Forgot password to reset their password or Contact us to contact the team.

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "Registration_for_External"> </div> 

## Registration for External Customer 
- Users who have reference current Invoice number or Orders in the M3 system can register as an external customer in the Customer Portal.
- Registration for External Customer - Prerequisites:
  - First Name 
  - Last Name 
  - M3 Customer Number
  - Invoice/Order Number
  - Invoice/Order Amount
  - Email id

<kbd>
<kbd><img alt="CustomerPortalCreateAccount" src="../../../images/customer-portal/front-end-user/CustomerPortalCreateAccount.png"></kbd>
</kbd>

- As the user enters the above details, Customer number, Invoice/Order Number and Invoice/Order amount is validated.
- A STAT ID may or may not be associated with the client in M3.  Behavior of the portal is slightly different based on whether the customer has a STAT ID or not.
- The first customer to be associated with a new account will be an Admin user for the account and will have full access.
- All other users will have limited access on the site, until the admin provides additional privileges.

<kbd>
<kbd><img alt="CustomerPortalCreateAccount1" src="../../../images/customer-portal/front-end-user/CustomerPortalCreateAccount1.png"></kbd>
</kbd>

- Following successful registration, an email with a link for account verification and password creation is sent to the registered email address.

Note: Please check the Junk or Spam folder in case this mail does not arrive within few minutes.

<kbd>
<kbd><img alt="CustomerPortalSuccessRegn" src="../../../images/customer-portal/front-end-user/CustomerPortalSuccessRegn.png"></kbd>
</kbd>

<kbd>
<kbd><img alt="CustomerPortalEmail" src="../../../images/customer-portal/front-end-user/Email_Customer_Registration.PNG"></kbd>
</kbd>

- The link in the email directs the user to the password creation screen, where they can create a new password in accordance with the [password policy](#Password_Policy).

<kbd>
<kbd><img alt="CustomerPortalSetPassword" src="../../../images/customer-portal/front-end-user/CustomerPortalSetPassword.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id="Password_Policy"></div>

## Password Policy
Characteristics of Strong Password:

- Minimum of three different classes of characters. 
- Classes of characters: 
  - Lower Case
  - Upper Case
  - Digits
  - Special Characters
- Minimum length must be equal or greater than 8 symbols. 
- Leading and trailing spaces are ignored.

<kbd>
<kbd><img alt="CustomerPortalSetPassword1" src="../../../images/customer-portal/front-end-user/CustomerPortalSetPassword1.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id="Help"></div>

## General guidelines/help
- The following are some of the possible mistakes that can occur when enrolling a new user.
  - Customer number not present in the Customer Portal Database.
  - The requested order/invoice does not match.
    - The combination of Customer number, Invoice number and Amount did not match in M3 system and Customer Portal Database.
  - Registration is not allowed for this customer.
    - Customer Number is part of a restricted user group that is denied access to the Customer portal.
  - There is already an account with this email address. If you are sure that it is your email address, [click here](https://cpqa.leanswiftdev.net/customer/account/forgotpassword/) to get your password and access your account.

<kbd>
<kbd><img alt="CustomerPortalGuideline" src="../../../images/customer-portal/front-end-user/CustomerPortalGuideline.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id="Login"></div>

# Login
- The user logs in to Customer Portal using their registered credentials. 

<kbd>
<kbd><img alt="CustomerPortalHome" src="../../../images/customer-portal/front-end-user/CustomerPortalHome.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id="Login1"></div>

## Login
- Successful login takes the front end user to the Customer Portal main screen, which displays a list of customers.
- The user can choose a customer and view their information.

<kbd>
<kbd><img alt="CustomerPortalMainScreen" src="../../../images/customer-portal/front-end-user/CustomerPortalMainScreen.png"></kbd>
</kbd>

<kbd>
<kbd><img alt="CustomerPortalLogin1" src="../../../images/customer-portal/front-end-user/CustomerPortalLogin1.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id="User_Privileges"></div>

## User Privileges
- Based on the user privileges of the external user, the options are enabled.

|External User|My Account|Switch Accounts|Download Sub Accounts Info|
| :- | :- | :- | :- |
|Customer with STAT ID + Account Admin User|Yes|Yes|Yes|
|Customer with STAT ID + Account Normal User|Yes|Yes|No|
|Customer without STAT ID|Yes|No|No|

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id="Forgot_Password"></div>

# Forgot Password
- To reset the password, user can click on forgot password button in the home screen of Customer Portal.

<kbd>
<kbd><img alt="CustomerPortalForgotPasswordButton" src="../../../images/customer-portal/front-end-user/CustomerPortalForgotPasswordButton.png"></kbd>
</kbd>

- The user can provide a registered email id and request a reset password.

<kbd>
<kbd><img alt="CustomerPortalForgotPassword" src="../../../images/customer-portal/front-end-user/CustomerPortalForgotPassword.png"></kbd>
</kbd>

- The password reset link will be sent to the user's email address.

<kbd>
<kbd><img alt="CustomerPortalSetPassEmail" src="../../../images/customer-portal/front-end-user/CustomerPortalSetPassEmail.png"></kbd>
</kbd>

- The link redirects the user to the password reset page, where they can create a new password that meets the[ password policy](#_heading=h.17dp8vu).

<kbd>
<kbd><img alt="CustomerPortalSetPassword" src="../../../images/customer-portal/front-end-user/CustomerPortalSetPassword.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id="Switch_Customer"></div>

# Switch Customer
- The Switch Customer option on the top right drop down menu is enabled for users with [privileges](#_heading=h.35nkun2) to view other customer account details.

<kbd>
<kbd><img alt="CustomerPortalSwitchCustomer" src="../../../images/customer-portal/front-end-user/CustomerPortalSwitchCustomer.png"></kbd>
</kbd>

- Once the user clicks on the switch customer option, a list of the user's customers are displayed. 
- To view details about a customer, the user must first select the customer.

<kbd>
<kbd><img alt="CustomerPortalLogin" src="../../../images/customer-portal/front-end-user/CustomerPortalLogin.png"></kbd>
</kbd>
<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id="Download_Sub_Accounts_Info"></div>

# Download Sub Accounts Info

- Users having Sub Accounts, i.e. Account Admin Users, have the option to download Sub Accounts Info.

<kbd>
<kbd><img alt="CustomerPortalDownloadSubAcc" src="../../../images/customer-portal/front-end-user/CustomerPortalDownloadSubAcc.png"></kbd>
</kbd>

- Click on Download Sub Accounts Info Option, to download the details of sub accounts in CSV format.
    - Name - Name of the customer.
    - Email - Email id of the customer.
    - Allowed Sections - The sections allowed to the user - View Order History, View Invoice History, View Pay Invoices.
    - Make Payment - Provides information on whether or not the customer has privileges to make a payment - Yes/No.

<kbd>
<kbd><img alt="CustomerPortalDownloadSubAcc1" src="../../../images/customer-portal/front-end-user/CustomerPortalDownloadSubAcc1.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id="My_Account"></div>

# My Account
- The My Account menu shows the selected customer's account information.

<kbd>
<kbd><img alt="CustomerPortalMyAccount" src="../../../images/customer-portal/front-end-user/CustomerPortalMyAccount.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id="Account_Summary"></div>

## Account Summary
- The user can access account summary, from the Accounts section's drop down menu,.
- The customer's contact information and invoice address are displayed in the account summary.

<kbd>
<kbd><img alt="CustomerPortalAccountSummary" src="../../../images/customer-portal/front-end-user/CustomerPortalAccountSummary.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id="Addresses"></div>

## Addresses
- The Addresses option displays the customer's invoice address as well as any extra addresses.

<kbd>
<kbd><img alt="CustomerPortalAddresses" src="../../../images/customer-portal/front-end-user/Additional_Address.PNG"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id="Invoices"></div>

# Invoices
- The customer's invoice data are displayed in the Invoice tab:Invoice number, Order number, Customer number, Customer PO Ref, Invoice Date, Invoice Amount, and Status.
- Ten invoice entries are displayed per page.

<kbd>
<kbd><img alt="CustomerPortalInvoices" src="../../../images/customer-portal/front-end-user/CustomerPortalInvoices.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id="Invoice_Search"></div>

## Invoice Search
- Search by Invoice Number or Order Number.
- Search by Invoice Date 
  - The user can view Invoices by slecting start date(Year 2018) and end date(Current year).

<kbd>
<kbd><img alt="CustomerPortalSearchOption" src="../../../images/customer-portal/front-end-user/Invoice_Search_Date.PNG"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id="Invoice_Filter"></div>

## Invoice Filter
- The user can filter invoices based on the status of invoices.
  - Open Invoices
  - Paid Invoices
  - All Invoices

<kbd>
<kbd><img alt="CustomerPortalFilter" src="../../../images/customer-portal/front-end-user/CustomerPortalFilter.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id="Invoice_Sort"></div>

## Invoice Sort
- By clicking on the sort arrow next to Invoice Date, users can sort the invoices by date.
- By default, invoices are sorted in descending order, with the most recent invoices appearing first.

<kbd>
<kbd><img alt="CustomerPortalInvoiceSort" src="../../../images/customer-portal/front-end-user/CustomerPortalInvoiceSort.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id="Download_Current_Statement"></div>

## Download Current Statement
- Click on Download Current Statement menu to download Current Open Invoices in CSV format.

<kbd>
<kbd><img alt="CustomerPortalDownloadCurrentStatement" src="../../../images/customer-portal/front-end-user/CustomerPortalDownloadCurrentStatement.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id="Orders"></div>

# Orders
- Orders tab displays the customer's order information – Order number, Customer number, Customer PO/Reference, Order Date and Order Status.
- Ten order entries are displayed per page.

<kbd>
<kbd><img alt="CustomerPortalOrders" src="../../../images/customer-portal/front-end-user/CustomerPortalOrders.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id="Order_Search"></div>

## Order Search
- Search by Order Number.
- Search by Order Date.

<div id="Order_Filter"></div>

## Order Filter
The user can filter orders based on the status of invoices.

- All Orders
- Open Orders
- Fully Invoiced Orders

<kbd>
<kbd><img alt="CustomerPortalInvoiceFilter" src="../../../images/customer-portal/front-end-user/CustomerPortalInvoiceFilter.png"></kbd>
</kbd>

<div id="Order_Sort"></div>

## Order Sort
- By clicking on the sort arrow next to Order Date, users may sort the orders by date.
- By default, orders are sorted in descending order, with the most recent orders appearing first.

<kbd>
<kbd><img alt="CustomerPortalInvoiceSort" src="../../../images/customer-portal/front-end-user/CustomerPortalInvoiceSort.png"></kbd>
</kbd>
<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id="Sign_Out"></div>

# Sign Out
- Click on the arrow next to the user's name on top right corner of the Customer Portal. 
- Select Sign Out from the dropdown menu.
- The user will be redirected to the main page in 5 seconds after successfully signing out.

<kbd>
<kbd><img alt="CustomerPortalSignOut" src="../../../images/customer-portal/front-end-user/CustomerPortalSignOut.png"></kbd>
</kbd>

<kbd>
<kbd><img alt="CustomerPortalHome" src="../../../images/customer-portal/front-end-user/CustomerPortalHome.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>
