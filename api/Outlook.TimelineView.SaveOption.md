---
title: TimelineView.SaveOption property (Outlook)
keywords: vbaol11.chm2654
f1_keywords:
- vbaol11.chm2654
ms.prod: outlook
api_name:
- Outlook.TimelineView.SaveOption
ms.assetid: c18bcf6f-eeb7-53d2-95a9-5d380d32f6cf
ms.date: 06/08/2017
ms.localizationpriority: medium
---


# TimelineView.SaveOption property (Outlook)

Returns an **[OlViewSaveOption](Outlook.OlViewSaveOption.md)** constant that specifies the folders in which the specified view is available and the read permissions attached to the view. Read-only.


## Syntax

_expression_. `SaveOption`

_expression_ A variable that represents a [TimelineView](Outlook.TimelineView.md) object.


## Remarks

The value of the  **SaveOption** property is set when the **[TimelineView](Outlook.timelineView.md)** object is created by using the **[Add](Outlook.Views.Add.md)** method of the **[Views](Outlook.Views.md)** collection.


## Example

The following Visual Basic for Applications (VBA) example locks the user interface for all views that are available to all users. The subroutine  `LockView` accepts the **[View](Outlook.View.md)** object and a **Boolean** value that indicates if the **View** user interface will be locked. In this example, the procedure is always called with the **Boolean** value set to **True**.


```vb
Sub LockPublicViews() 
 
 
 
 Dim objName As NameSpace 
 
 Dim objViews As Views 
 
 Dim objView As View 
 
 
 
 ' Get the Views collection for the Contacts default folder. 
 
 Set objName = Application.GetNamespace("MAPI") 
 
 Set objViews = objName.GetDefaultFolder(olFolderContacts).Views 
 
 
 
 ' Enumerate the Views collection and lock the user 
 
 ' interface for any view that can be accessed by 
 
 ' all users who have access to the Notes default folder. 
 
 For Each objView In objViews 
 
 If objView.SaveOption = _ 
 
 olViewSaveOptionThisFolderEveryone Then 
 
 
 
 Call LockView(objView, True) 
 
 End If 
 
 Next objView 
 
 
 
End Sub 
 
 
 
Sub LockView(ByRef objView As View, ByVal blnAns As Boolean) 
 
 
 
 ' Examine the view object. 
 
 With objView 
 
 If blnAns = True Then 
 
 ' Lock the user interface and 
 
 ' save the view 
 
 .LockUserChanges = True 
 
 .Save 
 
 Else 
 
 ' Unlock the user interface of the view. 
 
 .LockUserChanges = False 
 
 End If 
 
 End With 
 
 
 
End Sub
```


## See also


[TimelineView Object](Outlook.timelineView.md)

[!include[Support and feedback](~/includes/feedback-boilerplate.md)]