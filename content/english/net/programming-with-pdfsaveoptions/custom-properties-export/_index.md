---
title: Export Custom Properties in a PDF Document
linktitle: Export Custom Properties in a PDF Document
second_title: Aspose.Words Document Processing API
description: Learn how to export custom properties when converting documents to PDF with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-pdfsaveoptions/custom-properties-export/
---

In this tutorial, we'll walk you through the steps to export a document's custom properties in a PDF document using Aspose.Words for .NET. Exporting custom properties allows you to include additional information in the generated PDF document. Follow the steps below:

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


## Conclusion

In this tutorial, we explained how to export custom properties from a document into a PDF document using Aspose.Words for .NET. By following the steps described, you can easily include additional information in the generated PDF document by exporting the document's custom properties. Take advantage of the features of Aspose.Words for .NET to personalize and enrich your PDF documents by exporting custom properties.

### Frequently Asked Questions

#### Q: What is exporting custom properties to a PDF document?
A: Exporting custom properties to a PDF document allows additional information to be included in the generated PDF document. Custom properties are metadata specific to your document, such as tags, keywords, or credentials. By exporting these custom properties, you can make them available to users when viewing the PDF document.

#### Q: How can I export a document's custom properties to a PDF document using Aspose.Words for .NET?
A: To export a document's custom properties to a PDF document using Aspose.Words for .NET, follow these steps:

Create an instance of the `Document` class.

Add the desired custom properties using the `CustomDocumentProperties` collection. For example, use the `Add` method to add a "Company" property with the value "Aspose".

Create an instance of the `PdfSaveOptions` class and specify how to export custom properties using the `CustomPropertiesExport` property. The `PdfCustomPropertiesExport.Standard` value exports custom properties according to default settings.

Use the `Save` method of the `Document` class to convert the document to PDF specifying the conversion options.

#### Q: How can I access custom properties of a PDF document?
A: To access the custom properties of a PDF document, you can use a compatible PDF reader that supports viewing document properties. Most common PDF readers, such as Adobe Acrobat Reader, provide access to metadata and properties of a PDF document. You can usually find these options under the "File" menu or by right-clicking the document and selecting "Properties."