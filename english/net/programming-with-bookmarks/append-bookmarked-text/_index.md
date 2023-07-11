---
title: Append Bookmarked Text In Word Document
linktitle: Append Bookmarked Text In Word Document
second_title: Aspose.Words Document Processing API
description: Learn how to add text from a bookmark in a Word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-bookmarks/append-bookmarked-text/
---

In this article, we will explore the above C# source code to understand how to use Append Bookmarked Text function in Aspose.Words for .NET library. This feature allows you to add the text contained in a specific bookmark of a Word document to another document.

## Prerequisites

- Basic knowledge of the C# language.
- .NET development environment with Aspose.Words library installed.

## Step 1: Getting Paragraphs From Bookmark

Before we start adding the bookmark text, we need to get the paragraphs that contain the start and end of the bookmark. This can be done by accessing the `BookmarkStart` and `BookmarkEnd` properties of the bookmark:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## Step 2: Check Parent Paragraphs

We check if the beginning and ending paragraphs have valid parents, that is, if they really belong to a paragraph. If not, we generate an exception:

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## Step 3: Check Parents of Paragraphs

We check if the beginning and ending paragraphs have the same parent. If not, that means the paragraphs aren't contained in the same section or document, and we're throwing an exception:

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## Step 4: Copy paragraphs

We iterate through the nodes (paragraphs) from the start paragraph to the end paragraph. For each node, we create a copy and import it into the context of the destination document:

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### Example source code for Append Bookmarked Text using Aspose.Words for .NET

Here is the full example source code to demonstrate adding text from a bookmark using Aspose.Words for .NET:

```csharp

	// This is the paragraph that contains the beginning of the bookmark.
	Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

	// This is the paragraph that contains the end of the bookmark.
	Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

	if (startPara == null || endPara == null)
		throw new InvalidOperationException(
			"Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

	// Limit ourselves to a reasonably simple scenario.
	if (startPara.ParentNode != endPara.ParentNode)
		throw new InvalidOperationException(
			"Start and end paragraphs have different parents, cannot handle this scenario yet.");

	// We want to copy all paragraphs from the start paragraph up to (and including) the end paragraph,
	// therefore the node at which we stop is one after the end paragraph.
	Node endNode = endPara.NextSibling;

	for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
	{
		// This creates a copy of the current node and imports it (makes it valid) in the context
		// of the destination document. Importing means adjusting styles and list identifiers correctly.
		Node newNode = importer.ImportNode(curNode, true);

		dstNode.AppendChild(newNode);
	}

```

## Conclusion

In this article, we explored the C# source code to understand how to use the Append Bookmarked Text function of Aspose.Words for .NET. We've followed a step-by-step guide to getting paragraphs from a bookmark, verifying parents, and copying paragraphs to another document.

### FAQ's for append bookmarked text in word document

#### Q1: What are the prerequisites to use the "Add text with bookmarks" feature in Aspose.Words for .NET?

A: To use the "Add text with bookmarks" function in Aspose.Words for .NET, you need to have basic knowledge of C# language. You also need a .NET development environment with the Aspose.Words library installed.

#### Q2: How to get the paragraphs that contain the beginning and end of a bookmark in a Word document?

A: To get the paragraphs that contain the start and end of a bookmark in a Word document, you can access the `BookmarkStart` and `BookmarkEnd` properties of the bookmark. Here is a sample code:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

#### Q3: What happens if the start and end paragraphs don't have valid parents?

A: If the start and end paragraphs do not have valid parents, i.e. they are not really paragraphs, an exception will be thrown. This situation cannot be managed at this time.

