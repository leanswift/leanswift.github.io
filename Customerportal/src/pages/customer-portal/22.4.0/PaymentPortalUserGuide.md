![](RackMultipart20230128-1-rgl241_html_8e85754fa92f0167.jpg)

# **Version 22.4.0- User Manual - Payment Portal - User**

# Table of contents

- [**Version 22.4.0- User Manual - Payment Portal - User**](#version-2240--user-manual---payment-portal---user)
- [**Table of Contents**](#table-of-contents)
- [**Overview**](#overview)
- [**Architecture**](#architecture)
- [**User Guide for Payment Module of Customer Portal – Front End User**](#user-guide-for-payment-module-of-customer-portal--front-end-user)

# **Overview**

LeanSwift Customer Portal is a customer self-service web portal that enables users to get instance access to information about their orders, invoices and payments. With additional add-ons, uses can also make e-payments directly via the portal. It is seamlessly integrated with Infor M3 CloudSuite using ION. Customer Portal offers a single point of access to structured information about customer transactions and self-service functionality such as pay invoices, user management and much more.

The Payment Portal module is an add-on for Customer Portal which provides customers the ability to make payments for orders and invoices via the portal. The first version of this module uses CyberSource as the payment gateway and provides support for Credit Card payments.

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/add-ons/payment-portal/usermanual-paymentportal-user.html#toc)

# **Architecture**

![](RackMultipart20230128-1-rgl241_html_47799d23ad036281.jpg)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/add-ons/payment-portal/usermanual-paymentportal-user.html#toc)

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

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/add-ons/payment-portal/usermanual-paymentportal-user.html#toc)

**Point Of Contact**

This document and the software it describes are provided by LeanSwift Solutions Inc. For additional information regarding support, licensing, functionality etc. please contact LeanSwift Solutions Inc. via contact form at http://www.leanswift.com or email info@leanswift.com.

# **User Guide for Payment Module of Customer Portal – Front End User**

**Login**

- To login to the Customer portal Payment module, the front end user can login to Customer Portal – Select customer – Click on Payments.

![](RackMultipart20230128-1-rgl241_html_fb3e3b070ab2ba38.png)

![](RackMultipart20230128-1-rgl241_html_4bb362e2f4e9ae21.jpg)

![](RackMultipart20230128-1-rgl241_html_ffe1575f2d265404.jpg)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/add-ons/payment-portal/usermanual-paymentportal-user.html#toc)

**Pay Invoices**

- Customer Portal Front end users can pay their invoices from Payment module - Pay Invoices.
- Selecting Pay Invoices, displays all open invoices of the customer.

![](RackMultipart20230128-1-rgl241_html_223419194b0e960f.jpg)

- User can utilize Pagination option to navigate and identify the open invoice.

![](RackMultipart20230128-1-rgl241_html_71173a83cb7105ad.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/add-ons/payment-portal/usermanual-paymentportal-user.html#toc)

**Invoice Classification**

- Credit Invoices
  - Credit Invoices are displayed with negative amount due, also for easy identification they are displayed along with the orange colour alert symbol next to Amount due.

![](RackMultipart20230128-1-rgl241_html_3cabf2a3ead9d700.jpg)

- Invoices after Discount
  - Invoices with discount are displayed with the discounted rate and for ease of identification, displayed with green colour alert symbol next to Amount due.
  - Discount rates are applied on the outstanding amount.

![](RackMultipart20230128-1-rgl241_html_4b821d66f332e88a.jpg)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/add-ons/payment-portal/usermanual-paymentportal-user.html#toc)

**Apply Credits**

- Any open invoice can be paid by applying credits.
- Customer Portal User can select payment methods as Apply Credits while making payment.

![](RackMultipart20230128-1-rgl241_html_f2790354711accb1.jpg)

- Full Payment via Credits
  - Users can select the invoice to be paid.
  - Click on Apply Credit.
  - The system runs through defined algorithms, identifies possible invoice with credit or their combinations, that can be applied for the given invoice.
  - Users can review the Gross Total, Credits and Total Payment details displayed.
    - Gross total – Amount due for the invoice.
    - Credits – Amount of Credits applied.
    - Total Payment – Remaining payment required after credit adjustments.
  - Users can navigate using pagination to identify the Credits applied invoices, which are selected by system.
  - If the invoice requires more amount than Credits, or the user prefers to pay partially from Credit and remaining from other payment methods, user can select/deselect the credits applied automatically by system.

![](RackMultipart20230128-1-rgl241_html_f85130b24530fe55.png)

- Click on Process Payment.

![](RackMultipart20230128-1-rgl241_html_861b89f4228d9aa6.jpg)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/add-ons/payment-portal/usermanual-paymentportal-user.html#toc)

**Process Payment**

- When the user clicks on Process Payment:
  - If Total Payment due is zero, the credits are applied directly.
  - If there is an amount to be paid against total Payment, clicking on process payment takes the user to the payment screen, with other payment options.

![](RackMultipart20230128-1-rgl241_html_86e7f6e8145abf1c.jpg)

- In case the credits are higher than required total payment, the system automatically debits only the required amount due from the credit invoice.
- In the given example, we can find the balance amount in the credit invoice is $118.03, after applying credit.

![](RackMultipart20230128-1-rgl241_html_15be2c97c6ab9e3c.jpg)

- In case of multiple credits also, the credit invoice is updated with its amount due, after successfully applying credit and making payment for the invoice.

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/add-ons/payment-portal/usermanual-paymentportal-user.html#toc)

**Multiple Invoice Payment**

- Users can perform multiple invoice payments.
- Select multiple invoices, apply credits, verify Gross total, Credits and Total payments and proceed to Process Payment.

![](RackMultipart20230128-1-rgl241_html_418b941dd88501c1.jpg)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/add-ons/payment-portal/usermanual-paymentportal-user.html#toc)

**Partial Invoice Payment**

- Users can perform partial payment towards an invoice or group of invoices.
- Select invoice, type the amount preferred to pay, in the Payment Amt field.
- Select the Reason/Comment from the dropdown list.
- Apply required credits if any, verify Gross total, Credits and Total payments.

![](RackMultipart20230128-1-rgl241_html_a2ed846ff87391d2.jpg)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/add-ons/payment-portal/usermanual-paymentportal-user.html#toc)

**Fully Invoiced Payment**

- Fully Invoiced payments can be viewed under the Invoices tab in the Customer Portal.

**Remove Credits**

- To remove applied credits prior to payment, users can click on Remove Credits.

![](RackMultipart20230128-1-rgl241_html_d634bcf533edf104.jpg)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/add-ons/payment-portal/usermanual-paymentportal-user.html#toc)

**Pay on Account**

- Users can pay for open orders also from the portal via the "Pay on Account" tab, thereby creating credit invoices against their account.
- Selecting Pay on Account, displays all open orders of the customer.

![](RackMultipart20230128-1-rgl241_html_98c0fc8428ce22db.jpg)

- User can select the order, clicking on process payment takes the user to the payment screen, with other payment options.

![](RackMultipart20230128-1-rgl241_html_34cd2d10db29cc1c.jpg)

- On successful pay on account, credit Invoice is created for the amount paid and can be viewed in the Pay Invoices tab.

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/add-ons/payment-portal/usermanual-paymentportal-user.html#toc)

**On-demand Synchronization**

- Missing Invoices
  - Missing data for invoices option is accessible under Payments tab when Invoice/Order Sync Roles is enabled for the customer M3 User Role.

![](RackMultipart20230128-1-rgl241_html_b912c3caf25f3a2a.png)

- Clicking on Missing data, takes the user to screen, where the user can mention document number and run sync job or run by default for 3 days.
  - If no document number is mentioned and the submit button is clicked, invoices from the last 3 days will get synchronized.
  - If the document number is mentioned, the specific invoice alone will get synchronized with M3.
  - Can enter multiple document numbers separated by comma. Sync from M3 will be performed for the specified invoices alone.

![](RackMultipart20230128-1-rgl241_html_77ab7466a987d4ae.png)

- Status of the sync job will be displayed in the display message space of Customer Portal.

![](RackMultipart20230128-1-rgl241_html_cc5b27d67c4a4e32.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/add-ons/payment-portal/usermanual-paymentportal-user.html#toc)

**Payment Process**

**Payment Method**

- Click on proceed payment for both cases pay invoices and pay on account, the user is taken to payment screen with other payment method options.

![](RackMultipart20230128-1-rgl241_html_59f5f5729b5e2ed5.png)

- Select the preferred Payment method. Credit Card – MasterCard/Visa/Amex/Discover

![](RackMultipart20230128-1-rgl241_html_566b9670bff85f4d.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/add-ons/payment-portal/usermanual-paymentportal-user.html#toc)

**Payment Details**

- In the Payment process, once the user selects the payment method, the payment information screen is displayed to enter Card type, number and expiry details.
- Click on change payment method, system takes the user to payment method screen.

![](RackMultipart20230128-1-rgl241_html_5f892ad0cd325495.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/add-ons/payment-portal/usermanual-paymentportal-user.html#toc)

**Review your order**

- Enter payment details and click next, the payment review screen appears.
- Users can review all payment details, from billing address, card type, number, expiry or edit the details.
- Click on Pay to proceed with payment.

![](RackMultipart20230128-1-rgl241_html_837dff448aec928a.png)

**Receipt**

- When a payment is completed successfully, the transaction reference and payment status are presented on the Customer Portal's message display space.

![](RackMultipart20230128-1-rgl241_html_c410014da4ae0e79.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/add-ons/payment-portal/usermanual-paymentportal-user.html#toc)

**Cancel Payment**

- To cancel the payment process, the user can click on Cancel order, and confirm to cancel.

![](RackMultipart20230128-1-rgl241_html_68580d0666cb8412.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/add-ons/payment-portal/usermanual-paymentportal-user.html#toc)

**General Guidelines**

- Payment processing is enabled only on Google Chrome and Safari (on Mac).
- Users can view responses/error messages from the system in the message display space of Customer Portal.
- Payment by Credit Card only is supported by the Customer portal as of now.

![](RackMultipart20230128-1-rgl241_html_566e6c85ba75bccf.png)

[↥ **Go to Top**](https://leanswift.github.io/Customerportal/src/pages/add-ons/payment-portal/usermanual-paymentportal-user.html#toc)

![Shape1](RackMultipart20230128-1-rgl241_html_8364f73a6574c228.gif)
