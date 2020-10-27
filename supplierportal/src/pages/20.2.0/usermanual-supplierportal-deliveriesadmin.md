This is a separate add-on and has to be used alongside Supplier Portal.

The supplier should have Shipment Advice Value as 1 or 2. If 0 this panel is not shown in the user interface.

&#39;My Deliveries&#39; displays all the Delivery notes of the registered supplier. 

For the first time login, Background job will fetch the delivery data from M3. By default, 180 days old deliveries will be pulled from M3. Days can be changed in the backend configuration but max value is 180 days
Once the old data are pulled, Background job will run based on Timestamp

image

