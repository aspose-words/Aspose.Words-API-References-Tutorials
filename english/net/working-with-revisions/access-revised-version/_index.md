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

## Conclusion

In this tutorial, we learned how to access the revised version of a Word document using Aspose.Words for .NET. By loading the document, navigating to the revised version, and browsing through the revisions, we were able to get specific information for paragraphs that are list items. Aspose.Words for .NET offers powerful features for manipulating Word documents, including access to reviews. You can now use this knowledge to access the revised version of your own Word documents using Aspose.Words for .NET.

### FAQ's

#### Q: How do I load a document with revisions into Aspose.Words for .NET?

A: Use the `Document` class of Aspose.Words for .NET to load a document from a file containing revisions. You can specify the full document path.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q: How do I access the revised version of a document in Aspose.Words for .NET?

A: Use the `RevisionsView` property of the `Document` object to access the revised version of the document. You can set the value of the `RevisionsView` property to `RevisionsView.Final` to show the final version without the revisions.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

#### Q: How do I browse document revisions in Aspose.Words for .NET?

A: Use a `foreach` loop to iterate through the revisions present in the document. You can use the `Revisions` property of the `Document` object to get a collection of all revisions of the document.

```csharp
foreach (Revision revision in doc.Revisions)
{
     // Process each revision here
}
```

#### Q: How to check if a paragraph is a list item in Aspose.Words for .NET?

A: Use the `IsListItem` property of the `Paragraph` object to check if a paragraph is a list item. The `IsListItem` property returns `true` if the paragraph is a list item, otherwise it returns `false`.

```csharp
if (paragraph.IsListItem)
{
     // The paragraph is a list item
}
else
{
     // The paragraph is not a list item
}
```
