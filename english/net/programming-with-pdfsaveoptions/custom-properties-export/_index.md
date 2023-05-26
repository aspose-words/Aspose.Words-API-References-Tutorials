---
title: Custom Properties Export
linktitle: Custom Properties Export
second_title: Aspose.Words for .NET API Reference
description: Learn how to export custom properties when converting documents to PDF with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfsaveoptions/custom-properties-export/
---

In this tutorial, we'll walk you through the steps to export a document's custom properties using Aspose.Words for .NET. Exporting custom properties allows you to include additional information in the generated PDF document. Follow the steps below:

## Step 1: Creating a Document and Adding Custom Properties

Start by creating an instance of the Document class:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Step 2: Add custom properties
Next, add the desired custom properties. For example, to add a "Company" property with the value "Aspose", use the `Add` method of the CustomDocumentProperties collection:

```csharp
doc.CustomDocumentProperties.Add("Company", "Aspose");
```

You can add as many custom properties as needed.

## Step 3: Set PDF export options

Create an instance of the PdfSaveOptions class and specify how to export custom properties:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };
```

This option controls the export of custom properties when converting to PDF.

## Step 4: Convert Document to PDF

Use the `Save` method to convert the document to PDF specifying conversion options:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);
```

Make sure to specify the correct path to save the converted PDF.

### Example source code for Custom Properties Export using Aspose.Words for .NET

Here is the complete source code to export custom properties from a document using Aspose.Words for .NET:


```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	doc.CustomDocumentProperties.Add("Company", "Aspose");

	PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);

```

By following these steps, you can easily export custom properties of a document when converting to PDF with Aspose.Words for .NET.


