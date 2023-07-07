---
title: Set Fonts Folders
linktitle: Set Fonts Folders
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to setting font folders when rendering a document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fonts/set-fonts-folders/
---

In this tutorial, we'll walk you through the step-by-step process to set font folders when rendering a document using Aspose.Words for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. By the end of this tutorial, you will know how to specify the font folders to use when rendering your documents using Aspose.Words for .NET.

## Step 1: Define the document directory
First, you need to set the path to your documents directory. This is the location where you want to save your edited rendered document. Replace "YOUR DOCUMENTS DIRECTORY" with the appropriate path.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Set Font Sources
Then you can set the font sources using the `FontSettings.DefaultInstance` class and the `SetFontsSources()` method. In this example, we are using both a system font source and a custom folder font source. Be sure to adjust the path to the custom fonts folder according to your needs.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## Step 3: Load the document to render
Now you can load the document to render using the `Document` class. Be sure to specify the correct document path.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Step 4: Save the rendered document
Finally, you can save the rendered document to a file using the `Save()` method of the `Document` class. Be sure to specify the correct path and file name.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

### Sample source code for Set Fonts Folders using Aspose.Words for .NET 
```csharp
// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true)
});
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

## Conclusion
In this tutorial, we learned how to set font folders when rendering a document using Aspose.Words for .NET. By following this step-by-step guide, you can easily specify the font sources to use when rendering your documents. Aspose.Words offers a powerful and flexible API for working with fonts in your documents. With this knowledge, you can control and customize the font sources used when rendering your documents to your specific needs.

### FAQ's

#### Q: How can I configure font folders in a Word document using Aspose.Words?

A: To configure font folders in a Word document using Aspose.Words, you can use the API to specify custom font folders to use when generating or editing the document. This will allow Word to find the fonts required to render correctly.

#### Q: Is it possible to add custom fonts to a Word document with Aspose.Words?

A: Yes, with Aspose.Words you can add custom fonts to a Word document. The API allows you to embed specific fonts into your document, ensuring that they display correctly, even if the fonts are not installed on the end user's system.

#### Q: What happens if required fonts are missing in a Word document?

A: If required fonts are missing from a Word document, Aspose.Words can detect this issue and provide you with options to fix it. You can choose to substitute missing fonts with alternative fonts or include missing fonts in the document, which ensures correct viewing.

#### Q: How can I remove custom fonts from a Word document with Aspose.Words?

A: To remove custom fonts from a Word document using Aspose.Words, you can use the API to clean up the document and remove custom fonts that are no longer needed. This will reduce file size and make font management easier.

#### Q: Is it important to configure font folders in a Word document?

A: Yes, it is important to configure font folders in a Word document to ensure that the fonts used are displayed correctly. By specifying custom font folders for use with Aspose.Words, you ensure that the required fonts are available to render Word documents correctly.
