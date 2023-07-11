---
title: Modify Content Controls
linktitle: Modify Content Controls
second_title: Aspose.Words Document Processing API
description: Learn how to modify text, dropdown lists, and images within content controls in a Word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-sdt/modify-content-controls/
---

This tutorial explains how to modify different types of content controls in a Word document using Aspose.Words for .NET. You can update the text, selected value of a dropdown list, or replace an image within the content controls.

## Prerequisites
To follow this tutorial, you need to have the following:

- Aspose.Words for .NET library installed.
- Basic knowledge of C# and working with Word documents.

## Step 1: Set up the Document Directory
Begin by setting up the path to your document directory. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to the directory where your document is located.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Load the Document and Iterate Over Content Controls
Load the Word document using the `Document` constructor, passing the path to the document as a parameter. Iterate over all structured document tags in the document using a `foreach` loop.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // Perform actions based on the type of content control
}
```

## Step 3: Modify Plain Text Content Control
For content controls of type `SdtType.PlainText`, remove all existing children, create a new paragraph, and append a run with the desired text.

```csharp
case SdtType.PlainText:
{
    sdt.RemoveAllChildren();
    Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
    Run run = new Run(doc, "new text goes here");
    para.AppendChild(run);
    break;
}
```

## Step 4: Modify Drop-down List Content Control
For content controls of type `SdtType.DropDownList`, update the selected value by setting it to a specific `SdtListItem`.

```csharp
case SdtType.DropDownList:
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
    break;
}
```

## Step 5: Modify Picture Content Control
For content controls of type `SdtType.Picture`, retrieve the shape within the content control and replace its image with a new one.

```csharp
case SdtType.Picture:
{
    Shape shape = (Shape)sdt.GetChild(NodeType.Shape, 0, true);
    if (shape.HasImage)
    {
        shape.ImageData.SetImage(ImagesDir + "Watermark.png");
    }
    break;
}
```

## Step 6: Save the Modified Document
Save the modified document to the specified directory using the `Save` method. Provide the desired filename with the appropriate file extension. In this example, we save the document as "WorkingWithSdt.ModifyContentControls.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

### Example source code for Modify Content Controls using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
	{
		switch (sdt.SdtType)
		{
			case SdtType.PlainText:
			{
				sdt.RemoveAllChildren();
				Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
				Run run = new Run(doc, "new text goes here");
				para.AppendChild(run);
				break;
			}
			case SdtType.DropDownList:
			{
				SdtListItem secondItem = sdt.ListItems[2];
				sdt.ListItems.SelectedValue = secondItem;
				break;
			}
			case SdtType.Picture:
			{
				Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
				if (shape.HasImage)
				{
					shape.ImageData.SetImage(ImagesDir + "Watermark.png");
				}
				break;
			}
		}
	}
	doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");

```

That's it! You have successfully modified different types of content controls in your Word document using Aspose.Words for .NET.