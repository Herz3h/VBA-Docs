---
title: Menu.Index property (Visio)
keywords: vis_sdr.chm13113695
f1_keywords:
- vis_sdr.chm13113695
ms.prod: visio
api_name:
- Visio.Menu.Index
ms.assetid: 53982ac5-b652-3f46-f949-038e8f86e5cc
ms.date: 06/08/2017
ms.localizationpriority: medium
---


# Menu.Index property (Visio)

Gets the ordinal position of a  **Menu** object in a **Menus** collection. Read-only.


## Syntax

_expression_.**Index**

_expression_ A variable that represents a **[Menu](Visio.Menu.md)** object.


## Return value

Long


## Remarks


> [!NOTE] 
> Starting with Visio 2010, the Microsoft Office Fluent user interface (UI) replaced the previous system of layered menus, toolbars, and task panes. VBA objects and members that you used to customize the user interface in previous versions of Visio are still available in Visio, but they function differently.

Most collections are indexed starting with 1 rather than zero (0), so the index of the first element is 1, the index of the second element is 2, and so forth. The index of the last element in a collection is the same as the value of that collection's  **Count** property. You can iterate through a collection by using these index values. Adding objects to or deleting objects from a collection can change the index values of other objects in the collection.

There are some exceptions. The  **Colors** collection is indexed starting with 0.

These collections are also indexed starting with 0:  **AccelItems**, **AccelTables**, **MenuSets**, **MenuItems**, **Menus**, **ToolbarItems**, **Toolbars**, and **ToolbarSets**.

[!include[Support and feedback](~/includes/feedback-boilerplate.md)]