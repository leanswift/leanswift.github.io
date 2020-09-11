<h2>Table of contents</h2>

- [**For Multi-tenant/Cloud suite environment**](#--for-multi-tenant-cloud-suite-environment--)
    + [ION API Service URL](#ion-api-service-url)
    + [OAuth Token URL and Credentials](#oauth-token-url-and-credentials)
    + [Logical Id](#logical-id)
    + [M3 User](#m3-user)
    + [Basic Data](#basic-data)
- [**Infor Document Management**](#--infor-document-management--)
    + [IDM ION API Service URL](#idm-ion-api-service-url)
- [**For Single-tenant/On-Premise environment**](#--for-single-tenant-on-premise-environment--)

# **For Multi-tenant/Cloud suite environment**

Login to your Multi-tenant environment to get the following details:

### ION API Service URL

Sample URL: https://mingle-ionapi.inforcloudsuite.com/LEANSWIFT_TST/M3/m3api-rest/v2/execute

Please follow the below steps to get the ION API Service URL.

Click on “App Menu” and choose “Infor ION API”

![img](https://lh4.googleusercontent.com/oObGriih9z_qsqQa-lL5ySrv8ThuxfsTnFvh9m1s_DTkJo_VAYLHXGaESx5olKHAG9uCshxJNeGUMM-NMZniEX_hj_v-uWBxvnvv-IGRKNvq3tER2-p5mZy5nP_t0wwREWSwmPIo)

Click on “Available APIs” and search for “Infor M3” in the search text box. Then click on “Infor M3” from the search result.

![img](https://lh3.googleusercontent.com/O0oSrJ3HTlacLBc3K6QbHeD6dJozFRtcwtQ8MaI3jxzD2TYOJ5yEr1ufaPVOX-clw54IrkoJLF07lHsnWBSaRLZRJ6wra8lS5GH2vp8EUmaGJYC30lvMvypow9eMVBscXcwLSOzD)

Search for “Infor M3 MI v2” in the Description Box. Click on the arrow mark under the Details column as shown below.
![img](https://lh3.googleusercontent.com/__vHsoQopX6I51yd2fVFh8mTnEUrWc9EsM0azQvXIk5AlOB96LUc3TgZ_4of-eQU_im7PFYuAKNTsEHB016gTE1IVwPfCc-j-KkbEtRp9pLtiNFgLBGw6Tpsgu3V3Tppp50RPdRW)


Refer to the below image and note down the ION API Service URL.![img](https://lh4.googleusercontent.com/nFXhcfAu4_WBLVY9QMtcr8NABQ49LKDYnRm27m7eFkB8Isq_P7SVBDNQdYzWg9EDymOx3aiXNBzeWwamOb1mDMI11EVyBYEFmkAb4lXz8Q0PEh_cvuWXErDXgE0roFulI3r7J94I)

### OAuth Token URL and Credentials

Go to the Infor ION API menu, Click on the “Authorized Apps” then click on the “+” icon as shown in the below image.![img](https://lh4.googleusercontent.com/cQB40fpt2MnLqjdGOFHMwv263EGa8kQfNRTjv0WHPKSFGsn_Nr492VwOryY3sIhmJ3m6orZqAUc5hgkywJUxYwdagF_bUvvNQCtQUfWa9IofZ638VhHuBtW5x-uHUu-MV4lZ8ppw)


Mention the Name, Description, choose the Type as “Backend Service” and click on Save.![img](https://lh6.googleusercontent.com/cOPKxp8y_YAO5u_yk65uyMdAIRpYHw84KdjjdfEcKkvbxdKJaA6OU3OCEsbSh9mnM5Ge-oQSjWSL_7LBVAVXWt--zCwogoj7Uf5uiJEkmNrJUN2lTV9yKCUYirQLVWPi5D9Ed9Vl)

After clicking on “Save”, Click on the “Download Credentials” button.
![img](https://lh4.googleusercontent.com/mc9Sd9-y23qLBwqjCr6_AZqGr8Qbhzy0KT4vNNXSkirKZ4waP0xp9RlI666RP1VsmCkmoRGFTM50FvTlqlbQSDOSJ9ds-uC-q1jDqdCLERjKPD4IHh4vjNOGB-hbpcmjC6lsmP08)


Clicking on “Download Credentials will open the below dialog box.
		Enable “Create Service Account”.
		Choose “User Name”.
		Click on “Download”.
![img](https://lh4.googleusercontent.com/Blc6mJgOwPgo_Exbmo6ah4mrJ6pKz4_EdPGFaQVO3FSoNNJcef8DNsYPXiUDklVoXzju-8LQ3m0S9jGuMIClXXTHf-BEJL_ePhHpfgHCjOuS9EAyhRetyOly6GpVQmo86DTGK9Ap)


On clicking “Download”, “ionapi” file will get downloaded. Open the file with a text editor and get the credential details with the below image as a reference.

![img](https://lh4.googleusercontent.com/lYLI3vxvlbIYbFMtSKB2nCYUgkc4Lig77sSoupMxXaUWZGFXYFjy1foLorAfSG1P6sc41vjThoL8XTsN6q74kE83TeKbcThRb8aHLbkXdtJxIyyhx0pT6n0pdgH8l4ofRle__gkp)

### Logical Id

Click on the “User Icon” and Go to “Admin Settings”.

![img](https://lh3.googleusercontent.com/a98EXV5-Q_yFOmCmqFilIzT6L2RR69srSVM5tS8_UKEjANWAA_dPrtyZ_x5JbiRfsbr66Tm8pljs0VdHe4OV9snJ0u32OwaYQvMX06-eMjjX24ykH26aOTL6nX79edrQuotvOlqt)

After being redirected to the “Manage Applications” page, Double click on the “Infor M3”.
![img](https://lh3.googleusercontent.com/CvEbjwgzgkVolXxL_SK24qIPB4ojkcE5Hww-iDPgVO2g2QjsC0-Ql-tVWkWZv9pre1R4CdWGeJAJy465fa8CEidLCQDTmsiMEbVZWd7xbu__X57-Ybaze-RgmExQMSgN_mEgesk6)

Double click on “Infor M3” will bring the “Application Details” page. There you can get the “Logical Id”.
![img](https://lh5.googleusercontent.com/qEfGvdO6W-kzpRnnhrI7eMCPbr2snILQZ1gCWYzDkP-f78rEqtJOCqqEkcKyIeNFQlPJWBe8tbI0b1DKoPrmEAZEWacWh7iOW2fzMlNEHI8KGT04wsEH3KCpfHZoEWpJEK48bCJ1)

### M3 User

Go to “App Menu” and click on “Infor M3”.

![img](https://lh6.googleusercontent.com/Uix_Qv3HRWUHXgKLxrx4EEFI0mJzU3CLamg8plMfZM-cNX-b4jBum6ez_FwdPx897MQ1btGs5VBdEz-RR3r0afq9myeQweEDcMslw5xXPVNPmyFp1gBzqsGl0hTMGxRL2_xD6g5j)



Click on CTRL + R, Type “MNS150” and click “Enter”.

![img](https://lh4.googleusercontent.com/V6l4IGymO_pgiRG4xggU9sgPpCjLsjIkZ9BDYYhzCuppb3mrDDw-w9qM_4CqPAMB0vtYtRNM7p2lU9U0Vfdkn_ASERSGMfk94f-hfwEd529ygLyTCtiRLSIcIM9NcUQaWA36HeEm)

### Basic Data

Add the user with the Company, Division, and Facility details.
![img](https://lh3.googleusercontent.com/XoO5rCuT23yMHbcpYihiVMJh1bi0XhpJm2oH0M-z2uNJL3Z8nnIMRcN7HSmm1PqUWc5rqIHtvb-av4OXJSYSrAB6utynPwDKM0mFtn30Fr2PCivXW3xH7Rb7h2bClf4mYE6_Y_Cn)



# **Infor Document Management**

### IDM ION API Service URL

Sample URL: https://mingle-ionapi.inforcloudsuite.com/LEANSWIFT_TST/IDM/api

Click on “App Menu” and choose “Infor ION API”

![img](https://lh4.googleusercontent.com/oObGriih9z_qsqQa-lL5ySrv8ThuxfsTnFvh9m1s_DTkJo_VAYLHXGaESx5olKHAG9uCshxJNeGUMM-NMZniEX_hj_v-uWBxvnvv-IGRKNvq3tER2-p5mZy5nP_t0wwREWSwmPIo)



Click on “Available APIs” and search for “Infor Document Management” in the search text box. Then click on “Infor Document Management” from the search result.
![img](https://lh5.googleusercontent.com/TubdaZMByahs4j8Nn9OXd-w9alPVT2mzDD1pF0mRdwAE7aYNsMlK__ElZyOHHCW16yIrI0NjNEynzkXAeWTOPtIiy6vhxrt57U4rSbhgiV0So5VOlU4VFeB9jebRGLSbGq0fEvBW)



Click on “Infor Document Management”. From the Grid, Get the ION API Service URL(Rest Api) and the Token URL as shown below.
![img](https://lh3.googleusercontent.com/TBknKJnpsCSfDSNGz8pLNbkW9YT6EMam-k1Vmc3IynHHh5ROKYIJnXwSymR9zJGmU_7QLsCHr34nQ2Rf98dtef4yh3UHb3GtiJ5kosiYgw81Q0Q7tDGqXzHXui-JnLIH3s_xLdHn)



# **For Single-tenant/On-Premise environment**
