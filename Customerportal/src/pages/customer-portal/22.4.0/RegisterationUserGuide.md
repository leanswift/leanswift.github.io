![](RackMultipart20230128-1-ji83ln_html_257c7bafda5feb3e.jpg)

# **New Version 22.4.0 - User Manual – LeanSwift Customer Portal - User**

# Table of contents

- [**New Version 22.4.0 - User Manual – LeanSwift Customer Portal - User**](#new-version-2240---user-manual--leanswift-customer-portal---user)
- [**Table of contents**](#table-of-contents)
- [**User Manual - Customer Portal - Front end User**](#user-manual---customer-portal---front-end-user)
- [**Overview**](#overview)
- [**Architecture**](#architecture)
- [**Registration**](#registration)
- [**Login**](#login)
- [**Forgot Your Password**](#forgot-your-password)
- [**Switch Customer**](#switch-customer)
- [**Download Sub Accounts Info**](#download-sub-accounts-info)
- [**My Account**](#my-account)
- [**My Invoices**](#my-invoices)
- [**My Orders**](#my-orders)
- [**Sign Out**](#sign-out)

# **Overview**

LeanSwift Customer Portal is a customer self-service web portal that enables users to get instance access to information about their orders, invoices and payments. With additional add-ons, uses can also make e-payments directly via the portal. It is seamlessly integrated with Infor M3 CloudSuite using ION. Customer Portal offers a single point of access to structured information about customer transactions and self-service functionality such as pay invoices, user management and much more.

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#toc)

# **Architecture**

![](RackMultipart20230128-1-ji83ln_html_1f9f109cb2394308.jpg)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#toc)

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

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#toc)

**Point Of Contact**

This document and the software it describes are provided by LeanSwift Solutions Inc. For additional information regarding support, licensing, functionality etc. please contact LeanSwift Solutions Inc. via contact form at http://www.leanswift.com or email info@leanswift.com.

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#toc)

# **Registration**

**Registration for Internal Customer (M3 User)**

- Internal customers (M3 users) can utilise their Infor OS (Mingle) credentials to access the Customer Portal without having to sign up.
- The password box is disabled whenever an internal user inputs an email address with a valid internal domain.

![](RackMultipart20230128-1-ji83ln_html_656353c85e48fc9.png)

- By clicking Sign in, the front-end user is redirected to Infor OS to authenticate their credentials.
  - Note: The user must use the same credentials to login to Infor OS as used to log in to the customer portal.

![](RackMultipart20230128-1-ji83ln_html_5e80246e0dd8465.png)

- Following successful validation in the Infor OS, the system generates a Request for Approval, which includes the requester's information and the choice to grant or deny access.

![](RackMultipart20230128-1-ji83ln_html_8a42b9e970048083.png)

- Once the internal user has authorised access, the user gets signed into Customer Portal.

Note: After the initial successful login, the Infor OS user id is created in the Customer Portal Database.

![](RackMultipart20230128-1-ji83ln_html_f947d7680b12a8d2.png)

- If a user is unable to log in to Infor OS, they can utilise Forgot password to reset their password or contact us to contact the team.

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#toc)

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

![](RackMultipart20230128-1-ji83ln_html_446580919a6201ab.png)

- As the user enters the above details, Customer number, Invoice/Order Number and Invoice/Order amount is validated.
- A STAT ID may or may not be associated with the client in M3. Behaviour of the portal is slightly different based on whether the customer has a STAT ID or not.
- The first customer to be associated with a new account will be an Admin user for the account and will have full access.
- All other users will have limited access on the site, until the admin provides additional privileges.

![](RackMultipart20230128-1-ji83ln_html_a498b23f2f5ea3e2.png)

- Following successful registration, an email with a link for account verification and password creation is sent to the registered email address.

Note: Please check the Junk or Spam folder in case this mail does not arrive within few minutes.

![](RackMultipart20230128-1-ji83ln_html_9a517e1700c3890b.jpg)

![](RackMultipart20230128-1-ji83ln_html_ab5d134b539325d3.png)

- The link in the email directs the user to the password creation screen, where they can create a new password in accordance with the [password policy](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#Password_Policy).

![](RackMultipart20230128-1-ji83ln_html_4b6749f161543084.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#toc)

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

![](RackMultipart20230128-1-ji83ln_html_5dce4e6200e596c3.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#toc)

**General guidelines/help**

- The following are some of the possible mistakes that can occur when enrolling a new user.
  - Customer number should not present in the Customer Portal Database.
  - The requested order/invoice does not match.
    - The combination of Customer number, Invoice number and Amount did not match in M3 system and Customer Portal Database.
  - Registration is not allowed for this customer.
    - Customer Number is part of a restricted user group that is denied access to the Customer portal.
  - There is already an account with this email address. If you are sure that it is your email address, [click here](https://cpqa.leanswiftdev.net/customer/account/forgotpassword/) to get your password and access your account.

![](RackMultipart20230128-1-ji83ln_html_48bb69b954b00555.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#toc)

# **Login**

- The user logs in to Customer Portal using their registered credentials.

![](RackMultipart20230128-1-ji83ln_html_f0e1ba367531a99b.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#toc)

**Login**

- Successful login takes the front-end user to the Customer Portal main screen, which displays a list of customers.
- The user can choose a customer and view their information.
- We can logout to that customer while we are opening a particular customer.

![](RackMultipart20230128-1-ji83ln_html_b6b84b58fa8a6db.png)

![](RackMultipart20230128-1-ji83ln_html_8acfa775027a5a.jpg)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#toc)

**User Privileges**

- Based on the user privileges of the external user, the options are enabled.

| **External User** | **My Account** | **Switch Accounts** | **Download Sub Accounts Info** |
| --- | --- | --- | --- |
| Customer with STAT ID + Account Admin User | Yes | Yes | Yes |
| --- | --- | --- | --- |
| Customer with STAT ID + Account Normal User | Yes | Yes | No |
| Customer without STAT ID | Yes | No | No |

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#toc)

# **Forgot Your Password**

- To reset the password, user can click on forgot password button in the home screen of Customer Portal.

![](RackMultipart20230128-1-ji83ln_html_84031d82467eb5df.jpg)

- The user can provide a registered email id and request a reset password.

![](RackMultipart20230128-1-ji83ln_html_70681ab40d480977.png)

- After entering email id and clicking on Reset My password, it will take to Customer portal home page with message displayed " **If there is an account associated with challa.anjana@leanswift.com you will receive an email with a link to reset your password.**"

![](RackMultipart20230128-1-ji83ln_html_1641647b84ed82c8.png)

- The password reset link will be sent to the user's email address.

![](RackMultipart20230128-1-ji83ln_html_3ef017692ed90452.png)

- The link redirects the user to the password reset page, where they can create a new password that meets the[ password policy](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#_heading=h.17dp8vu).

![](RackMultipart20230128-1-ji83ln_html_5f110b7420308705.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#toc)

# **Switch Customer**

- The Switch Customer option on the right side human icon menu is enabled for users with [privileges](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#_heading=h.35nkun2) to view other customer account details.

![](RackMultipart20230128-1-ji83ln_html_b635a770eacd5e9c.jpg)

- Once the user clicks on the switch customer option, a list of the user's customers are displayed.
- To view details about a customer, the user must first select the customer.

![](RackMultipart20230128-1-ji83ln_html_ad0dc7f1f584cc7f.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#toc)

# **Download Sub Accounts Info**

- Users having Sub Accounts, i.e. Account Admin Users, have the option to download Sub Accounts Info.

![](RackMultipart20230128-1-ji83ln_html_8b8b6c3a9b80a6a5.jpg)

- Click on Download Sub Accounts Info Option, to download the details of sub accounts in CSV format.
  - Name - Name of the customer.
  - Email - Email id of the customer.
  - Allowed Sections - The sections allowed to the user - View Order History, View Invoice History, View Pay Invoices.
  - Make Payment - Provides information on whether the customer has privileges to make a payment - Yes/No.

![](RackMultipart20230128-1-ji83ln_html_15f8faf963b1045.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#toc)

# **My Account**

- The My Account menu shows the selected customer's account information.

![](RackMultipart20230128-1-ji83ln_html_110d17724b565611.jpg)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#toc)

**My Addresses**

- The My Addresses option displays the customer's invoice address as well as any extra addresses.

![](RackMultipart20230128-1-ji83ln_html_7774424f64540c4e.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#toc)

# **My Invoices**

- The customer's invoice data are displayed in the Invoice tab: Invoice number, Order number, Customer number, Customer PO Ref, Invoice Date, Invoice Amount, and Status.
- Ten invoice entries are displayed per page.

![](RackMultipart20230128-1-ji83ln_html_d0ec1beabd16c376.jpg)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#toc)

**My Invoice Search**

- Search by Invoice Number or Po reference.
- Search by Invoice Date
  - The user can view Invoices by selecting start date (Year 2018) and end date (Current year).

![](RackMultipart20230128-1-ji83ln_html_2fe078792de2b1.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#toc)

**My Invoice Filter**

- The user can filter invoices based on the status of invoices.
  - Open Invoices
  - Paid Invoices
  - All Invoices

![](RackMultipart20230128-1-ji83ln_html_588fa529566dbfb.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#toc)

**My Invoice Sort**

- By clicking on the sort of arrow next to Invoice Date, users can sort the invoices by date.
- By default, invoices are sorted in descending order, with the most recent invoices appearing first.

![](RackMultipart20230128-1-ji83ln_html_bd4ba52e4ebde52.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#toc)

**Download Current Statement**

- Click on Download Current Statement menu to download Current Open Invoices in CSV format.

![](RackMultipart20230128-1-ji83ln_html_b9acf5c15dfd887d.jpg)

![](RackMultipart20230128-1-ji83ln_html_30d5457ddad2e16.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#toc)

**Email Document**

- Select one or multiple invoices and click on Send Email icon.
- The user will be displayed with a success message.

![](RackMultipart20230128-1-ji83ln_html_4054aa0ab26a142f.png)

![](RackMultipart20230128-1-ji83ln_html_684da342c45b56d2.png)

- The documents are sent email through Infrocloudsite and Customer portal also (as configured in back end).

![](RackMultipart20230128-1-ji83ln_html_18fdd78e27d77b11.png)

![](RackMultipart20230128-1-ji83ln_html_c455a9ae7dbec5ff.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#toc)

**Document Download in Invoice History**

- Click on the PDF icon on left side of an invoice to download customer invoice document.
- Document(s) will be downloaded and opened in new tab(s).

When no document is available for the selected invoice, following message is displayed" No Documents available".

![](RackMultipart20230128-1-ji83ln_html_fe5c06c2e0bcac0b.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#toc)

# **My Orders**

- My Orders tab displays the customer's order information – Order number, Customer number, Customer Name, PO/Reference, Order Date and Order Status, Delivery.
- Ten order entries are displayed per page.

![](RackMultipart20230128-1-ji83ln_html_748900a1c7612a7e.jpg)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#toc)

**My Order Search**

- Search by Po reference.
- Search by Order Date.

![](RackMultipart20230128-1-ji83ln_html_f45eda8bffecc1a5.png)

**My Order Filter**

The user can filter orders based on the status of invoices.

- All Orders
- Open Orders
- Fully Invoiced Orders

![](RackMultipart20230128-1-ji83ln_html_3c9bd5d7d0cc881a.png)

**My Order Sort**

- By clicking on the sort of arrow next to Order Date, users may sort the orders by date.
- By default, orders are sorted in descending order, with the most recent orders appearing first.

![](RackMultipart20230128-1-ji83ln_html_aabb547c1301293c.jpg)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#toc)

**Email Order Confirmation Document**

- Select one or multiple Orders and click on Send Email icon
- The user will be displayed with a success message.

![](RackMultipart20230128-1-ji83ln_html_7c48b55821fdeff9.png)

![](RackMultipart20230128-1-ji83ln_html_60da971a25ac33a0.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#toc)

**Document Download in Order History**

- Click on the PDF icon on left side of an order to download Order Confirmation document.
- Document(s) will be downloaded and opened in new tab(s).

![](RackMultipart20230128-1-ji83ln_html_5af2c3c44ac4434c.png)

When no document is available for the selected order, following message is displayed.

![](RackMultipart20230128-1-ji83ln_html_118a46f5bb1bbfcc.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#toc)

**Delivery Document Download**

- Click on the truck icon on right corner of order history page.
- Click on the PDF icon next to delivery number
- Document(s) will be downloaded and opened in new tab(s)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#toc)

**View Order Shipment information**

- Click on the truck icon on right corner of order history page.
- View the order shipment details such as Shipment number, delivery number, forwarding agent etc.

![](RackMultipart20230128-1-ji83ln_html_80606fff4736d013.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#toc)

# **Sign Out**

- Click on the human ion on right corner.
- Select Sign Out from the dropdown menu.
- The user will be redirected to the main page in 5 seconds after successfully signing out.

![](RackMultipart20230128-1-ji83ln_html_cc968a3ad7236eb8.png)

![](RackMultipart20230128-1-ji83ln_html_862b820931767fae.png)

![](RackMultipart20230128-1-ji83ln_html_aed8ef85542b6c05.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/customer-portal/21.2.0/usermanual-customerportal-user.html#toc)

![Shape1](RackMultipart20230128-1-ji83ln_html_8364f73a6574c228.gif)

Internal to Wipro
