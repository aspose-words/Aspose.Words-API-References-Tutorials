---
title: Write All Css Rules In Single File
linktitle: Write All Css Rules In Single File
second_title: Aspose.Words for .NET API Reference
description: Learn how to convert a Word document to fixed HTML by writing all CSS rules in a single file with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-htmlfixedsaveoptions/write-all-css-rules-in-single-file/
---

When converting a Word document to fixed HTML in a C# application, you may want to consolidate all CSS rules into a single file for better organization and portability. With the Aspose.Words library for .NET, you can easily specify this functionality using the HtmlFixedSaveOptions save options. In this step-by-step guide, we will walk you through how to use Aspose.Words for .NET C# source code to convert a Word document to fixed HTML by writing all CSS rules in a single file using save options HtmlFixedSaveOptions.

## Understanding the Aspose.Words library

Before diving into the code, it's important to understand the Aspose.Words library for .NET. Aspose.Words is a powerful library to create, edit, convert and protect Word documents in different platforms including .NET. It offers many features for manipulating documents, such as inserting text, changing formatting, adding sections and much more.

## Loading the Word document

The first step is to load the Word document you want to convert to fixed HTML. Use the Document class to load the document from the source file. Here is an example :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

In this example, we load the document "Document.docx" located in the documents directory.

## Configuring backup options

The next step is to configure the save options for converting to fixed HTML. Use the HtmlFixedSaveOptions class and set the SaveFontFaceCssSeparately property to false to write all CSS rules in a single file. Here's how to do it:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };
```

We create a new HtmlFixedSaveOptions object and set the SaveFontFaceCssSeparately property to false to write all CSS rules in a single file.

## Fixed HTML document conversion

Now that we have configured the save options, we can proceed to convert the document to fixed HTML. Use the Save method of the Document class to save the converted document in fixed HTML format by specifying save options. Here is an example :

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

In this example, we save the converted document as "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html" using the specified save options.

### Example source code for HtmlFixedSaveOptions with "Write all CSS rules in one file" feature using Aspose.Words for .NET

```csharp
// Access path to your document directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the Word document
Document doc = new Document(dataDir + "Document.docx");

// Configure backup options with "Write all CSS rules in one file" feature
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };

// Convert document to fixed HTML
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

## Conclusion

In this guide, we have covered how to convert a Word document to fixed HTML by writing all CSS rules in a single file using HtmlFixedSaveOptions with Aspose.Words library for .NET. By following the provided steps and using the provided C# source code, you can easily apply this functionality in your C# application. Writing all the CSS rules in a single file makes it easier to organize and manage the HTML code generated during document conversion.
