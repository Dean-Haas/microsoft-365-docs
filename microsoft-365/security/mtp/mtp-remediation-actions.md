---
title: Remediation actions following automated investigations in Microsoft 365 Defender 
description: Get an overview of remediation actions that follow automated investigations in Microsoft 365 Defender
keywords: automated, investigation, alert, trigger, action, remediation
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: 
- M365-security-compliance 
- m365initiative-m365-defender 
ms.topic: conceptual
ms.custom: autoir
ms.date: 09/16/2020 
ms.reviewer: evaldm, isco
---

# Remediation actions following automated investigations in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Applies to:**
- Microsoft 365 Defender


## Remediation actions

During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items. Some kinds of remediation actions are taken on devices, also referred to as endpoints. Other remediation actions are taken on email content. Automated investigations complete after remediation actions are taken, approved, or rejected.

The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender: 

|Device (endpoint) remediation actions  |Email remediation actions  |
|---------|---------|
|- Collect investigation package <br/>- Isolate device (this action can be undone)<br/>- Offboard machine <br/>- Release code execution <br/>- Release from quarantine <br/>- Request sample <br/>- Restrict code execution (this action can be undone) <br/>- Run antivirus scan <br/>- Stop and quarantine      |- Block URL (time-of-click)<br/>- Soft delete email messages or clusters<br/>- Quarantine email<br/>- Quarantine an email attachment<br/>- Turn off external mail forwarding          |

Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).

## Remediation actions follow automated investigations

When an automated investigation completes, a verdict is reached for every piece of evidence involved. Depending on the verdict, remediation actions are identified. In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval. It all depends on how [automated investigation and response is configured](mtp-configure-auto-investigation-response.md).

The following table lists possible verdicts and outcomes:

|Verdict    |Area    |Outcomes|
|------|------|------|
|Malicious    |Devices (endpoints)    |Remediation actions are taken automatically (assuming your organization's [device groups](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)|
|Malicious    |Email content (URLs or attachments) | Recommended remediation actions are pending approval|
|Suspicious    |Devices or email content |Recommended remediation actions are pending approval|
|No threats found    |Devices or email content    |No remediation actions are needed|

> [!IMPORTANT]
> Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as your organization's device group policies. To learn more, see the following articles:
> - [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md)
> - [How threats are remediated on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

## Next steps

- [Visit the Action center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [Approve or reject pending actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [Handle false positives/negatives in automated investigation and response capabilities](mtp-autoir-report-false-positives-negatives.md)
