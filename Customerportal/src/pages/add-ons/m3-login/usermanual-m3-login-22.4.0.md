![CustomerPortalHeader](/Customerportal/src/images/customer-portal/front-end-user/CP_banner.jpg)

# **Version 22.4.0- User Manual - M3 Login**

# Table of contents

<div id = "toc"></div>


  - [Overview](#overview)
  - [Architecture](#architecture)
  - [Features](#features)
  - [Point Of Contact](#point-of-contact)
  - [User Guide for M3 Login Module – Admin User](#user-guide-for-m3-login-module--admin-user)
     - [Login](#login)
     - [General](#general)
     - [Authentication](#authentication)
     - [Import M3 User Roles](#import-m3-user-roles)
     - [Customer User Permissions](#customer-user-permissions)


## Overview

<div id = "overview"> </div>

**LeanSwift M3 login module**  provides the ability to log into Magento with an Infor OS user (Single Sign-on support with Infor OS). It also retrieves the list of users in Infor M3 along with security roles. The module leverages ION APIs and Infor's authentication and authorization services to validate M3 user credentials (Ming.le user) via IFS (Infor Federation Services).

# Architecture

<div id = "architecture"></div>

<kbd>
<kbd><img alt="CustomerPortal_Architecture" src="../../../images/customer-portal/admin-user/CustomerPortal_Architecture.jpg"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

## Features

- Redirect user login attempt from Magento to Infor OS (Ming.le) login interface
- Authenticate Ming.le user credentials
- Redirect to invoking Magento interface after authentication is successful
- Retrieves list of M3 users and associated security roles

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

## Point Of Contact

This document and the software it describes are provided by LeanSwift Solutions Inc. For additional information regarding support, licensing, functionality etc. please contact LeanSwift Solutions Inc. via contact form at [http://www.leanswift.com](http://www.leanswift.com/) or email [info@leanswift.com](mailto:info@leanswift.com).

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

# User Guide for M3 Login Module – Admin User

<div id = "Login"> </div>

## Login

- To access M3 Login Settings as admin user, go to LeanSwift – M3 Login – Settings.

<kbd>
<kbd><img alt="M3Configuration" src="../../../images/add-ons/m3-login/22.4.0/M3Configuration.png"></kbd>
</kbd>

- From the M3 Login module the Admin user can configure logging preference, domain and authentication settings and click on Save Config.

<kbd>
<kbd><img alt="M3SaveConfiguration" src="../../../images/add-ons/m3-login/22.4.0/M3SaveConfiguration.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

## General

- M3 Login general module allows admin to configure logging preference and internal email domain settings.
- Go to LeanSwift – M3 Login – Settings – General.
- Enable Login
  - To enable login for M3 User, configure Enable Login setting as Yes.
  - Configuring the enable login as No, disables M3 User Login into Customer Portal. Internal users will not be able to access Customer Portal.
- Debug/log data
  - To enable debug/log data, configure Debug/log data as Yes.
  - Setting Debug/log data to No, disables logger.
  - The logger is disabled by default and can be enabled to check request and response data for troubleshooting purposes.

<kbd>
<kbd><img alt="M3Genral" src="../../../images/add-ons/m3-login/22.4.0/M3Genral.png"></kbd>
</kbd>

- Internal user Email domain(s)
  - Configure the internal user email domain(s).
  - Specify comma separated list of internal user email domains.Ex: leanswift.com
  - If the login Id contains any of the internal user email domains, the password field is disabled and the user is taken to Magento for login authentication.

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

## Authentication

- M3 Login authentication module allows admin to configure service URL for authorization, service URL for Ming.le, Client id and Client secret settings.
  - This information can be obtained from [Multi-tenant Cloud Infor OS](https://www.infor.com/resources/infor-ming-le).
- Go to LeanSwift – M3 Login – Settings – Authentication.

<kbd>
<kbd><img alt="Authentication" src="../../../images/add-ons/m3-login/22.4.0/Authentication.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

## Import M3 User Roles

- It is part of add-on to fetch M3 User Roles and Functions as initial import. This is not required for Customer Portal v21.1.0.

<kbd>
<kbd><img alt="M3UserRoles" src="../../../images/add-ons/m3-login/22.4.0/M3UserRoles.png"></kbd>
</kbd>

## Prerequisites

<div id = "Force_Customer_Login"> </div>

### Force Customer Login

<div id = "White_List"> </div>

#### White List
- To whitelist URLs, admin shall login to Magento System and go to Customers – White List. 
- For first-time internal user login, whitelisting URLs is a prerequisite.
<kbd>
<kbd><img alt="Customer-Whitelist" src="../../../images/add-ons/m3-login/22.4.0/M3Login_WhiteList.png"></kbd>
</kbd>

- Force Customer Login – Overview screen displays whitelisted URLS, id, label, rules, Strategy and Store.
<kbd>
<kbd><img alt="Customer-ForceLogin" src="../../../images/add-ons/m3-login/22.4.0/M3Login_ForceCustomerLogin.png"></kbd>
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
<kbd><img alt="Customer-Whitelist-AddentryButton" src="../../../images/add-ons/m3-login/22.4.0/M3Login_AddEntry.png"></kbd>
</kbd>

- Force Customer Login – Create a new entry screen.
- Provide details of white list entry.
  - Label – Specify the label for entry. Eg: M3 Login Page.
  - URL rule – Specify the URL Path /lslogin/index/index. This configuration is standard for Customer Portal.
  - Strategy – Specify the Strategy - Static, RegEx (All), RegEx (Negation).
  - Store – Select Store view – Eg: All Stores, Default Store View, CP Stage Store View.
- Click on Save to create a new white list entry.

<kbd>
<kbd><img alt="Customer-Whitelist-Addentry-Save" src="../../../images/add-ons/m3-login/22.4.0/M3Login_AddEntry_Save.png"></kbd>
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
<kbd><img alt="Customer-Whitelist-Edit" src="../../../images/add-ons/m3-login/22.4.0/M3Login_ForceCustomerLogin_EditOrDelete.png"></kbd>
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
<kbd><img alt="Customer-Whitelist-Restore" src="../../../images/add-ons/m3-login/22.4.0/M3Login_RestoreDefaults.png"></kbd>
</kbd>

<div align="right">
<p>
 <a href="#toc">↥ Go to Top</a>
</p>
</div>

<div id = "Customer_User_Permissions"> </div>

## Customer User Permissions

- Users must have roles assigned to them in Magento, and they can only log in to the frontend based on the rights they have been allowed.
- **Internal User Permission**

<kbd>
<kbd><img alt="InternalPermission" src="../../../images/add-ons/m3-login/22.4.0/InternalPermission.png"></kbd>
</kbd>

- M3 USER Role - Internal User permissions are leveraged at M3 user Role configuration.
  - Customers of Magento have permissions by default.
  - Users should have access configured both in Customers Portal Settings and M3 user role settings.

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>
