# Version 3.0.0 - CenPOS Addon for eConnect SX.e/CSD

## User Manual

- Payment using CenPOS is developed as a separate Add-on to the eConnect extension. CenPOS’s Magento Extension SimpleWebpay is a prerequisite for this Add-on and we use the following GitHub link to download this extension.

  - https://github.com/mastercelta/SimpleWebpay/blob/master/composer.json

- PCI compliant CenPos functionality is ONLY available with the SFOEOrderTotLoadV4 API which is available only in SX.e versions 6.1.091 or higher

- So the version number of SX.e that eConnect is integrated with, has to be configured in the admin panel when this add-on is activated. If version is 6.1.091 or higher and SimpleWebPay module configuration is also available, then CC payment mode will be activated at “checkout” and order in SX.e will be created via SFOEOrderTotLoadV4 API. Otherwise order in SX.e will be created via OEFullOrderMntV6 API.

## SimpleWebpay Configuration

  - Go to Stores > Configuration > Sales > Payment Methods > Other Payment Methods and look for Simple Webpay.


  <kbd>
  <img alt ="simple webpay" src="/../../../ecommerce/images/eConnect-Sxe/cenpos_simplewebpay.png"></kbd>
  

    - Log into the Simple Webpay Admin panel to retrieve the encrypted Merchant ID and secret key values

        https://www3.cenpos.net/simplewebpay/cards/administration/

    - The URL should be one of the following depending on if you are processing cards or checks:

        https://www3.cenpos.net/simplewebpay/cards/ 
        
        https://www3.cenpos.net/webpay/viewprocess/

   - Click save config.


## Sales Configuration

  - "Extra fields for Order Creation" under Sales section allows to add the additional fields to be sent in CenPOS Order Creation request.

  - Change the CenPOS Order type and Transaction type under sales configuration if necessary. By default, "O" will be mentioned under CenPOS Order type and "LSF" will be mentioned under CenPOS Transaction type.

  <kbd>
  <img alt ="cenpos order type" src="/../../../ecommerce/images/eConnect-Sxe/cenpos_ordertype.png"></kbd>



_Note:_
- _All the fields mentioned under the configuration section are case sensitive_


