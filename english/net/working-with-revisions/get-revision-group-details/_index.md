---
title: Get Revision Group Details
linktitle: Get Revision Group Details
second_title: Aspose.Words for .NET API Reference
description: Get revision group details in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-revisions/get-revision-group-details/
---

In this step-by-step guide, we are going to show you how to get the details of a group of revisions in a Word document using Aspose.Words for .NET. We'll provide you with the complete source code and show you how to format the markdown output.

## Step 1: Loading the document

The first step is to upload the document containing the revisions.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Step 2: Browse revisions

Next, we'll loop through the revisions present in the document and display their details, such as type, author, date, and revised text.

```csharp
foreach (Revision revision in doc.Revisions)
{
     string groupText = revision.Group != null
         ? "Revision group text: " + revision.Group.Text
         : "The revision does not belong to any group";

     Console.WriteLine("Type: " + revision.RevisionType);
     Console.WriteLine("Author: " + revision.Author);
     Console.WriteLine("Date: " + revision.DateTime);
     Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
     Console.WriteLine(groupText);
}
```


### Example source code for Get Revision Group Details using Aspose.Words for .NET

Here is the complete source code to get the details of a group of revisions in a document using Aspose.Words for .NET:

```csharp

	Document doc = new Document(MyDir + "Revisions.docx");

	foreach (Revision revision in doc.Revisions)
	{
		 string groupText = revision.Group != null
			 ? "Revision group text: " + revision.Group.Text
			 : "The revision does not belong to any group";

		 Console.WriteLine("Type: " + revision.RevisionType);
		 Console.WriteLine("Author: " + revision.Author);
		 Console.WriteLine("Date: " + revision.DateTime);
		 Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
		 Console.WriteLine(groupText);
	}
	
```


