![](https://github.com/leanswift/leanswift.github.io/blob/LCP-147/Customerportal/src/images/customer-portal/front-end-user/CP_banner.jpg)


# Version 1.1.0 - User Manual - Payment Portal - User

# Table of Contents

<div id = "toc"></div>

- [Overview](#Overview)
	- [Architecture](#Architecture)
    - [Features](#Features)
    - [Point Of Contact](#Point_Of_Contact)
- [User Guide for Payment Module of Customer Portal – Front End User](#User_Guide)
    - [Login](#Login)
    - [Pay Invoices](#Pay_Invoices)
        - [Invoice Classification](#Invoice_Classification)
        - [Apply Credits](#Apply_Credits)
        - [Process Payment](#Process_Payment)
        - [Multiple Invoice Payment](#Multiple_Invoice_Payment)
        - [Partial Invoice Payment](#Partial_Invoice_Payment)
        - [Fully Invoiced Payment](#Fully_Invoiced_Payment)
        - [Remove Credits](#Remove_Credits)
	- [Pay on Account](#Pay_on_Account)
	- [ On-demand Synchronization](#On_demand_Synchronization)
	- [Payment Process](#Payment_Process)
        - [Payment Method](#Payment_Method)
        - [Payment Details](#Payment_Details)
        - [Review your order](#Review_your_order)
        - [Receipt](#Receipt)
    - [Cancel Payment](#Cancel_Payment)
    - [General Guidelines](#General_Guidelines)

<div id = "Overview"> </div>

# Overview

LeanSwift Customer Portal is a customer self-service web portal that enables users to get instance access to information about their orders, invoices and payments. With additional add-ons, uses can also make e-payments directly via the portal. It is seamlessly integrated with Infor M3 CloudSuite using ION. Customer Portal offers a single point of access to structured information about customer transactions and self-service functionality such as pay invoices, user management and much more.

The Payment Portal module is an add-on for Customer Portal which provides customers the ability to make payments for orders and invoices via the portal. The first version of this module uses CyberSource as the payment gateway and provides support for Credit Card payments.

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "Architecture"></div>

# Architecture

<kbd>
<kbd><img alt="CustomerPortal_Architecture" src="../../../images/add-ons/payment-portal/payment-user/CustomerPortal_Architecture.jpg"></kbd>
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


<div id = "User_Guide"> </div> 

# User Guide for Payment Module of Customer Portal – Front End User

<div id = "Login"> </div> 

## Login
- To login to the Customer portal Payment module, the front end user can login to Customer Portal – Select customer – Click on Payments.

<kbd>
<kbd><img alt="CustomerPortal-Login" src="../../../images/add-ons/payment-portal/payment-user/CustomerPortal-Login.PNG"></kbd>
</kbd>

<kbd>
<kbd><img alt="CustomerPortal-SelectCustomer" src="../../../images/add-ons/payment-portal/payment-user/CustomerPortal-SelectCustomer.PNG"></kbd>
</kbd>

<kbd>
<kbd><img alt="CustomerPortal-PaymentHome" src="../../../images/add-ons/payment-portal/payment-user/CustomerPortal-PaymentHome.PNG"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "Pay_Invoices"> </div> 

## Pay Invoices
- Customer Portal Front end users can pay their invoices from Payment module - Pay Invoices.
- Selecting Pay Invoices, displays all open invoices of the customer.

<kbd>
<kbd><img alt="CustomerPortal-PayInvoicesButton" src="../../../images/add-ons/payment-portal/payment-user/CustomerPortal-PayInvoicesButton.PNG"></kbd>
</kbd>

- User can utilize Pagination option to navigate and identify the open invoice.

<kbd>
<kbd><img alt="CustomerPortal-PayInvoices-Pagination" src="../../../images/add-ons/payment-portal/payment-user/CustomerPortal-PayInvoices-Pagination.PNG"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "Invoice_Classification"> </div> 

### Invoice Classification
- Credit Invoices
    - Credit Invoices are displayed with negative amount due, also for easy identification they are displayed along with the Orange colour alert symbol next to Amount due.

<kbd>
<kbd><img alt="CustomerPortal-PaymentsCreditNoteInvoice" src="../../../images/add-ons/payment-portal/payment-user/CustomerPortal-PaymentsCreditNoteInvoice.PNG"></kbd>
</kbd>

- Invoices after Discount
    - Invoices with discount are displayed with the discounted rate and for ease of identification, displayed with Green colour alert symbol next to Amount due.
    - Discount rates are applied on the outstanding amount. 

<kbd>
<kbd><img alt="CustomerPortal-Payments-DiscountInvoice" src="../../../images/add-ons/payment-portal/payment-user/CustomerPortal-Payments-DiscountInvoice.PNG"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "Apply_Credits"> </div> 

### Apply Credits
- Any open invoice can be paid by applying credits.
- Customer Portal User can select payment methods as Apply Credits while making payment.

<kbd>
<kbd><img alt="CustomerPortal-PayInvoices-ApplyCredits" src="../../../images/add-ons/payment-portal/payment-user/CustomerPortal-PayInvoices-ApplyCredits.PNG"></kbd>
</kbd>

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

<kbd>
<kbd><img alt="CustomerPortal-PayInvoices-Pagination" src="../../../images/add-ons/payment-portal/payment-user/CustomerPortal-PayInvoices-Pagination.PNG"></kbd>
</kbd>

- Click on Process Payment.

<kbd>
<kbd><img alt="CustomerPortal-PayInvoices-ProcessPayment" src="../../../images/add-ons/payment-portal/payment-user/CustomerPortal-PayInvoices-ProcessPayment.PNG"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "Process_Payment"> </div> 

### Process Payment
- When the user clicks on Process Payment:
  - If Total Payment due is zero, the credits are applied directly.
  - If there is an amount to be paid against total Payment, clicking on process payment takes the user to the payment screen, with other payment options.

<kbd>
<kbd><img alt="CustomerPortal-PayInvoices-ApplyCreditBalance" src="../../../images/add-ons/payment-portal/payment-user/CustomerPortal-PayInvoices-ApplyCreditBalance.PNG"></kbd>
</kbd>

- In case the credits are higher than required total payment, the system automatically debits only the required amount due from the credit invoice. 
- In the given example, we can find the balance amount in the credit invoice is Rs.5.75, after applying credit.

<kbd>
<kbd><img alt="CustomerPortal-PayInvoices-ApplyCreditBalance1" src="../../../images/add-ons/payment-portal/payment-user/CustomerPortal-PayInvoices-ApplyCreditBalance1.PNG"></kbd>
</kbd>

- In case of multiple credits also, the credit invoice is updated with its amount due, after successfully applying credit and making payment for the invoice. 

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "Multiple_Invoice_Payment"> </div> 

### Multiple Invoice Payment
- Users can perform multiple invoice payments. 
- Select multiple invoices, apply credits, verify Gross total, Credits and Total payments and proceed to Process Payment.

<kbd>
<kbd><img alt="CustomerPortal-PayInvoices-MultiInvoice" src="../../../images/add-ons/payment-portal/payment-user/CustomerPortal-PayInvoices-MultiInvoice.PNG"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "Partial_Invoice_Payment"> </div> 

### Partial Invoice Payment
- Users can perform partial payment towards an invoice or group of invoices. 
- Select invoice, type the amount preferred to pay, in the Payment Amt field.
- Select the Reason/Comment from the dropdown list.
- Apply required credits if any, verify Gross total, Credits and Total payments.

<kbd>
<kbd><img alt="CustomerPortal-PayInvoice-PartialPayment" src="../../../images/add-ons/payment-portal/payment-user/CustomerPortal-PayInvoice-PartialPayment.PNG"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "Fully_Invoiced_Payment"> </div> 

### Fully Invoiced Payment
- Fully Invoiced payments can be viewed under the Invoices tab in the Customer Portal.

<div id = "Remove_Credits"> </div> 

### Remove Credits
- To remove applied credits prior to payment, users can click on Remove Credits.

<kbd>
<kbd><img alt="CustomerPortal-PayInvoices-RemoveCredits" src="../../../images/add-ons/payment-portal/payment-user/CustomerPortal-PayInvoices-RemoveCredits.PNG"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "Pay_on_Account"> </div> 

## Pay on Account

- Users can pay for open orders also from the portal via the “Pay on Account” tab, thereby creating credit invoices against their account.
- Selecting Pay on Account, displays all open orders of the customer.

<kbd>
<kbd><img alt="CustomerPortal-PayOnAccountButton" src="../../../images/add-ons/payment-portal/payment-user/CustomerPortal-PayOnAccountButton.PNG"></kbd>
</kbd>

- User can select the order, clicking on process payment takes the user to the payment screen, with other payment options.

<kbd>
<kbd><img alt="CustomerPortal-PayOnAccountProcessPayment" src="../../../images/add-ons/payment-portal/payment-user/CustomerPortal-PayOnAccountProcessPayment.PNG"></kbd>
</kbd>

- On successful pay on account, credit Invoice is created for the amount paid and can be viewed in the Pay Invoices tab.

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "On_demand_Synchronization"> </div> 

## On-demand Synchronization
- Missing Invoices
	- Missing data for invoices option is accessible under Payments tab when Invoice/Order Sync Roles is enabled for the customer M3 User Role.

<kbd>
<kbd><img alt="CustomerPortal-PaymentPortal-Missingdata" src="../../../images/add-ons/payment-portal/payment-user/CustomerPortal-PaymentPortal-Missingdata.PNG"></kbd>
</kbd>

- Clicking on Missing data, takes the user to screen, where the user can mention document number and run sync job or run by default for 3 days.
    - If no document number is mentioned and the submit button is clicked, invoices from the last 3 days will get synchronized.
    - If the document number is mentioned, the specific invoice alone will get synchronized with M3.
    - Can enter multiple document numbers separated by comma. Sync from M3 will be performed for the specified invoices alone.

<kbd>
<kbd><img alt="CustomerPortal-PaymentPortal-MissingdataDoc" src="../../../images/add-ons/payment-portal/payment-user/CustomerPortal-PaymentPortal-MissingdataDoc.PNG"></kbd>
</kbd>

- Status of the sync job will be displayed in the display message space of Customer Portal.

<kbd>
<kbd><img alt="CustomerPortal-PaymentPortal-MissingdataSuccess" src="../../../images/add-ons/payment-portal/payment-user/CustomerPortal-PaymentPortal-MissingdataSuccess.PNG"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "Payment_Process"> </div> 

## Payment Process

<div id = "Payment_Method"> </div> 

### Payment Method
- Click on proceed payment for both cases pay invoices and pay on account, the user is taken to payment screen with other payment method options.

<kbd>
<kbd><img alt="CustomerPortal-PayOnAccount-Card" src="../../../images/add-ons/payment-portal/payment-user/CustomerPortal-PayOnAccount-Card.PNG"></kbd>
</kbd>

- Select the preferred Payment method. Credit Card – MasterCard/Visa/Amex/Discover

<kbd>
<kbd><img alt="CustomerPortal-PayOnAccount-Selectcardtype" src="../../../images/add-ons/payment-portal/payment-user/CustomerPortal-PayOnAccount-Selectcardtype.PNG"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "Payment_Details"> </div> 

### Payment Details
- In the Payment process, once the user selects the payment method, the payment information screen is displayed to enter Card type, number and expiry details. 
- Click on change payment method, system takes the user to payment method screen.

<kbd>
<kbd><img alt="CustomerPortal-PayOnAccount-PaymentScreen" src="../../../images/add-ons/payment-portal/payment-user/CustomerPortal-PayOnAccount-PaymentScreen.PNG"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "Review_your_order"> </div> 

### Review your order
- Enter payment details and click next, the payment review screen appears.
- Users can review all payment details, from billing address, card type, number, expiry or edit the details.
- Click on Pay to proceed with payment.

<kbd>
<kbd><img alt="CustomerPortal-PayOnAccount-PaymentReview" src="../../../images/add-ons/payment-portal/payment-user/CustomerPortal-PayOnAccount-PaymentReview.PNG"></kbd>
</kbd>

<div id = "Receipt"> </div> 

### Receipt
- When a payment is completed successfully, the transaction reference and payment status are presented on the Customer Portal's message display space.

<kbd>
<kbd><img alt="CustomerPortal-PayOnAccount-PaymentConfirm" src="../../../images/add-ons/payment-portal/payment-user/CustomerPortal-PayOnAccount-PaymentConfirm.PNG"></kbd>
</kbd>

<div id = "Cancel_Payment"> </div> 

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

## Cancel Payment
- To cancel the payment process, the user can click on Cancel order, and confirm to cancel.

<kbd>
<kbd><img alt="CustomerPortal-Payment-CancelOrder" src="../../../images/add-ons/payment-portal/payment-user/CustomerPortal-Payment-CancelOrder.PNG"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>

<div id = "General_Guidelines"> </div> 

## General Guidelines
- Payment processing is enabled only on Google Chrome and Safari (on Mac).
- Users can view responses/error messages from the system in the message display space of Customer Portal.
- Payment by Credit Card only is supported by the Customer portal as of now.


<kbd>
<kbd><img alt="CustomerPortal-PayInvoices-PartialPay-Phone" src="../../../images/add-ons/payment-portal/payment-user/CustomerPortal-PayInvoices-PartialPay-Phone.PNG"></kbd>
</kbd>

<div align="right">
<b>
 <a href="#toc">↥ Go to Top</a>
</b>
</div>




