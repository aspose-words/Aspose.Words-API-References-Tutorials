---
title: Get Revision Groups
linktitle: Get Revision Groups
second_title: Aspose.Words for .NET API Reference
description: Get revision groups in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-revisions/get-revision-groups/
---

In this step by step guide, we are going to tell you how to get the revision groups in a Word document using Aspose.Words for .NET. We'll provide you with the complete source code and show you how to format the markdown output.

## Step 1: Loading the document

The first step is to upload the document containing the revisions.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Step 2: Browse Revision Groups

Next, we will loop through the revision groups present in the document and display their details, such as author, revision type, and revised text.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
     Console.WriteLine(group.Text);
}
```


### Example source code for Get Revision Groups using Aspose.Words for .NET

Here is the complete source code to get the revision groups in a document using Aspose.Words for .NET:

```csharp

	Document doc = new Document(MyDir + "Revisions.docx");

	foreach(RevisionGroup group in doc.Revisions.Groups)
	{
		 Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
		 Console.WriteLine(group.Text);
	}
	
```



