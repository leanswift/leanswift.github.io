<img alt ="Supplier Portal Banner" src="../../images/pwa/SupplierPortal_Banner.png">

# Version 24.2.0 - User Manual - Invoice - Admin 

This is an Add-on to display a list of Invoices for that Supplier.

<kbd>
<img alt="metrics display" src="../../images/usermanual/invoice-settings.png"> 
</kbd>

- Initial Sync Invoices: Admin can choose whether to display All invoices or Open invoices during the first-time login of the user.
- From date to fetch invoices: Invoices up to last 6months will only be displayed for the logged in Supplier. Users can choose the date from which Invoices has to be listed. It can be less than 180 days from the current date but not more than that. 
- The Date format must be YYYY/MM/DD. If no date is chosen, default date will be 180 days behind current date. 
- Note that Logged in User must have permission to view Invoices. 

- The list of filter options can be configured under Leanswift > Supplier Portal > Design/Display > Invoice. 
- Sync.SupplierInvoice bod will be triggered when buyer invoices a PO IN APS100. 
- After completing payment Sync.PayableTransaction bod will be triggered. The paid amount will be updated to the supplier in My Invoices. 
- EXPORTMI/Select/FPLEDG call is made to pull old invoices during 1st time of registration of supplier. 

## **Filters** 

    - **Max filters**: Based on this configuration number o filters can be configured. 
    - **Filter mapping**: In this Filter Attribute, Filter Label, Filter Type, Filter Operations can be mapped. 

<kbd>
<img alt="metrics display" src="../../images/usermanual/invoice-filter-settings.png"> 
</kbd>


