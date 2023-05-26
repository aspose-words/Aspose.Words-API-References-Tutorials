---
title: Read Active XControl Properties
linktitle: Read Active XControl Properties
second_title: Aspose.Words for .NET API Reference
description: Read properties of ActiveX controls in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

In this step-by-step guide, we will show you how to read properties of ActiveX controls in a Word document using Aspose.Words for .NET. We'll provide you with the complete source code and show you how to format the markdown output.

## Step 1: Document initialization

The first step is to initialize the `Document` object by loading the Word document containing the ActiveX controls. Be sure to replace `MyDir` with the actual path to the directory containing the document.

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");
```

## Step 2: Recover ActiveX controls

In this step, we will iterate through each `Shape` of the document to retrieve the ActiveX controls and read their properties.

```csharp
string properties = "";
foreach(Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
     if (shape.OleFormat is null) break;

     OleControl oleControl = shape.OleFormat.OleControl;
     if (oleControl.IsForms2OleControl)
     {
         Forms2OleControl checkBox = (Forms2OleControl)oleControl;
         properties = properties + "\nCaption: " + checkBox.Caption;
         properties = properties + "\nValue: " + checkBox.Value;
         properties = properties + "\nEnabled: " + checkBox.Enabled;
         properties = properties + "\nType: " + checkBox.Type;
         if (checkBox. ChildNodes != null)
         {
             properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
         }

         properties += "\n";
     }
}

properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
Console.WriteLine("\n" + properties);
```

### Example source code for Read Active XControl Properties using Aspose.Words for .NET

Here is the complete source code for reading properties of ActiveX controls using Aspose.Words for .NET:

```csharp
	Document doc = new Document(MyDir + "ActiveX controls.docx");

	string properties = "";
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
	{
		if (shape.OleFormat is null) break;

		OleControl oleControl = shape.OleFormat.OleControl;
		if (oleControl.IsForms2OleControl)
		{
			Forms2OleControl checkBox = (Forms2OleControl) oleControl;
			properties = properties + "\nCaption: " + checkBox.Caption;
			properties = properties + "\nValue: " + checkBox.Value;
			properties = properties + "\nEnabled: " + checkBox.Enabled;
			properties = properties + "\nType: " + checkBox.Type;
			if (checkBox.ChildNodes != null)
			{
				properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
			}

			properties += "\n";
		}
	}

	properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
	Console.WriteLine("\n" + properties);
```


