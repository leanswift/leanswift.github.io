# **Supplier Portal**

# **20. 2 .0**

## **Internal Release Notes**

**Table of Contents**

**[Overview](#_heading=h.1fob9te) 

**[Environment Details](#_heading=h.3znysh7) 

**[Standard Features](#_heading=h.2et92p0) 

**[Account](#_heading=h.tyjcwt) 

**[JIRA References](#_heading=h.3dy6vkm) 

**[Notes](#_heading=h.1t3h5sf) 

**Validated Versions 

**[GitHub Link](#_heading=h.2s8eyo1) 

**[TestRail Link](#_heading=h.17dp8vu) 

**[Documentation](#_heading=h.3rdcrjn) 

**[Point of Contact](#_heading=h.26in1rg) 

##

##

## **Overview**

**LeanSwift Supplier Portal** for Infor M3 CloudSuite is a supplier self-service portal that enables efficient online communication with vendors. It is seamlessly integrated with Infor M3 Cloudsuite via ION. Supplier Portal helps automate the entire purchase-to-pay process for the customer.

## **Environment Details**

| _ **Software Name** _ | _ **Version** _ |
| --- | --- |
| Magento Open Source | 2.3.5 |
| eConnect Base Module Version | 3.0.0 |
| IDM Module version | 3.0.0 |
| RabbitMQ | 3.8.3 |
| ION Desk | 12.0.0 |
| Infor M3 | 16.1 |
| Infor ION Grid | 12.0.2.0.20180308-135417.2 |

##

## **Standard Features**

- **Purchase Orders**
  - Re-Confirm PO line
  - Confirm multiple POs
  - Advise PO line , PO(all lines) , Multiple POs
  - Notify PO line , PO(all lines) , Multiple POs
  - Notify PO via Delivery Note number

- **Upload supplier-specific docs into IDM**
- **View open and pending invoices**
- **View delivery notes**
- **Supplier Admin to manage users/roles**
- **Email notifications on new orders/changes to existing orders**

## **JIRA References**

[**All**](https://leanswift.atlassian.net/issues/?jql=project%20%3D%20SP%20AND%20fixVersion%20in%20(unreleasedVersions()%2C%2020.2.0)%20order%20by%20created%20DESC)

[**User Stories/Tasks**](https://leanswift.atlassian.net/issues/?jql=project%20%3D%20SP%20AND%20issuetype%20in%20(Change%2C%20Story%2C%20Task)%20AND%20fixVersion%20in%20(unreleasedVersions()%2C%2020.2.0%2C%20%22SP%2020.2.0%22)%20order%20by%20created%20DESC)

[**Bugs Identified/Fixed/Closed**](https://leanswift.atlassian.net/issues/?jql=project%20%3D%20SP%20AND%20issuetype%20%3D%20Bug%20AND%20fixVersion%20in%20(unreleasedVersions()%2C%2020.2.0%2C%20%22SP%2020.2.0%22)%20order%20by%20created%20DESC)

## **Notes**

- When SHAC is kept as 2 , and Automatic dely note generation is enabled , advise and notify is done for a delivery note number PPS360 / TransNotifyHead is called .

when the SHAC is disabled for the same supplier and I advise a line with same delivery note number ( line is not added in PPS360 ) but since the delivery note number is available in pps360 during notify the PPS360 / TransNotifyHead is called and the PPS001MI/NotifyDelNot is not called. This causes the line to remain in processing state

- filters that it works with ltd conditions

- During Advise All, if some error message is displayed Ex. Delivery number must be entered, Click refresh button for the input to be cleared before choosing another order to Advise

## **Validated Versions**

- Microsoft Edge 44.18362.449.0
- Chrome Version 83.0.4103.61
- Internet Explorer 11.836.18362.0

## **GitHub Link**

[https://github.com/leanswift/supplier-portal/releases/tag/20.1.0](https://github.com/leanswift/supplier-portal/releases/tag/20.1.0)

## **TestRail Link**

https://leanswift.testrail.net/index.php?/runs/view/264&group_by=cases:section_id&group_order=asc&group_id=2650

## **Documentation**

All relevant documentation regarding release 20.2.0 are available on [LeanSwift&#39;s Intranet](https://sites.google.com/a/leanswift.com/leanswiftinfo/products) and on [LeanSwift&#39;s Google Drive](https://drive.google.com/drive/folders/1HSdOA2C8dMBNRVkoCEWpnFrWXsOdphHx)

## **Point of Contact**

[prabhu.mano@leanswift.com](mailto:prabhu.mano@leanswift.com)

[niranjan.b@leanswift.com](mailto:niranjan.b@leanswift.com)

[deepthi.tadikamalla@leanswift.com](mailto:deepthi.tadikamalla@leanswift.com)

[srinidhi.narayanan@leanswift.com](mailto:srinidhi.narayanan@leanswift.com)

[nrithya.rajagopalan@leanswift.com](mailto:nrithya.rajagopalan@leanswift.com)
