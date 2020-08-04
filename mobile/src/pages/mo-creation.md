# User Guide - MO Creation

<img src="../../../images/banner-mobilefirst-cloudsuite.jpg" alt="banner" style="zoom:100%;" />



# Table of contents

- **[About this guide](#about-this-guide)**

  - [Intended Audience](#intended-audience)
    - [MO Creation standard functionality](#std-func)

- **[Workflow & Screen Layouts](#tech-details)**
- [MO Details For Creation](#mo-creation)
  







# <a name="about-this-guide"></a>About this guide

### <a name="intended-audience"></a>Intended Audience

MobileFirst Configuration User Guide provides guidance for LeanSwift customers and consultants regarding understanding the basic concept, functionality and configuration of the MO Creation Standard App. Further information about MobileFirst standard applications can be found at [www.inform3marketplace.com](http://www.inform3marketplace.com).  



#### **<a name="std-func"></a>MO Creation standard functionality**

The intended use of this app is for a user to be able to quickly and simply create a Manufacturing Order (MO) from an iOS device. The application is not intended to re-create all of the options available to the user within M3 but be a quick on-the-go option to create missing/additional Manufacturing orders manually.

# <a name="tech-details"></a>Workflow & Screen Layouts

This section provides details on the desired workflow within the applications and sample screen animation.

Upon navigating into MO Creation, the current logged in user's warehouse and facility will be selected under warehouse and facility fields. If the current user has no default warehouse assigned the field will be empty and user can select the warehouse from the list of warehouse by tapping the field.

### <a name="mo-creation"></a>MO details For Creation

After selection of warehouse and facility, product number has to be entered in the product field. This product number will be validated against M3 and upon valid product number the item details will be fetched and the product structure type will be auto populated in the product structure type field.

For creating an manufacturing order the quantity, status, pick date has to be provided. These fields has to be entered by the user.

On entering all valid values the slider controll will appear. Using this slide to confirm the MO creation will be done in the M3 and the order creation result success / failure message will be dispalyed with the order number.



