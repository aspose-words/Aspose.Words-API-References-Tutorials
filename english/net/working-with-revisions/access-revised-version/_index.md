---
title: Access Revised Version
linktitle: Access Revised Version
second_title: Aspose.Words for .NET API Reference
description: Access a revised version of a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-revisions/access-revised-version/
---

In this step-by-step guide, we are going to show you how to access the revised version of a Word document using Aspose.Words for .NET. We'll provide you with the complete source code and show you how to format the markdown output.

## Step 1: Loading the document

The first step is to upload the document containing the revisions.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## Step 2: Access the revised version

We will now move on to the revised version of the document.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## Step 3: Browse revisions

Next, we'll loop through the revisions present in the document and display specific information for paragraphs that are list items.

```csharp
foreach (Revision revision in doc.Revisions)
{
     if (revision.ParentNode.NodeType == NodeType.Paragraph)
     {
         Paragraph paragraph = (Paragraph)revision.ParentNode;
         if (paragraph.IsListItem)
         {
             Console.WriteLine(paragraph.ListLabel.LabelString);
             Console.WriteLine(paragraph.ListFormat.ListLevel);
         }
     }
}
```

### Example source code for Access Revised Version using Aspose.Words for .NET

Here is the complete source code for accessing the revised version of a document using Aspose.Words for .NET:

```csharp

	Document doc = new Document(MyDir + "Revisions.docx");
	doc.UpdateListLabels();

	// Switch to the revised version of the document.
	doc.RevisionsView = RevisionsView.Final;

	foreach (Revision revision in doc.Revisions)
	{
		 if (revision.ParentNode.NodeType == NodeType.Paragraph)
		 {
			 Paragraph paragraph = (Paragraph)revision.ParentNode;
			 if (paragraph.IsListItem)
			 {
				 Console.WriteLine(paragraph.ListLabel.LabelString);
				 Console.WriteLine(paragraph.ListFormat.ListLevel);
			 }
		 }
	}

```



