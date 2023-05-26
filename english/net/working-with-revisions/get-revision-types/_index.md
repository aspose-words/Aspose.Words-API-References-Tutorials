---
title: Get Revision Types
linktitle: Get Revision Types
second_title: Aspose.Words for .NET API Reference
description: Get revision types in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-revisions/get-revision-types/
---

In this step by step guide, we are going to tell you how to get the types of revisions in a Word document using Aspose.Words for .NET. We'll provide you with the complete source code and show you how to format the markdown output.

## Step 1: Loading the document

The first step is to upload the document containing the revisions.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Step 2: Step through the paragraphs

Next, we'll go through the paragraphs of the document and check the types of revisions associated with each paragraph.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     if (paragraphs[i].IsMoveFromRevision)
         Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
     if (paragraphs[i].IsMoveToRevision)
         Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

### Example source code for Get Revision Types using Aspose.Words for .NET

Here is the full source code for getting revision types in a document using Aspose.Words for .NET:

```csharp

	Document doc = new Document(MyDir + "Revisions.docx");

	ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
	for (int i = 0; i < paragraphs.Count; i++)
	{
		 if (paragraphs[i].IsMoveFromRevision)
			 Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
		 if (paragraphs[i].IsMoveToRevision)
			 Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
	}

```

