# Release Notes - Accounts Receivable 8.0.0




## Environment Details

|  **Software Name**  |  **Version**  |
| --- | --- |
| Infor M3 (ST) | 13.4 |
| Infor M3 (MT) | 16.1 |
| Infor H5 SDK version | 2.2.1 |

## Standard Features

All the standard functionalities of Accounts Receivable are supported in v8.0.0, which include the following:

- Invoices
- Basic Data
- Tickler Notes
- Credit Release
- Credit History
- Account Payments
- Cash Payments
- Search
- Order

## Highlights

1. Built from scratch using the latest version of Infor M3 H5 SDK (version 2.2.1)
2. Overall performance improvements
3. PWA support in standalone mode (works only in ST)
4. Compatibility for recent security changes with Infor APIs
5. Performance &amp; stability improvements to Invoice table
  - Much more consistent totals calculation for invoices
  - Invoice table doesn&#39;t load all of the order and discount details like previous versions to improve performance and reduce the number of failures.
  - The following fields are loaded on demand once an invoice has been selected
    1. Order number
    2. Order type
    3. Delivery number
    4. Our reference
    5. Project
    6. PONO
    7. Discount amount
    8. Net amount
    9. Discount date
6. Removed all MDBREADMI calls and instead makes used of EXPORTMI extensively in the following arears

- Invoice Module: For finding discount details
- Invoice Module: For finding order details
- Invoice Module: For finding payment details
- Credit History : For finding payer information and overdue amount
- Cash Payments : For finding cash details
- Cash Payments : For finding extended invoice details
- Cash Payments : For finding payment details
- Basic data : For Finding Overdue amount
- Basic Data,Credit Release,Tickler Notes : For finding Authority Roles across modules.
- Search: Finding Invoices,Orders by searching

7. Support for RMS440MI-AddTickleNote for adding tickler notes on MT



## Important Points to Note

This version does not support the following:

1. Changing Theme from UI
2. Changing Language from UI
3. Changing Wallpaper from UI

## Limitations

1. AR webapp Multi-tenant will not work on Safari browser
2. The results from the following API&#39;s are limited to 1000 records inside the webapp:

- Open Invoices,Paid Invoices
- Payer Information
 Orders,Order lines and Order Charges
- Pricing ,Discount Model and Order Types in Basic Data section.

## GitHub Links

1. [All](https://leanswift.atlassian.net/issues/?jql=project%20%3D%20LHW%20ORDER%20BY%20priority%20DESC)
2. [Bugs](https://leanswift.atlassian.net/issues/?jql=issuetype%20%3D%20Bug%20AND%20project%20%3D%20LHW%20ORDER%20BY%20priority%20DESC)
3. [Story/Task](https://leanswift.atlassian.net/issues/?jql=issuetype%20in%20(Epic%2C%20Story%2C%20Task%2C%20Subtask)%20AND%20project%20%3D%20LHW%20ORDER%20BY%20priority%20DESC)


## Points of Contact

1. [shyam.sathyanathan](mailto:shyam.sathyanathan@leanswift.com)[@leanswift.com](mailto:shyam.sathyanathan@leanswift.com)
2. [backiyalakshmi.r@leanswift.com](mailto:backiyalakshmi.r@leanswift.com)
3. [deepthi.tadikamalla@leanswift.com](mailto:deepthi.tadikamalla@leanswift.com)
4. [srinidhi.narayanan](mailto:srinidhi.narayanan@leanswift.com)[@leanswift.com](mailto:srinidhi.narayanan@leanswift.com)
5. [nrithya.rajagopalan@leanswift.com](mailto:nrithya.rajagopalan@leanswift.com)
