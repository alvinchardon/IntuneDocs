---
# required metadata

title: Set up Wandera Mobile Security with Intune
titleSuffix: Intune on Azure
description: How to set up the Wandera Mobile Security with Microsoft Intune to control mobile device access to your corporate resources.
keywords:
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology:
ms.assetid:  

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: davidra
#ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
#ms.custom:
ms.collection: M365-identity-device-management
---


# Wandera Mobile Threat Defense connector with Intune  

Control mobile device access to corporate resources using conditional access based on risk assessment conducted by Wandera. Wandera is a Mobile Threat Defense (MTD) solution that integrates with Microsoft Intune.  Risk is assessed based on telemetry collected from devices by the Wandera service, including:
- Operating system vulnerabilities
- Malicious apps installed
- Malicious network profiles
- Cryptojacking

You can configure *conditional access* policies that are based on Wandera's risk assessment, enabled through Intune device compliance policies. Risk assessment policy can allow or block noncompliant devices from accessing corporate resources based on detected threats.  


## How do Intune and Wandera Mobile Threat Defense help protect your company resources?  

Wandera’s mobile app seamlessly installs using Microsoft Intune. This app captures file system, network stack, and device and application telemetry (where available). This information synchronizes to the Wandera cloud service to assess the device's risk for mobile threats. These risk level classifications are configurable to suit your needs in the Wandera console, RADAR.

The compliance policy in Intune includes a rule for MTD  based on Wandera’s risk assessment. When this rule is enabled, Intune evaluates device compliance with the policy that you enabled.

For devices that are noncompliant, access to resources like Office 365 can be blocked. Users on blocked devices receive guidance from the Wandera app to resolve the issue and regain access.

## Supported platforms  

The following platforms are supported for Wandera when enrolled in Intune:

- Android 5.0 and later  
- iOS 10.2 and later  

For more information about platform and device, see the [Wandera website](https://www.wandera.com/mobile-threat-defense/).

## Prerequisites  

- Microsoft Intune subscription  
- Azure Active Directory  
- Wandera Mobile Threat Defense (formerly Wandera Secure)  

For more information, see [Wandera Mobile Security](https://www.wandera.com/mobile-security/).
 
## Sample scenarios

Here are the common scenarios when using Wandera MTD with Intune.

### Control access based on threats from malicious apps  

When malicious apps such as malware are detected on devices, you can block devices from common tools until you can resolve the threat. Common blocks  include:  
- Connecting to corporate e-mail  
- Syncing corporate files with the OneDrive for Work app  
- Accessing company apps  

**Block when malicious apps are detected**:

![Conceptual image of Malicious apps detected](./media/wandera-mtd-connector/wandera-malicious-apps-blocked.png)  

**Access granted on remediation**: 

![Conceptual image of access granted after remediation](./media/wandera-mtd-connector/wandera-malicious-apps-unblocked.png)


### Control access based on threat to network  

Detect threats to your network such as man-in-the-middle attacks and protect access to Wi-Fi networks based on the device risk.  

**Block network access through Wi-Fi**:  

![Block network access through Wi-Fi](./media/wandera-mtd-connector/wandera-network-wifi-blocked.png)

**Access granted on remediation**:  

![Access granted on remediation](./media/wandera-mtd-connector/wandera-network-wifi-unblocked.png)  

## Control access to SharePoint Online based on threat to network

Detect threats to your network such as Man-in-the-middle attacks, and prevent synchronization of corporate files based on the device risk.

**Block SharePoint Online when network threats are detected**:  

![Block SharePoint Online when network threats are detected](./media/wandera-mtd-connector/wandera-network-spo-blocked.png)  


**Access granted on remediation**:  

![Access granted on remediation for SharePoint example](./media/wandera-mtd-connector/wandera-network-spo-unblocked.png)  

## Next steps

- [Integrate Wandera with Intune](wandera-mtd-connector-integration.md)
- [Set up Wandera apps](mtd-apps-ios-app-configuration-policy-add-assign.md)
- [Create Wandera device compliance policy](mtd-device-compliance-policy-create.md)
- [Enable Wandera MTD connector](mtd-connector-enable.md)
