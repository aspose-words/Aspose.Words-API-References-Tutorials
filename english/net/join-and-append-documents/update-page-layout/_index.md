---
title: Update Page Layout
linktitle: Update Page Layout
second_title: Aspose.Words Document Processing API
description: Learn how to update page layout when joining and appending Word documents using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/join-and-append-documents/update-page-layout/
---

This tutorial will guide you through the process of using the Update Page Layout feature of Aspose.Words for .NET. This feature ensures that the page layout is updated correctly when joining and appending Word documents.

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
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Step 3: Update Page Layout for the Destination Document

To ensure that the page layout is updated correctly before appending the source document, you can call the `UpdatePageLayout` method on the destination document.

```csharp
dstDoc.UpdatePageLayout();
```

## Step 4: Append the Source Document to the Destination Document

Now, you can append the source document to the destination document using the `AppendDocument` method of the `Document` class. The `ImportFormatMode.KeepSourceFormatting` parameter ensures that the source formatting is preserved during the append operation.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Step 5: Update Page Layout Again

After appending the source document, you need to call the `UpdatePageLayout` method on the destination document again to ensure that any changes made after the append operation are reflected in the rendered output.

```csharp
dstDoc.UpdatePageLayout();
```

## Step 6: Save the Final Document

Finally, save the merged document with the Update Page Layout feature enabled using the `Save` method of the `Document` class.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

### Example source code for Update Page Layout using Aspose.Words for .NET

Here's the full source code for the "Update Page Layout" feature in C# using Aspose.Words for .NET:

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// If the destination document is rendered to PDF, image etc.
	// or UpdatePageLayout is called before the source document. Is appended,
	// then any changes made after will not be reflected in the rendered output
	dstDoc.UpdatePageLayout();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	// For the changes to be updated to rendered output, UpdatePageLayout must be called again.
	// If not called again, the appended document will not appear in the output of the next rendering.
	dstDoc.UpdatePageLayout();
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

That's it! You have successfully implemented the Update Page Layout feature using Aspose.Words for .NET. The final document will contain the merged content with the page layout updated correctly.
