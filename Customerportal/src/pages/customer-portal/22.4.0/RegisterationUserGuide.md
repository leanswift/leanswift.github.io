![CustomerPortalHeader](/Customerportal/src/images/customer-portal/front-end-user/CP_banner.jpg)

# **New Version 22.4.0 - Registration Manual – LeanSwift Customer Portal - User**

# Table of contents

<div id = "toc"></div>

- [**New Version 22.4.0 - Registration Manual – LeanSwift Customer Portal - User**](#new-version-2240-registration-manual-leanswift-customer-portal-user)
- [**Table of contents**](#table-of-contents)
- [**Overview**](#overview)
- [**Architecture**](#architecture)
- [**Features**](#features)
- [**Point Of Contact**](#point-of-contact)
- [**Registration**](#registration)
- [**Login**](#login)
- [**Forgot Your Password**](#forgot-your-password)
- [**Switch Customer**](#switch-customer)
- [**Download Sub Accounts Info**](#download-sub-accounts-info)
- [**My Account**](#my-account)
- [**My Invoices**](#my-invoices)
- [**My Orders**](#my-orders)
- [**Sign Out**](#sign-out)

<div id = "overview"> </div>

# **Overview**

LeanSwift Customer Portal is a customer self-service web portal that enables users to get instance access to information about their orders, invoices and payments. With additional add-ons, uses can also make e-payments directly via the portal. It is seamlessly integrated with Infor M3 CloudSuite using ION. Customer Portal offers a single point of access to structured information about customer transactions and self-service functionality such as pay invoices, user management and much more.

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "architecture"></div>

# **Architecture**

<kbd>
<kbd><img alt="CustomerPortal_Architecture" src="../../../images/customer-portal/admin-user/CustomerPortal_Architecture.jpg"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "features"> </div>

**Features**

Account

- Registration and Login of External User
- Import and Login of Internal User
- View User Account Information
- Customer Selection by logged in user
- Switch Customer Account

Orders

- View Order History
- Synchronization of Order Status in real-time
- Search by Po reference#, Order Date
- Filter by Order Status
- Sort by Order Date

Invoices

- View Invoice History
- Synchronization of Invoice Status in real-time
- Search by Invoice number or po reference#, Invoice Date
- Filter by Invoice Status
- Sort by Invoice Date

Payments

- Pay Invoices by CC
- Pay Invoices by Credit Memos
- Pay on Account by CC
- Support for both Full & Partial Payments
- Synchronization of Payment Status via cron

Admin

- Settings and Configuration for Portal and M3 Connectivity
- M3 User Roles Configuration, User Permissions and sub-account management

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "point-of-contact"> </div>

**Point Of Contact**

This document and the software it describes are provided by LeanSwift Solutions Inc. For additional information regarding support, licensing, functionality etc. please contact LeanSwift Solutions Inc. via contact form at http://www.leanswift.com or email info@leanswift.com.

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "registration"> </div>

# **Registration**

**Registration for Internal Customer (M3 User)**

- Internal customers (M3 users) can utilise their Infor OS (Mingle) credentials to access the Customer Portal without having to sign up.
- The password box is disabled whenever an internal user inputs an email address with a valid internal domain.

<kbd>
<kbd><img alt="InternalLogin" src="../../../images/22.4.0/RegisterUserGuide/InternalLogin.png"></kbd>
</kbd>

- By clicking Sign in, the front-end user is redirected to Infor OS to authenticate their credentials.
  - Note: The user must use the same credentials to login to Infor OS as used to log in to the customer portal.

<kbd>
<kbd><img alt="M3Credentials" src="../../../images/22.4.0/RegisterUserGuide/M3Credentials.png"></kbd>
</kbd>

- Following successful validation in the Infor OS, the system generates a Request for Approval, which includes the requester's information and the choice to grant or deny access.

<kbd>
<kbd><img alt="M3Approval" src="../../../images/22.4.0/RegisterUserGuide/M3Approval.png"></kbd>
</kbd>

- Once the internal user has authorised access, the user gets signed into Customer Portal.

Note: After the initial successful login, the Infor OS user id is created in the Customer Portal Database.

<kbd>
<kbd><img alt="InternalCustomerPage" src="../../../images/22.4.0/RegisterUserGuide/InternalCustomerPage.png"></kbd>
</kbd>

- If a user is unable to log in to Infor OS, they can utilise Forgot password to reset their password or contact us to contact the team.

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

**Registration for External Customer**

- Users who have reference current Invoice number or Orders in the M3 system can register as an external customer in the Customer Portal.
- Registration for External Customer - Prerequisites:
  - First Name
  - Last Name
  - Customer Number
  - Invoice/Order Number
  - Invoice/Order Amount
  - Email
  - Confirm Email

<kbd>
<kbd><img alt="ExternalCustomer" src="../../../images/22.4.0/RegisterUserGuide/ExternalCustomer.png"></kbd>
</kbd>

- As the user enters the above details, Customer number, Invoice/Order Number and Invoice/Order amount is validated.
- A STAT ID may or may not be associated with the client in M3. Behaviour of the portal is slightly different based on whether the customer has a STAT ID or not.
- The first customer to be associated with a new account will be an Admin user for the account and will have full access.
- All other users will have limited access on the site, until the admin provides additional privileges.

<kbd>
<kbd><img alt="ExternalCustomerDetails" src="../../../images/22.4.0/RegisterUserGuide/ExternalCustomerDetails.png"></kbd>
</kbd>

- Following successful registration, an email with a link for account verification and password creation is sent to the registered email address.

Note: Please check the Junk or Spam folder in case this mail does not arrive within few minutes.

<kbd>
<kbd><img alt="ExternalCustomerSucessfull" src="../../../images/22.4.0/RegisterUserGuide/ExternalCustomerSucessfull.png"></kbd>
</kbd>

<kbd>
<kbd><img alt="ExternalCustomerMail" src="../../../images/22.4.0/RegisterUserGuide/ExternalCustomerMail.png"></kbd>
</kbd>

- The link in the email directs the user to the password creation screen, where they can create a new password in accordance with the [password policy](https://leanswift.github.io/Customerportal/src/pages/customer-portal/22.4.0/registration-user-guide.html#Password_Policy).

<kbd>
<kbd><img alt="SetNewPassword" src="../../../images/22.4.0/RegisterUserGuide/SetNewPassword.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

**Password Policy**

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
<kbd><img alt="PasswordPolicy" src="../../../images/22.4.0/RegisterUserGuide/PasswordPolicy.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

**General guidelines/help**

- The following are some of the possible mistakes that can occur when enrolling a new user.
  - Customer number should not present in the Customer Portal Database.
  - The requested order/invoice does not match.
    - The combination of Customer number, Invoice number and Amount did not match in M3 system and Customer Portal Database.
  - Registration is not allowed for this customer.
    - Customer Number is part of a restricted user group that is denied access to the Customer portal.
  - There is already an account with this email address. If you are sure that it is your email address, [click here](https://cpqa.leanswiftdev.net/customer/account/forgotpassword/) to get your password and access your account.

<kbd>
<kbd><img alt="ExternalCustomerError" src="../../../images/22.4.0/RegisterUserGuide/ExternalCustomerError.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "login"> </div>

# **Login**

- The user logs in to Customer Portal using their registered credentials.

<kbd>
<kbd><img alt="LoginPage" src="../../../images/22.4.0/RegisterUserGuide/LoginPage.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

**Login**

- Successful login takes the front-end user to the Customer Portal main screen, which displays a list of customers.
- The user can choose a customer and view their information.
- We can logout to that customer while we are opening a particular customer.

<kbd>
<kbd><img alt="ExternalCustomerPage" src="../../../images/22.4.0/RegisterUserGuide/ExternalCustomerPage.png"></kbd>
</kbd>

<kbd>
<kbd><img alt="MyAccountPage" src="../../../images/22.4.0/RegisterUserGuide/MyAccountPage.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

**User Privileges**

- Based on the user privileges of the external user, the options are enabled.

| **External User** | **My Account** | **Switch Accounts** | **Download Sub Accounts Info** |
| --- | --- | --- | --- |
| Customer with STAT ID + Account Admin User | Yes | Yes | Yes |
| --- | --- | --- | --- |
| Customer with STAT ID + Account Normal User | Yes | Yes | No |
| Customer without STAT ID | Yes | No | No |

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "forgot-your-password"> </div>

# **Forgot Your Password**

- To reset the password, user can click on forgot password button in the home screen of Customer Portal.

<kbd>
<kbd><img alt="ForgotPassword" src="../../../images/22.4.0/RegisterUserGuide/ForgotPassword.png"></kbd>
</kbd>

- The user can provide a registered email id and request a reset password.

<kbd>
<kbd><img alt="ForgotPasswordGiven" src="../../../images/22.4.0/RegisterUserGuide/ForgotPasswordGiven.png"></kbd>
</kbd>

- After entering email id and clicking on Reset My password, it will take to Customer portal home page with message displayed " **If there is an account associated with challa.anjana@leanswift.com you will receive an email with a link to reset your password.**"

<kbd>
<kbd><img alt="ForgotPasswordEmailSent" src="../../../images/22.4.0/RegisterUserGuide/ForgotPasswordEmailSent.png"></kbd>
</kbd>

- The password reset link will be sent to the user's email address.

<kbd>
<kbd><img alt="ForgotPasswordEmail" src="../../../images/22.4.0/RegisterUserGuide/ForgotPasswordEmail.png"></kbd>
</kbd>

- The link redirects the user to the password reset page, where they can create a new password that meets the[ password policy](https://leanswift.github.io/Customerportal/src/pages/customer-portal/22.4.0/registration-user-guide.html#_heading=h.17dp8vu).

<kbd>
<kbd><img alt="ForgotPasswordNewPassword" src="../../../images/22.4.0/RegisterUserGuide/ForgotPasswordNewPassword.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "switch-customer"> </div>

# **Switch Customer**

- The Switch Customer option on the right side human icon menu is enabled for users with [privileges](https://leanswift.github.io/Customerportal/src/pages/customer-portal/22.4.0/registration-user-guide.html#_heading=h.35nkun2) to view other customer account details.

<kbd>
<kbd><img alt="SwitchCustomer" src="../../../images/22.4.0/RegisterUserGuide/SwitchCustomer.png"></kbd>
</kbd>

- Once the user clicks on the switch customer option, a list of the user's customers are displayed.
- To view details about a customer, the user must first select the customer.

<kbd>
<kbd><img alt="ExternalCustomerPage" src="../../../images/22.4.0/RegisterUserGuide/ExternalCustomerPage.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "download-sub-accounts-info"> </div>

# **Download Sub Accounts Info**

- Users having Sub Accounts, i.e. Account Admin Users, have the option to download Sub Accounts Info.

<kbd>
<kbd><img alt="DownloadSubAccounts" src="../../../images/22.4.0/RegisterUserGuide/DownloadSubAccounts.png"></kbd>
</kbd>

- Click on Download Sub Accounts Info Option, to download the details of sub accounts in CSV format.
  - Name - Name of the customer.
  - Email - Email id of the customer.
  - Allowed Sections - The sections allowed to the user - View Order History, View Invoice History, View Pay Invoices.
  - Make Payment - Provides information on whether the customer has privileges to make a payment - Yes/No.

<kbd>
<kbd><img alt="SubAccountExcel" src="../../../images/22.4.0/RegisterUserGuide/SubAccountExcel.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "my-account"> </div>

# **My Account**

- The My Account menu shows the selected customer's account information.

<kbd>
<kbd><img alt="MyAccounts" src="../../../images/22.4.0/RegisterUserGuide/MyAccounts.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

**My Addresses**

- The My Addresses option displays the customer's invoice address as well as any extra addresses.

<kbd>
<kbd><img alt="MyAddress" src="../../../images/22.4.0/RegisterUserGuide/MyAddress.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "my-invoices"> </div>

# **My Invoices**

- The customer's invoice data are displayed in the Invoice tab: Invoice number, Order number, Customer number, Customer PO Ref, Invoice Date, Invoice Amount, and Status.
- Ten invoice entries are displayed per page.

<kbd>
<kbd><img alt="MyInvoices" src="../../../images/22.4.0/RegisterUserGuide/MyInvoices.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

**My Invoice Search**

- Search by Invoice Number or Po reference.
- Search by Invoice Date
  - The user can view Invoices by selecting start date (Year 2018) and end date (Current year).

<kbd>
<kbd><img alt="MyInvoicesSearch" src="../../../images/22.4.0/RegisterUserGuide/MyInvoicesSearch.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

**My Invoice Filter**

- The user can filter invoices based on the status of invoices.
  - Open Invoices
  - Paid Invoices
  - All Invoices

<kbd>
<kbd><img alt="MyInvoicesFilters" src="../../../images/22.4.0/RegisterUserGuide/MyInvoicesFilters.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

**My Invoice Sort**

- By clicking on the sort of arrow next to Invoice Date, users can sort the invoices by date.
- By default, invoices are sorted in descending order, with the most recent invoices appearing first.

<kbd>
<kbd><img alt="MyInvoicesSort" src="../../../images/22.4.0/RegisterUserGuide/MyInvoicesSort.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

**Download Current Statement**

- Click on Download Current Statement menu to download Current Open Invoices in CSV format.

<kbd>
<kbd><img alt="DownloadCurrentStatement" src="../../../images/22.4.0/RegisterUserGuide/DownloadCurrentStatement.png"></kbd>
</kbd>

<kbd>
<kbd><img alt="DownloadCurrentStatementExcel" src="../../../images/22.4.0/RegisterUserGuide/DownloadCurrentStatementExcel.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

**Email Document**

- Select one or multiple invoices and click on Send Email icon.
- The user will be displayed with a success message.

<kbd>
<kbd><img alt="EmailDocument" src="../../../images/22.4.0/RegisterUserGuide/EmailDocument.png"></kbd>
</kbd>

<kbd>
<kbd><img alt="EmailDocumentScuess" src="../../../images/22.4.0/RegisterUserGuide/EmailDocumentScuess.png"></kbd>
</kbd>

- The documents are sent email through Infrocloudsite and Customer portal also (as configured in back end).

<kbd>
<kbd><img alt="CustomerPortalMail" src="../../../images/22.4.0/RegisterUserGuide/CustomerPortalMail.png"></kbd>
</kbd>

<kbd>
<kbd><img alt="InfroM3Mail" src="../../../images/22.4.0/RegisterUserGuide/InfroM3Mail.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

**Document Download in Invoice History**

- Click on the PDF icon on left side of an invoice to download customer invoice document.
- Document(s) will be downloaded and opened in new tab(s).

When no document is available for the selected invoice, following message is displayed" No Documents available".

<kbd>
<kbd><img alt="NoDocuments" src="../../../images/22.4.0/RegisterUserGuide/NoDocuments.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "my-orders"> </div>

# **My Orders**

- My Orders tab displays the customer's order information – Order number, Customer number, Customer Name, PO/Reference, Order Date and Order Status, Delivery.
- Ten order entries are displayed per page.

<kbd>
<kbd><img alt="MyOrders" src="../../../images/22.4.0/RegisterUserGuide/MyOrders.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

**My Order Search**

- Search by Po reference.
- Search by Order Date.

<kbd>
<kbd><img alt="MyOrdersSearch" src="../../../images/22.4.0/RegisterUserGuide/MyOrdersSearch.png"></kbd>
</kbd>

**My Order Filter**

The user can filter orders based on the status of invoices.

- All Orders
- Open Orders
- Fully Invoiced Orders

<kbd>
<kbd><img alt="MyOrdersFilter" src="../../../images/22.4.0/RegisterUserGuide/MyOrdersFilter.png"></kbd>
</kbd>

**My Order Sort**

- By clicking on the sort of arrow next to Order Date, users may sort the orders by date.
- By default, orders are sorted in descending order, with the most recent orders appearing first.

<kbd>
<kbd><img alt="MyOrdersSort" src="../../../images/22.4.0/RegisterUserGuide/MyOrdersSort.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

**Email Order Confirmation Document**

- Select one or multiple Orders and click on Send Email icon
- The user will be displayed with a success message.

<kbd>
<kbd><img alt="MyOrdersEmail" src="../../../images/22.4.0/RegisterUserGuide/MyOrdersEmail.png"></kbd>
</kbd>

<kbd>
<kbd><img alt="MyOrdersDocumentsSent" src="../../../images/22.4.0/RegisterUserGuide/MyOrdersDocumentsSent.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

**Document Download in Order History**

- Click on the PDF icon on left side of an order to download Order Confirmation document.
- Document(s) will be downloaded and opened in new tab(s).

<kbd>
<kbd><img alt="MyOrdersDocumentsNewTab" src="../../../images/22.4.0/RegisterUserGuide/MyOrdersDocumentsNewTab.png"></kbd>
</kbd>

When no document is available for the selected order, following message is displayed.

<kbd>
<kbd><img alt="MyOrdersNoDoc" src="../../../images/22.4.0/RegisterUserGuide/MyOrdersNoDoc.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

**Delivery Document Download**

- Click on the truck icon on right corner of order history page.
- Click on the PDF icon next to delivery number
- Document(s) will be downloaded and opened in new tab(s)

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

**View Order Shipment information**

- Click on the truck icon on right corner of order history page.
- View the order shipment details such as Shipment number, delivery number, forwarding agent etc.

<kbd>
<kbd><img alt="ShipmentDetails" src="../../../images/22.4.0/RegisterUserGuide/ShipmentDetails.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "sign-out"> </div>

# **Sign Out**

- Click on the human ion on right corner.
- Select Sign Out from the dropdown menu.
- The user will be redirected to the main page in 5 seconds after successfully signing out.

<kbd>
<kbd><img alt="SignOut" src="../../../images/22.4.0/RegisterUserGuide/SignOut.png"></kbd>
</kbd>

<kbd>
<kbd><img alt="SignedOut" src="../../../images/22.4.0/RegisterUserGuide/SignedOut.png"></kbd>
</kbd>

<kbd>
<kbd><img alt="LoginPage" src="../../../images/22.4.0/RegisterUserGuide/LoginPage.png"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>