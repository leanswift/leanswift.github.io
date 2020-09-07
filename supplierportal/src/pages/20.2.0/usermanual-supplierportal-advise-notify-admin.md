
![Supplier portal banner](../../../../images/banner-supplier-portal.jpg)

# Version 20.2.0 - Advise/Notify User Manual - Admin

This Add-on is used to Advise and/or Notify PO lines and should be used along with Supplier Portal

# Advise
Image

### Can Advise PO before confirm: 
If &quot;Yes&quot; is selected, Advise PO can be done before Confirm PO.

If &quot;No&quot; is selected, Advise PO cannot be performed before Confirm PO is executed.

When the above setting is &quot;No&quot;, PO Lines which are in READY/PRINTED status, that is, PO Line status less than 35 cannot be Advised for Shipment.

### Realtime API call for advise PO:
If &quot;Yes&quot; is selected, API calls will be made in real time. If &quot;No&quot; is selected, API calls are processed via a background job (CRON).

### Cron setting to send Advise PO requests to M3:
Set an expression for CRON to send requests to M3 at fixed intervals

# Notify

This Add-on is used to Notify PO lines and has to be used along with Supplier Portal and Advise PO.

Image

### Allow Notify Transportation before Advise:
If &quot;Yes&quot; is selected, Notify PO can be done before advise.If &quot;No&quot; is selected, Notify PO cannot be done before advise.

When the above setting is No, POs which are in READY/PRINTED/ASN status i.e PO status less than 40 cannot be Notified.

### Allow Notify Transportation before Confirm: 
If &quot;Yes&quot; is selected, Notify PO can be done before confirm.

If &quot;No&quot; is selected, Notify PO cannot be done before confirm.

When the above setting is No, POs which are in READY/PRINTED status i.e PO status less than 20 cannot be Notified.

### Realtime API call for notify PO:
If &quot;Yes&quot; is selected, API calls are processed realtime. If &quot;No&quot; is selected, API calls are processed via CRON.

### Cron setting to send notify PO requests to M3:
Set an expression for CRON to send requests to M3 at fixed intervals


