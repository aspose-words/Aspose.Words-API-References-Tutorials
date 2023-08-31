---
title: Keep Source Together
linktitle: Keep Source Together
second_title: Aspose.Words Document Processing API
description: Learn how to use Aspose.Words for .NET to join and append Word documents while keeping the source content together with the destination document.
type: docs
weight: 10
url: /net/join-and-append-documents/keep-source-together/
---

This tutorial will guide you through the process of using the Keep Source Together feature of Aspose.Words for .NET. This feature allows you to join and append multiple Word documents while keeping the source document's content together with the destination document's content. 

## Prerequisites

Before you begin, make sure you have the following:

1. Aspose.Words for .NET installed. You can download it from the Aspose website or install it via NuGet.
2. Visual Studio or any other C# development environment.

## Step 1: Initialize the Document Directories

First, you need to set the path to your document directory. Modify the value of the `dataDir` variable to the path where your documents are located.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Load the Source and Destination Documents

Next, you need to load the source and destination documents using the Aspose.Words `Document` class. Update the file names in the `Document` constructor according to your document names.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Step 3: Set the Source Document to Appear After the Destination Document's Content

To ensure that the source document appears immediately after the destination document's content, you need to set the `SectionStart` property of the first section in the source document to `SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Step 4: Set "Keep with Next" Paragraph Formatting for Source Document

To keep the paragraphs in the source document together, you can iterate through each paragraph in the document and set the `KeepWithNext` property to `true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Step 5: Append the Source Document to the Destination Document

Now, you can append the source document to the destination document using the `AppendDocument` method of the `Document` class. The `ImportFormatMode.KeepSourceFormatting` parameter ensures that the source formatting is preserved during the append operation.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Step 6: Save the Final Document

Finally, save the merged document with the "Keep Source Together" feature enabled using the `Save` method of the `Document` class.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### Example source code for Keep Source Together using Aspose.Words for .NET 

Here's the full source code for the "Keep Source Together" feature in C# using Aspose.Words for .NET:


```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Set the source document to appear straight after the destination document's content.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

That's it! You have successfully implemented the Keep Source Together feature using Aspose.Words for .NET. The final document will contain the merged content with the paragraphs in the source document kept together.
