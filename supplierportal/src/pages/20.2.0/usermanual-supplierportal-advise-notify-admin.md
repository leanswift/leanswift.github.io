
![Supplier portal banner](../../../../images/banner-supplier-portal.jpg)

# Version 20.2.0 - Advise/Notify User Manual - Admin User

This Add-on is used to Advise and/or Notify PO lines and should be used along with Supplier Portal

Image

### Can Advise PO before confirm: 
If &quot;Yes&quot; is selected, Advise PO can be done before Confirm PO.

If &quot;No&quot; is selected, Advise PO cannot be performed before Confirm PO is executed.

When the above setting is &quot;No&quot;, PO Lines which are in READY/PRINTED status, that is, PO Line status less than 35 cannot be Advised for Shipment.

### Realtime API call for advise PO:
If &quot;Yes&quot; is selected, API calls will be made in real time. If &quot;No&quot; is selected, API calls are processed via a background job (CRON).

### Cron setting to send Advise PO requests to M3:
Set an expression for CRON to send requests to M3 at fixed intervals

