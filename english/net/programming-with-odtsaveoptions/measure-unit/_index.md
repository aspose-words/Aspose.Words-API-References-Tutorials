---
title: Measure Unit
linktitle: Measure Unit
second_title: Aspose.Words for .NET API Reference
description: Learn how to specify the unit of measure when converting a Word document to ODT with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-odtsaveoptions/measure-unit/
---

When you convert a Word document to OpenDocument Text (ODT) format in a C# application, you may want to specify the unit of measurement used for measurable formatting and content properties. With the Aspose.Words library for .NET, you can easily specify this functionality using the OdtSaveOptions save options. In this step-by-step guide, we will walk you through how to use Aspose.Words for .NET C# source code to convert a Word document to ODT by specifying the unit of measure using OdtSaveOptions.

## Understanding the Aspose.Words library

Before diving into the code, it's important to understand the Aspose.Words library for .NET. Aspose.Words is a powerful library to create, edit, convert and protect Word documents in different platforms including .NET. It offers many features for manipulating documents, such as inserting text, changing formatting, adding sections and much more.

## Loading the Word document

The first step is to load the Word document you want to convert to ODT. Use the Document class to load the document from the source file. Here is an example :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

In this example, we load the document "Document.docx" located in the documents directory.

## Configuring backup options

The next step is to configure the backup options for converting to ODT. Use the OdtSaveOptions class and set the MeasureUnit property to the desired value. For example, if you want to use inches as the unit of measurement, set MeasureUnit to OdtSaveMeasureUnit.Inches. Here's how to do it:

```csharp
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

We create a new OdtSaveOptions object and set the MeasureUnit property to the desired value, in our case, OdtSaveMeasureUnit.Inches to use inches as the measurement unit.

## Convert document to ODT

Now that we have configured the save options, we can proceed to convert the document to ODT. Use the Save method of the Document class to save the converted document in ODT format by specifying save options. Here is an example :

```csharp
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

In this example, we save the converted document as "WorkingWithOdtSaveOptions.MeasureUnit.odt" using the specified save options.

### Example source code for OdtSaveOptions with "Unit of measure" functionality using Aspose.Words for .NET



```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the Word document
Document doc = new Document(dataDir + "Document.docx");

// Configuration of backup options with the "Unit of measurement" feature
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };

// Convert the document to ODT
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

## Conclusion

In this guide, we have explained how to convert a Word document to ODT by specifying the unit of measurement using the OdtSaveOptions save options with the Aspose.Words library for .NET. By following the provided steps and using the provided C# source code, you can easily apply this functionality in your C# application. Specifying the unit of measurement when converting to ODT allows you to control the formatting and dimensions of the resulting document according to your specific needs.