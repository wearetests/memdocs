---
title: include file
description: include file
author: ErikjeMS  
ms.service: microsoft-intune
ms.topic: include
ms.date: 06/09/2021
ms.author: erikje
ms.custom: include file
---

These notices provide important information that can help you prepare for future Intune changes and features.

### Upgrade to the Microsoft Intune Management Extension<!-- 10102913 -->

We’ve released an upgrade to the Microsoft Intune Management Extension to improve handling of Transport Layer Security (TLS) errors on Windows 10 devices. 

The new version for the Microsoft Intune Management Extension is **1.43.203.0**. Intune automatically upgrades all versions of the extension that are less than **1.43.203.0** to this latest version. To check the version of the extension on a device, review the version for *Microsoft Intune Management Extension* in the program list under **Apps & features**.

For more information, see **CVE-2021-31980** at [https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-31980](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-31980).

#### What action do I need to take?

No action is required. As soon as the client connects to the service, it automatically receives a message to upgrade.

### Update to Endpoint Security Antivirus Windows 10 Profiles<!-- 9741752   -->

We've made a minor change to improve the Antivirus profile experience for Windows 10. There’s no end-user effect as this is a change only in what you’ll see in the UI.

#### How does this affect me?

Previously, when you configured a [Windows security profile](../protect/antivirus-security-experience-windows-settings.md) for Endpoint security Antivirus policy, you had two options for most settings: *Yes* and *Not configured*. Moving forward, those same settings now include *Yes*, *Not configured*, and a new option of *No*. Previously configured settings that were set to *Not configured* remain as *Not configured*.  When you create new profiles or edit an existing profile, you now have the option to explicitly specify *No*.

In addition, the setting *Hide the Virus and threat protection area in the Windows Security app* has a child setting, *Hide the Ransomware data recovery option in the Windows Security app*. If the parent setting (Hide the Virus and threat protection area) was set to *Not configured* and the child setting was set to *Yes*, both the parent and child settings will be set to *Not configured*, which will take effect when you edit the profile.

#### What action do I need to take?

No action is needed. However, you might want to notify your helpdesk about this change.

### Plan for Change: Intune ending company portal support for unsupported versions of Windows

Intune follows Windows 10 lifecycle for supported Windows 10 versions. We’re now removing support for the associated Windows 10 Company Portals for those Windows versions that are out of the Modern Support policy.

#### How does this affect me?

Given that Microsoft no longer supports these OSs, this may not affect you; you have likely already upgraded your OS or devices. This will only affect you if you are still managing unsupported Windows 10 versions. Windows and Company portal versions this affects include:

- Windows 10, Version 1507, Company portal version 10.1.721.0
- Windows 10, Version 1511, Company portal version 10.1.1731.0
- Windows 10, Version 1607, Company portal version 10.3.5601.0
- Windows 10, Version 1703, Company portal version 10.3.5601.0
- Windows 10, Version 1709, any Company portal version

We will not uninstall these Company portal versions mentioned above, but we will remove them from the Microsoft Store and stop testing our service releases with them.

**User Impact:** If you continue to use an unsupported version of Window 10, your users won't get the latest security updates, new features, bug fixes, latency improvements, accessibility improvements, and performance investments. The user will not be able to be co-managed with System Center Configuration Manager and Intune.

#### What do I need to do?

In the Microsoft Endpoint Manager admin center, use the [Discovered apps](../apps/app-discovered-apps.md) feature to find apps with these versions. On a user’s device, the Company Portal version is shown in the **Settings** page of the company portal. Update to a supported Windows/Company Portal version.

### Plan for Change: Intune moving to support Android 6.0 and higher in April 2021

As mentioned in MC234534, Intune will be moving to support Android 6.0 (Marshmallow) and higher in the April (2104) service release.

#### How this change will affect your organization

Given that the Office mobile apps for Android ended support for Android 5.x (Lollipop) on June 30, 2019 (MC181101) this change may not affect you; you have likely already upgraded your OS or devices. However, if you have any device that is still running Android version 5.x, or decide to enroll any device that is running Android version 5.x, please note that these devices will no longer be supported. Either update them to Android version 6.0 (Marshmallow) or higher or replace them with a device on Android version 6.0 or higher.

> [!NOTE]
> Teams Android devices are not impacted by this announcement and will continue to be supported regardless of their Android OS version.

#### What you need to do to prepare

Notify your helpdesk, if applicable, of this upcoming change in support. You also have two admin options to help inform your end users or block enrollment.

1. Here’s how you can warn end users:
    - Utilize a device compliance policy for Android device administrator or Android Enterprise and set the action for non-compliance to send a message to users before marking them noncompliant.
    - Configure an app protection policy Conditional launch setting with a Min OS version requirement to warn users.
2. Here’s how you can block devices on versions below Android 6.0:
    - Set enrollment restrictions to prevent devices on Android 5.x from enrolling
    - Utilize a device compliance policy for Android device administrator or Android Enterprise to make devices on Android 5.x non-compliant.
    - Configure an app protection policy Conditional launch setting with a Min OS version requirement to block users from app access.