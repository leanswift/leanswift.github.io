![Supplier portal banner](/Customerportal/src/images/customer-portal/front-end-user/CP_banner.jpg)

# Version 1.0.0 - User Manual - M3 Login

# Table of Contents

<div id="toc"></div>

- [Overview](#Overview)
    - [Architecture](#Architecture)
    - [Features](#Features)
    - [Point of Contact](#Point_of_Contact)
- [User Guide for M3 Login Module – Admin User](#User_Guide_for_M3_Login_Module_Admin_User)
  - [Login](#Login)
  - [General](#General)
  - [Authentication](#Authentication)
  - [Prerequisites](#Prerequisites)
	- [Force_Customer_Login](#Force_Customer_Login)
	- [White List](#White_List)
	- [Add Entry](#Add_Entry)
	- [Edit/Delete Entry](#Edit_Delete_Entry)
	- [Customer User Permissions](#Customer_User_Permissions)

<div id = "Overview"> </div>

## Overview
**LeanSwift M3 login module** provides the ability to log into Magento with an Infor OS user (Single Sign-on support with Infor OS). It also retrieves the list of users in Infor M3 along with security roles. The module leverages ION APIs and Infor’s authentication and authorization services to validate M3 user credentials (Ming.le user) via IFS (Infor Federation Services).
<div id = "Architecture"></div>

# Architecture

<kbd>
<kbd><img alt="CustomerPortal_Architecture" src="../../../images/add-ons/m3-login/CustomerPortal_Architecture.jpg"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>


<div id = "Features"> </div>

## Features
- Redirect user login attempt from Magento to Infor OS (Ming.le) login interface
- Authenticate Ming.le user credentials
- Redirect to invoking Magento interface after authentication is successful
- Retrieves list of M3 users and associated security roles

<div align="right">
<p>
 <a href="#toc" align="right">↥ Go to Top</a>
</p>
</div>

<div id = "Point_of_Contact"> </div>

## Point Of Contact
This document and the software it describes are provided by LeanSwift Solutions Inc. For additional information regarding support, licensing, functionality etc. please contact LeanSwift Solutions Inc. via contact form at http://www.leanswift.com or email info@leanswift.com.

<div align="right">
<p>
 <a href="#toc">↥ Go to Top</a>
</p>
</div>

<div id = "User_Guide_for_M3_Login_Module_Admin_User"> </div>

# User Guide for M3 Login Module – Admin User

<div id = "Login"> </div>

## Login
- To access M3 Login Settings as admin user, go to LeanSwift – M3 Login – Settings.
<kbd>
<kbd class="aligncenter"><img alt="M3Login" src="../../../images/add-ons/m3-login/M3Login.jpg"></kbd>
</kbd>

- From the M3 Login module the Admin user can configure logging preference, domain and authentication settings and click on Save Config.

<kbd>
<kbd><img alt="M3LoginHomePage" src="../../../images/add-ons/m3-login/M3LoginHomePage.jpg"></kbd>
</kbd>

<div align="right">
<p>
 <a href="#toc">↥ Go to Top</a>
</p>
</div>

<div id = "General"> </div>

## General
- M3 Login general module allows admin to configure logging preference and internal email domain settings. 
- Go to LeanSwift – M3 Login – Settings – General.
- Enable Login
  - To enable login for M3 User, configure Enable Login setting as Yes.
  - Configuring the enable login as No, disables M3 User Login into Customer Portal. Internal users will not be able to access Customer Portal.              
- Debug/log data
  - To enable debug/log data, configure Debug/log data as Yes.
  - Setting Debug/log data to No, disables logger.
  - The logger is disabled by default, and can be enabled to check request and response data for troubleshooting purposes.

<kbd>
<kbd><img alt="M3Login-General" src="../../../images/add-ons/m3-login/M3Login-General.jpg"></kbd>
</kbd>

- Internal user Email domain(s)
  - Configure the internal user email domain(s).
  - Specify comma separated list of internal user email domains.Ex: leanswift.com 
  - If the login Id contains any of the internal user email domains, the password field is disabled and the user is taken to Magento for login authentication.

<div align="right">
<p>
 <a href="#toc">↥ Go to Top</a>
</p>
</div>

<div id = "Authentication"> </div>

## Authentication
- M3 Login authentication module allows admin to configure service URL for authorization, service URL for Ming.le, Client id and Client secret settings. 
  - This information can be obtained from [Multi-tenant Cloud Infor OS](https://www.infor.com/resources/infor-ming-le).
- Go to LeanSwift – M3 Login – Settings – Authentication.

<kbd>
<kbd><img alt="M3Login-Authentication" src="../../../images/add-ons/m3-login/M3Login-Authentication.jpg"></kbd>
</kbd>

<div align="right">
<p>
 <a href="#toc">↥ Go to Top</a>
</p>
</div>

<div id = "Prerequisites"> </div>

## Prerequisites

<div id = "Force_Customer_Login"> </div>

### Force Customer Login

<div id = "White_List"> </div>

#### White List
- To whitelist URLs, admin shall login to Magento System and go to Customers – White List. 
- For first-time internal user login, whitelisting URLs is a prerequisite.
<kbd>
<kbd><img alt="Customer-Whitelist" src="../../../images/add-ons/m3-login/Customer-Whitelist.jpg"></kbd>
</kbd>

- Force Customer Login – Overview screen displays whitelisted URLS, id, label, rules, Strategy and Store.
<kbd>
<kbd><img alt="Customer-WhitelistHome" src="../../../images/add-ons/m3-login/Customer-WhitelistHome.jpg"></kbd>
</kbd>

<div align="right">
<p>
 <a href="#toc">↥ Go to Top</a>
</p>
</div>

<div id = "Add_Entry"> </div>

#### *Add Entry*
- To add white list entry admin users can go to Customers – White List – Click on Add Entry. 

<kbd>
<kbd><img alt="Customer-Whitelist-AddentryButton" src="../../../images/add-ons/m3-login/Customer-Whitelist-AddentryButton.jpg"></kbd>
</kbd>

- Force Customer Login – Create a new entry screen.
- Provide details of white list entry.
  - Label – Specify the label for entry. Eg: M3 Login Page.
  - URL rule – Specify the URL Path /lslogin/index/index. This configuration is standard for Customer Portal.
  - Strategy – Specify the Strategy - Static, RegEx (All), RegEx (Negation).
  - Store – Select Store view – Eg: All Stores, Default Store View, CP Stage Store View.
- Click on Save to create a new white list entry.

<kbd>
<kbd><img alt="Customer-Whitelist-AddentryScreen" src="../../../images/add-ons/m3-login/Customer-Whitelist-AddentryScreen.jpg"></kbd>
</kbd>

<div align="right">
<p>
 <a href="#toc">↥ Go to Top</a>
</p>
</div>

<div id = "Edit_Delete_Entry"> </div>

#### *Edit/Delete Entry*
- To edit or delete Whitelist entry, go to Customers – Whitelist – Click on Edit or Delete next to the entry.

<kbd>
<kbd><img alt="Customer-Whitelist-Edit" src="../../../images/add-ons/m3-login/Customer-Whitelist-Edit.jpg"></kbd>
</kbd>

<div align="right">
<p>
 <a href="#toc">↥ Go to Top</a>
</p>
</div>

<div id = "Restore_Defaults"> </div>

#### *Restore Defaults*
- To restore defaults of white listed URLs, go to Customer – White List – Click on Restore Defaults.
- Restoring default is a prerequisite for internal users to have access for **Customer Portal**.
<kbd>
<kbd><img alt="Customer-Whitelist-Restore" src="../../../images/add-ons/m3-login/Customer-Whitelist-Restore.jpg"></kbd>
</kbd>

<div align="right">
<p>
 <a href="#toc">↥ Go to Top</a>
</p>
</div>

<div id = "Customer_User_Permissions"> </div>

### Customer User Permissions 
- Users must have roles assigned to them in Magento, and they can only log in to the frontend based on the rights they have been allowed.

- **Internal User Permission**
<kbd>
<kbd><img alt="UserPermission-InternalUserPermission" src="../../../images/add-ons/m3-login/UserPermission-InternalUserPermission.png"></kbd>
</kbd>

- M3 USER Role - Internal User permissions are leveraged at M3 user Role configuration. 
  - Customers of Magento have permissions by default. 
  - Users should have access configured both in Customers Portal Settings and M3 user role settings.

<div align="right">
<p>
 <a href="#toc">↥ Go to Top</a>
</p>
</div>
