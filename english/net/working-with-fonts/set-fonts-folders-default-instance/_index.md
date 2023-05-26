---
title: Set Fonts Folders Default Instance
linktitle: Set Fonts Folders Default Instance
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to setting the default font folder when rendering a document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fonts/set-fonts-folders-default-instance/
---

In this tutorial, we'll walk you through the step-by-step process to set the default font folder when rendering a document using Aspose.Words for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. At the end of this tutorial, you will know how to set the default font folder to use when rendering your documents using Aspose.Words for .NET.

## Step 1: Define the document directory
First, you need to set the path to your documents directory. This is the location where you want to save your edited rendered document. Replace "YOUR DOCUMENTS DIRECTORY" with the appropriate path.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Set default font folder
Then you can set the default font folder using the `FontSettings.DefaultInstance` class and the `SetFontsFolder()` method. Specify the path to the fonts folder you want to use as the default folder.

```csharp
FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
```

## Step 3: Load the document to render
Now you can load the document to render using the `Document` class. Be sure to specify the correct document path.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Step 4: Save the rendered document
Finally, you can save the rendered document to a file using the `Save()` method of the `Document` class. Be sure to specify the correct path and file name.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

### Sample source code for Set Fonts Folders Default Instance using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
	Document doc = new Document(dataDir + "Rendering.docx");
	doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

## Conclusion
In this tutorial, we learned how to set the default font folder when rendering a document using Aspose.Words for .NET. By following this step-by-step guide, you can easily specify which folder of fonts to use as the default folder when rendering your documents. Aspose.Words offers a powerful and flexible API for working with fonts in your documents. With this knowledge, you can control and customize the font sources used when rendering your documents to your specific needs.
