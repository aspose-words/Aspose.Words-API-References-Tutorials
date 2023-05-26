---
title: Set True Type Fonts Folder
linktitle: Set True Type Fonts Folder
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to setting the true type fonts folder when rendering a document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fonts/set-true-type-fonts-folder/
---

In this tutorial, we'll walk you through the step-by-step process to set the true type fonts folder when rendering a document using Aspose.Words for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. At the end of this tutorial, you will know how to specify a custom folder containing True Type fonts to use when rendering your documents using Aspose.Words for .NET.

## Step 1: Define the document directory
First, you need to set the path to your documents directory. This is the location where you want to save your edited rendered document. Replace "YOUR DOCUMENTS DIRECTORY" with the appropriate path.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Load the document to render
Next, you need to load the document to render using the `Document` class. Be sure to specify the correct document path.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Step 3: Set True Type Fonts Folder
Now you can specify the folder of true type fonts to use when rendering by creating an instance of the `FontSettings` class and using the `SetFontsFolder()` method to set the fonts folder. You can specify a custom folder containing your True Type fonts. The second parameter to `SetFontsFolder()` indicates whether you want to search subfolders of the specified folder as well.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
doc.FontSettings = fontSettings;
```

## Step 4: Save the rendered document
Finally, you can save the rendered document to a file using the `Save()` method of the `Document` class. Be sure to specify the correct path and file name.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

### Sample source code for Set True Type Fonts Folder using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Rendering.docx");
	FontSettings fontSettings = new FontSettings();
	// Note that this setting will override any default font sources that are being searched by default. Now only these folders will be searched for
	// Fonts when rendering or embedding fonts. To add an extra font source while keeping system font sources then use both FontSettings.GetFontSources and
	// FontSettings.SetFontSources instead
	fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
	// Set font settings
	doc.FontSettings = fontSettings;
	doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

## Conclusion
In this tutorial, we learned how to set the true type fonts folder when rendering a document using Aspose.Words for .NET. By following this step-by-step guide, you can easily specify a custom folder containing True Type fonts to use when rendering your documents. Aspose.Words offers a powerful and flexible API for working with fonts in your documents. With this knowledge, you can control and customize the fonts used when rendering your documents to your specific needs.
