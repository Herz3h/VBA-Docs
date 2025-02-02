---
title: ValidationIssue.TargetPageID property (Visio)
keywords: vis_sdr.chm18662680
f1_keywords:
- vis_sdr.chm18662680
ms.prod: visio
api_name:
- Visio.ValidationIssue.TargetPageID
ms.assetid: fe893b42-839c-573e-fada-88f6e54fa562
ms.date: 06/08/2017
ms.localizationpriority: medium
---


# ValidationIssue.TargetPageID property (Visio)

Returns the ID of the page that is associated with the validation issue. Read-only.


## Syntax

_expression_. `TargetPageID`

_expression_ A variable that represents a **[ValidationIssue](Visio.ValidationIssue.md)** object.


## Return value

 **Long**


## Remarks

If the issue is not associated with a specific page, the  **TargetPageID** property returns -1.

[!include[Support and feedback](~/includes/feedback-boilerplate.md)]