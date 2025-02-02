---
title: ReportItem.IsConflict property (Outlook)
keywords: vbaol11.chm1677
f1_keywords:
- vbaol11.chm1677
ms.prod: outlook
api_name:
- Outlook.ReportItem.IsConflict
ms.assetid: ec5db93a-43e5-8f9c-ed55-c940c0d056d1
ms.date: 06/08/2017
ms.localizationpriority: medium
---


# ReportItem.IsConflict property (Outlook)

Returns a **Boolean** that determines if the item is in conflict. Read-only.


## Syntax

_expression_. `IsConflict`

_expression_ A variable that represents a [ReportItem](Outlook.ReportItem.md) object.


## Remarks

Whether or not an item is in conflict is determined by the state of the application. For example, when a user is offline and tries to access an online folder the action will fail. In this scenario, the  **IsConflict** property will return **True**.

If  **True**, the specified item is in conflict.


## See also


[ReportItem Object](Outlook.ReportItem.md)

[!include[Support and feedback](~/includes/feedback-boilerplate.md)]