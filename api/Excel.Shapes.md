---
title: Shapes object (Excel)
keywords: vbaxl10.chm637072
f1_keywords:
- vbaxl10.chm637072
ms.prod: excel
api_name:
- Excel.Shapes
ms.assetid: f9c6548c-d028-1b70-a11c-c4b45ff19177
ms.date: 04/02/2019
ms.localizationpriority: medium
---


# Shapes object (Excel)

A collection of all the **[Shape](Excel.Shape.md)** objects on the specified sheet.


## Remarks

Each **Shape** object represents an object in the drawing layer, such as an AutoShape, freeform, OLE object, or picture.

> [!NOTE] 
> If you want to work with a subset of the shapes on a document—for example, to do something to only the AutoShapes on the document or to only the selected shapes—you must construct a **[ShapeRange](Excel.ShapeRange.md)** collection that contains the shapes that you want to work with.


## Example

Use the **[Shapes](excel.worksheet.shapes.md)** property of the **Worksheet** object to return the **Shapes** collection. The following example selects all the shapes on _myDocument_.

> [!NOTE] 
> If you want to do something (like delete or set a property) to all the shapes on a sheet at the same time, select all the shapes, and then use the **ShapeRange** property on the selection to create a **ShapeRange** object that contains all the shapes on the sheet, and then apply the appropriate property or method to the **ShapeRange** object.

```vb
Set myDocument = Worksheets(1) 
myDocument.Shapes.SelectAll
```

<br/>

Use **Shapes** (_index_), where _index_ is the shape's name or index number, to return a single **Shape** object. The following example sets the fill to a preset shade for shape one on _myDocument_.

```vb
Set myDocument = Worksheets(1) 
myDocument.Shapes(1).Fill.PresetGradient _ 
 msoGradientHorizontal, 1, msoGradientBrass
```

<br/>

Use **Range** (_index_), where _index_ is the shape's name or index number or an array of shape names or index numbers, to return a **ShapeRange** collection that represents a subset of the **Shapes** collection. The following example sets the fill pattern for shapes one and three on _myDocument_.

```vb
Set myDocument = Worksheets(1) 
myDocument.Shapes.Range(Array(1, 3)).Fill.Patterned _ 
 msoPatternHorizontalBrick
```

<br/>

An ActiveX control on a sheet has two names: the name of the shape that contains the control, which you can see in the **Name** box when you view the sheet, and the code name for the control, which you can see in the cell to the right of **(Name)** in the Properties window. When you first add a control to a sheet, the shape name and code name match. However, if you change either the shape name or code name, the other isn't automatically changed to match.

You use the code name of a control in the names of its event procedures. However, when you return a control from the **Shapes** or **OLEObjects** collection for a sheet, you must use the shape name, not the code name, to refer to the control by name. For example, assume that you add a check box to a sheet and that both the default shape name and the default code name are CheckBox1. If you then change the control code name by typing chkFinished next to **(Name)** in the Properties window, you must use chkFinished in event procedures names, but you still have to use CheckBox1 to return the control from the **Shapes** or **OLEObject** collection, as shown in the following example.

```vb
Private Sub chkFinished_Click() 
 ActiveSheet.OLEObjects("CheckBox1").Object.Value = 1 
End Sub
```

## Methods

- [AddCallout](Excel.Shapes.AddCallout.md)
- [AddChart2](Excel.shapes.addchart2.md)
- [AddConnector](Excel.Shapes.AddConnector.md)
- [AddCurve](Excel.Shapes.AddCurve.md)
- [AddFormControl](Excel.Shapes.AddFormControl.md)
- [AddLabel](Excel.Shapes.AddLabel.md)
- [AddLine](Excel.Shapes.AddLine.md)
- [AddOLEObject](Excel.Shapes.AddOLEObject.md)
- [AddPicture](Excel.Shapes.AddPicture.md)
- [AddPicture2](Excel.shapes.addpicture2.md)
- [AddPolyline](Excel.Shapes.AddPolyline.md)
- [AddShape](Excel.Shapes.AddShape.md)
- [AddSmartArt](Excel.Shapes.AddSmartArt.md)
- [AddTextbox](Excel.Shapes.AddTextbox.md)
- [AddTextEffect](Excel.Shapes.AddTextEffect.md)
- [Add3DModel](Excel.Shapes.Add3DModel.md)
- [BuildFreeform](Excel.Shapes.BuildFreeform.md)
- [Item](Excel.Shapes.Item.md)
- [SelectAll](Excel.Shapes.SelectAll.md)

## Properties

- [Application](Excel.Shapes.Application.md)
- [Count](Excel.Shapes.Count.md)
- [Creator](Excel.Shapes.Creator.md)
- [Parent](Excel.Shapes.Parent.md)
- [Range](Excel.Shapes.Range.md)

## See also

- [Excel Object Model Reference](overview/Excel/object-model.md)

[!include[Support and feedback](~/includes/feedback-boilerplate.md)]
