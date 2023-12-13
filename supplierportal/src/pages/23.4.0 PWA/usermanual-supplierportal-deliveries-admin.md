![Supplier portal banner](../../../../images/banner-supplier-portal.jpg)

# Version 23.4.0 - Deliveries User Manual - Admin

- This is a separate add-on and has to be used alongside Supplier Portal. 
- 'My Deliveries' displays all the Delivery notes of the registered supplier. 
- For the first time login, Background job will fetch the delivery data from M3.  
- By default, 180 days old deliveries will be pulled from M3. Days can be changed in the backend configuration, but max value is 180 days Once the old data are pulled, Background job will run based on Timestamp. 

<kbd>
<img alt="metrics display" src="../../images/usermanual/delivery-setting.png"> 
</kbd>

- Filter settings by which deliveries can be filtered in the portal are to be configured in the admin section under Leanswift -> Supplier Portal -> Design/Display ->Deliveries.
- Filter: This can be used to filter for the apply the number of filters for the deliveries. 
- Filter Mapping: In this we can map the Filter Attribute, Filter Label, Filter Operations, Filter type, Action.  

<kbd>
<img alt="metrics display" src="../../images/usermanual/deliveries-filter-setting.png"> 
</kbd>


