![Supplier portal banner](../../../../images/banner-supplier-portal.jpg)

# Version 20.2.0 - Deliveries User Manual - Admin

This is a separate add-on and has to be used alongside Supplier Portal.


&#39;My Deliveries&#39; displays all the Delivery notes of the registered supplier. 

For the first time login, Background job will fetch the delivery data from M3. By default, 180 days old deliveries will be pulled from M3. Days can be changed in the backend configuration but max value is 180 days
Once the old data are pulled, Background job will run based on Timestamp

<kbd>
<img alt="metrics display" src="../../images/usermanual/delivery-setting.png"> 
</kbd>

Filter settings by which deliveries can be filtered in the portal are to be configured in the admin section under Leanswift > Supplier Portal > Design/Display > Deliveries

<kbd>
<img alt="metrics display" src="../../images/usermanual/deliveries-filter-setting.png"> 
</kbd>

Delivery informations are fetched from FGRECL table ( Goods Receipt Lines) using ExportMI/ Select query during the first time login. Below are the fields fetched F2CONO (company), F2LMTS (Last modified time stamp), F2SUNO (supplier number), F2PUNO (Purchase order number),F2PNLI (Purchase order line),F2PNLS (purchase order subline),F2REPN ,F2RELP(Responsible),F2SUDO (delivery number) ,F2SORN (supplier order number),F2TRDT (transaction date) ,F2RPQT (Reported quantity), F2ITNO (item number), F2IMST (Invoice matching status)
