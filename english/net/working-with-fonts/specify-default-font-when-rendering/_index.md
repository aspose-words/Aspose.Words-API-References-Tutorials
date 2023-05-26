---
title: Specify Default Font When Rendering
linktitle: Specify Default Font When Rendering
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to specifying the default font when rendering a document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fonts/specify-default-font-when-rendering/
---

In this tutorial, we'll walk you through the step-by-step process to specify the default font when rendering a document using Aspose.Words for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. By the end of this tutorial, you will know how to specify a default font to use when rendering your documents using Aspose.Words for .NET.

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

## Step 3: Set default font
Now you can specify the default font to use when rendering by creating an instance of the `FontSettings` class and setting the `DefaultFontName` property of the `DefaultFontSubstitution` object to the `DefaultFontSubstitution` object `SubstitutionSettings` of `FontSettings`.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
```

## Step 4: Save the rendered document
Finally, you can save the rendered document to a file using the `Save()` method of the `Document` class. Be sure to specify the correct path and file name.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

### Sample source code for Specify Default Font When Rendering using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Rendering.docx");
	FontSettings fontSettings = new FontSettings();
	// If the default font defined here cannot be found during rendering then
	// the closest font on the machine is used instead.
	fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
	doc.FontSettings = fontSettings;
	doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## Conclusion
In this tutorial, we learned how to specify the default font when rendering a document using Aspose.Words for .NET. By following this step-by-step guide, you can easily set a default font to use when rendering your documents. Aspose.Words offers a powerful and flexible API for working with fonts in your documents. With this knowledge, you can control and customize the rendering of your documents to your specific needs.
