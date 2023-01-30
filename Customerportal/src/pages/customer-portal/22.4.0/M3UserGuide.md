[![](RackMultipart20230128-1-nq44dl_html_8e85754fa92f0167.jpg)](https://github.com/leanswift/leanswift.github.io/blob/master/Customerportal/src/images/customer-portal/front-end-user/CP_banner.jpg)

# **Version 22.4.0- User Manual - M3 Login**

# Table of contents

- [**Version 22.4.0- User Manual - M3 Login**](#version-2240--user-manual---m3-login)
- [**Table of Contents**](#table-of-contents)
- [**Architecture**](#architecture)
- [**User Guide for M3 Login Module – Admin User**](#user-guide-for-m3-login-module--admin-user)

**Overview**

**LeanSwift M3 login module**  provides the ability to log into Magento with an Infor OS user (Single Sign-on support with Infor OS). It also retrieves the list of users in Infor M3 along with security roles. The module leverages ION APIs and Infor's authentication and authorization services to validate M3 user credentials (Ming.le user) via IFS (Infor Federation Services).

# **Architecture**

[![](RackMultipart20230128-1-nq44dl_html_47799d23ad036281.jpg)](https://github.com/leanswift/leanswift.github.io/blob/master/Customerportal/src/images/add-ons/m3-login/CustomerPortal_Architecture.jpg)

[↥ **Go to Top**](https://github.com/leanswift/leanswift.github.io/blob/master/Customerportal/src/pages/add-ons/m3-login/usermanual-m3-login.md#toc)

**Features**

- Redirect user login attempt from Magento to Infor OS (Ming.le) login interface
- Authenticate Ming.le user credentials
- Redirect to invoking Magento interface after authentication is successful
- Retrieves list of M3 users and associated security roles

[↥Go to Top](https://github.com/leanswift/leanswift.github.io/blob/master/Customerportal/src/pages/add-ons/m3-login/usermanual-m3-login.md#toc)

**Point Of Contact**

This document and the software it describes are provided by LeanSwift Solutions Inc. For additional information regarding support, licensing, functionality etc. please contact LeanSwift Solutions Inc. via contact form at [http://www.leanswift.com](http://www.leanswift.com/) or email [info@leanswift.com](mailto:info@leanswift.com).

[↥Go to Top](https://github.com/leanswift/leanswift.github.io/blob/master/Customerportal/src/pages/add-ons/m3-login/usermanual-m3-login.md#toc)

# **User Guide for M3 Login Module – Admin User**

**Login**

- To access M3 Login Settings as admin user, go to LeanSwift – M3 Login – Settings.

[![](RackMultipart20230128-1-nq44dl_html_26808ff74ed9a807.jpg)](https://github.com/leanswift/leanswift.github.io/blob/master/Customerportal/src/images/add-ons/m3-login/M3Login.jpg)

- From the M3 Login module the Admin user can configure logging preference, domain and authentication settings and click on Save Config.

[![](RackMultipart20230128-1-nq44dl_html_7369730f8c64bf86.jpg)](https://github.com/leanswift/leanswift.github.io/blob/master/Customerportal/src/images/add-ons/m3-login/M3LoginHomePage.jpg)

[↥Go to Top](https://github.com/leanswift/leanswift.github.io/blob/master/Customerportal/src/pages/add-ons/m3-login/usermanual-m3-login.md#toc)

**General**

- M3 Login general module allows admin to configure logging preference and internal email domain settings.
- Go to LeanSwift – M3 Login – Settings – General.
- Enable Login
  - To enable login for M3 User, configure Enable Login setting as Yes.
  - Configuring the enable login as No, disables M3 User Login into Customer Portal. Internal users will not be able to access Customer Portal.
- Debug/log data
  - To enable debug/log data, configure Debug/log data as Yes.
  - Setting Debug/log data to No, disables logger.
  - The logger is disabled by default and can be enabled to check request and response data for troubleshooting purposes.

[![](RackMultipart20230128-1-nq44dl_html_60e3173b97f2f465.jpg)](https://github.com/leanswift/leanswift.github.io/blob/master/Customerportal/src/images/add-ons/m3-login/M3Login-General.jpg)

- Internal user Email domain(s)
  - Configure the internal user email domain(s).
  - Specify comma separated list of internal user email domains.Ex: leanswift.com
  - If the login Id contains any of the internal user email domains, the password field is disabled and the user is taken to Magento for login authentication.

[↥Go to Top](https://github.com/leanswift/leanswift.github.io/blob/master/Customerportal/src/pages/add-ons/m3-login/usermanual-m3-login.md#toc)

**Authentication**

- M3 Login authentication module allows admin to configure service URL for authorization, service URL for Ming.le, Client id and Client secret settings.
  - This information can be obtained from [Multi-tenant Cloud Infor OS](https://www.infor.com/resources/infor-ming-le).
- Go to LeanSwift – M3 Login – Settings – Authentication.

[![](RackMultipart20230128-1-nq44dl_html_c9dd475509758ed9.jpg)](https://github.com/leanswift/leanswift.github.io/blob/master/Customerportal/src/images/add-ons/m3-login/M3Login-Authentication.jpg)

[↥Go to Top](https://github.com/leanswift/leanswift.github.io/blob/master/Customerportal/src/pages/add-ons/m3-login/usermanual-m3-login.md#toc)

**Import M3 User Roles**

- It is part of add-on to fetch M3 User Roles and Functions as initial import. This is not required for Customer Portal v21.1.0.

![](RackMultipart20230128-1-nq44dl_html_61c92283e0aba313.png)

**Customer User Permissions**

- Users must have roles assigned to them in Magento, and they can only log in to the frontend based on the rights they have been allowed.
- **Internal User Permission**

[![](RackMultipart20230128-1-nq44dl_html_11754d15265a8e96.png)](https://github.com/leanswift/leanswift.github.io/blob/master/Customerportal/src/images/add-ons/m3-login/UserPermission-InternalUserPermission.png)

- M3 USER Role - Internal User permissions are leveraged at M3 user Role configuration.
  - Customers of Magento have permissions by default.
  - Users should have access configured both in Customers Portal Settings and M3 user role settings.

[↥Go to Top](https://github.com/leanswift/leanswift.github.io/blob/master/Customerportal/src/pages/add-ons/m3-login/usermanual-m3-login.md#toc)

![Shape1](RackMultipart20230128-1-nq44dl_html_8364f73a6574c228.gif)
