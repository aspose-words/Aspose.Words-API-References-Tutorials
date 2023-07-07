---
title: Get Revision Types Of Words
linktitle: Get Revision Types Of Words
second_title: Aspose.Words for .NET API Reference
description: Get revision types of words in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-revisions/get-revision-types/
---

In this step by step guide, we are going to tell you how to get the types of words revisions in a Word document using Aspose.Words for .NET. We'll provide you with the complete source code and show you how to format the markdown output.

## Step 1: Loading the document

The first step is to upload the document containing the revisions.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Step 2: Step through the paragraphs

Next, we'll go through the paragraphs of the document and check the types of words revisions associated with each paragraph.

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

## Conclusion

In this tutorial, we learned how to get the types of words revisions in a Word document using Aspose.Words for .NET. We followed the steps to load the document, go through the paragraphs, and check the types of word reviews associated with each paragraph. Now you can apply this knowledge to analyze word reviews in your own Word documents using Aspose.Words for .NET.

### FAQ's for get revision types of words

#### Q: How to upload a document in Aspose.Words for .NET?

A: Use the `Document` class of Aspose.Words for .NET to load a document from a file. You can specify the full document path.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q: How do I loop through paragraphs in a document in Aspose.Words for .NET?

A: Use the `Paragraphs` property of the document section to get the collection of paragraphs. You can then use a loop to loop through each paragraph.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     // Process each paragraph here
}
```

#### Q: How to check if a paragraph has been moved (deleted) in Aspose.Words for .NET?

A: Use a paragraph's `IsMoveFromRevision` property to check if it has been moved (deleted).

```csharp
if (paragraph. IsMove

FromRevision)
{
     // The paragraph has been moved (deleted)
}
```

#### Q: How to check if a paragraph has been moved (inserted) in Aspose.Words for .NET?

A: Use a paragraph's `IsMoveToRevision` property to check if it has been moved (inserted).

```csharp
if (paragraph.IsMoveToRevision)
{
     // The paragraph has been moved (inserted)
}
```
