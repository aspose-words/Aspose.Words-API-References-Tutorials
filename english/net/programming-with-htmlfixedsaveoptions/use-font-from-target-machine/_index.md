---
title: Use Font From Target Machine
linktitle: Use Font From Target Machine
second_title: Aspose.Words Document Processing API
description: Learn how to convert a Word document to fixed HTML using the target machine's fonts with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-htmlfixedsaveoptions/use-font-from-target-machine/
---

When converting a Word document to fixed HTML in a C# application, you may want to use the target machine's fonts to ensure that the rendered HTML retains the original look and style of the document. With the Aspose.Words library for .NET, you can easily specify this functionality using the HtmlFixedSaveOptions save options. In this step-by-step guide, we will walk you through how to use the C# source code of Aspose.Words for .NET to convert a Word document to fixed HTML using the target machine's fonts using the HtmlFixedSaveOptions.

## Understanding the Aspose.Words library

Before diving into the code, it's important to understand the Aspose.Words library for .NET. Aspose.Words is a powerful library to create, edit, convert and protect Word documents in different platforms including .NET. It offers many features for manipulating documents, such as inserting text, changing formatting, adding sections and much more.

## Loading the Word document

The first step is to load the Word document you want to convert to fixed HTML. Use the Document class to load the document from the source file. Here is an example :

```csharp
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");
```

In this example, we load the document "Bullet points with alternative font.docx" located in the documents directory.

## Configuring backup options

The next step is to configure the save options for converting to fixed HTML. Use the HtmlFixedSaveOptions class and set the UseTargetMachineFonts property to true to tell Aspose.Words to use fonts from the target machine. Here's how to do it:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };
```

We create a new HtmlFixedSaveOptions object and set the UseTargetMachineFonts property to true to use the target machine's fonts when converting.

## Fixed HTML document conversion

Now that we have configured the save options, we can proceed to convert the document to fixed HTML. Use the Save method of the Document class to save the converted document in fixed HTML format by specifying save options. Here is an example :

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

In this example, we save the converted document as "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html" using the specified save options.

### Example source code for HtmlFixedSaveOptions with "Use fonts from target machine" feature using Aspose.Words for .NET

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the Word document
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");

// Configure backup options with the "Use fonts from target machine" feature
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };

// Convert document to fixed HTML
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

## Conclusion

In this guide, we have explained how to convert a Word document to fixed HTML using the target machine's fonts with the Aspose.Words library for .NET. By following the provided steps and using the provided C# source code, you can easily apply this functionality in your C# application. The conversion to fixed HTML with the fonts of the target machine guarantees faithful and consistent rendering of the document in an HTML format.

