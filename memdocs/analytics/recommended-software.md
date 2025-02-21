---
title: Recommended software in Endpoint Analytics
titleSuffix: Microsoft Endpoint Manager
description: Get details about recommended software in Endpoint Analytics
ms.date: 10/05/2021
ms.prod: configuration-manager
ms.technology: configmgr-analytics
ms.topic: conceptual
author: mestew
ms.author: mstewart
manager: dougeby
ms.localizationpriority: high
---

# <a name="bkmk_rs"></a> Recommended software

Certain software is known to improve the end-user experience, independent of lower-level health metrics. For example, currently supported versions of Windows have a much higher Net Promoter score than Windows 7. The **Software adoption** score is a number between 0 and 100. The score represents a weighted average of the percent of devices that have deployed various recommended software. The current weighting is higher for Windows than for the other metrics since users interact with them more often. The metrics are described below: 

[![Endpoint analytics Recommended software page](media/recommended-software.png)](media/recommended-software.png#lightbox)

> [!Important]  
> Endpoint Analytics computes the **Software adoption** score for all your Intune and co-managed devices, regardless of whether they've been configured with the [Intune data collection policy](settings.md#bkmk_profile) or not. For Configuration Manager-managed devices, scores are only computed for [enrolled devices](enroll-configmgr.md#bkmk_cm_enroll).

## <a name="bkmk_win10"></a> Windows 10 and later

Supported versions of Windows provide a better user experience than older versions of Windows. For more information, see the [TEI whitepaper](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RWCpaP).

This metric measures the percent of devices on Windows 10 or later versus an older version of Windows.

The recommended remediation action for moving devices from older versions of Windows is to create a deployment plan using [Desktop Analytics](../configmgr/desktop-analytics/overview.md).

## <a name="bkmk_ap"></a> Autopilot

Microsoft Autopilot provides a simpler initial provisioning experience for Windows PCs than the native experience by reducing the number of screens in the Out Of Box Experience (OOBE) and providing defaults, to ensure the employees device is correctly provisioning from the factory or on reset.

This metric measures the percent of Windows 10 or later devices that are registered for Autopilot.

The recommended remediation action is to register existing devices in Autopilot using [Microsoft Intune](../autopilot/enrollment-autopilot.md).

## <a name="bkmk_aad"></a> Azure Active Directory

Azure Active Directory (Azure AD) provides users with many productivity benefits including device-wide single sign-on to apps and services, Windows Hello sign-in, self-service BitLocker recovery, and corporate data roaming.

This metric measures the percent of devices enrolled in Azure AD.

Your Microsoft-Intune managed devices are already enrolled in Azure AD. The recommended remediation action for devices managed by Configuration Manager is to either [enroll them in Azure AD](/azure/active-directory/devices/hybrid-azuread-join-managed-domains) or [co-manage them](../configmgr/comanage/overview.md). Co-managing devices also improves your cloud management score.

## <a name="bkmk_intune"></a> Cloud management

Configuration Manager and Intune provide integrated cloud-powered management tools and unique co-management options to provision, deploy, manage, and secure endpoints and applications across an organization. With the power of cloud management, you can achieve several productivity benefits, including enabling access to corporate resources even when they're away from the corporate network, and eliminating the need for and performance overhead of Group Policy, resulting in a better end-user experience.

This metric measures the percent of PCs that have attached to the Microsoft 365 cloud to unlock additional capabilities. See how [Microsoft is enabling modern management for our employees](https://www.microsoft.com/en-us/itshowcase/managing-windows-10-devices-with-microsoft-intune).

The recommended action for devices managed by Configuration Manager that aren't yet enrolled in Intune is to [co-manage them](../configmgr/comanage/overview.md) to unlock additional cloud-powered capabilities like conditional access.

## <a name="bkmk_np"></a> No commercial median

The built-in baseline of **All organizations (median)** doesn't currently have metrics for the subscores listed in the sections above.

## Next steps

- View [Startup performance](startup-performance.md)
- Use [Proactive remediations](proactive-remediations.md) to help fix common support issues before end-users notice issues.
