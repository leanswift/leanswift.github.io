# CenPOS Payment
# Community Edition

## Add-on for eConnect for SX.e

## Usermanual

## Version 3.0.0


## Configuration

Log into the Magento Administration Panel, go to System > Cache Management, and click Flush Magento Cache

<kbd>
<img alt ="cache flush" src="../../Leanswift Sxe and CSD/Images/magento_cacheflush.png"></kbd>

Reload the page and then go to Stores > Configuration > Sales > Payment Methods > Other Payment Methods and look for Simple Webpay.

<kbd>
<img alt ="simple webpay" src="../../Leanswift Sxe and CSD/Images/cenpos_simplewebpay.png"></kbd>

Log into the Simple Webpay Admin panel to retrieve the encrypted Merchant ID and secret key values

https://www3.cenpos.net/simplewebpay/cards/administration/

The URL should be one of the following depending on if you are processing cards or checks:

https://www3.cenpos.net/simplewebpay/cards/ 
https://www3.cenpos.net/webpay/viewprocess/

Click save config.


## Sxe Configuration

Add the Cenpos Transaction type and Cenpos order type under sales configuration as below.

<kbd>
<img alt ="cenpos order type" src="../../Leanswift Sxe and CSD/Images/cenpos_ordertype.png"></kbd>





