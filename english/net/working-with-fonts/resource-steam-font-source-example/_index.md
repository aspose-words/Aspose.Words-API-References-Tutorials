---
title: Resource Steam Font Source Example
linktitle: Resource Steam Font Source Example
second_title: Aspose.Words for .NET API Reference
description: Learn how to use the Resource Stream Font Source to load custom fonts into Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fonts/resource-steam-font-source-example/
---

In this tutorial, we are going to walk you through how to use Resource Flow Font Source with Aspose.Words for .NET. This font source allows you to load fonts from a resource stream, which can be useful when you want to incorporate custom fonts into your application.

## Prerequisites
Before you begin, make sure you have the following items:
- A working knowledge of the C# programming language
- The Aspose.Words library for .NET installed in your project

## Step 1: Define the document directory
First, you need to set the directory path to the location of your Word document. Replace `"YOUR DOCUMENT DIRECTORY"` in the code with the appropriate path.

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Upload Document and Set Resource Stream Font Source
Next, we'll load the document using the `Document` class and set the resource stream font source using the `FontSettings.DefaultInstance.SetFontsSources()` class. This will allow Aspose.Words to find the fonts in the resource stream.

```csharp
// Load document and set resource stream font source
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{ new SystemFontSource(), new ResourceSteamFontSource() });
```

## Step 3: Save the document
Finally, we will save the document. Fonts will be loaded from the specified resource stream and embedded in the document.

```csharp
// Save the document
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

### Sample source code for Resource Steam Font Source Example using Aspose.Words for .NET 

```csharp
// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
	{ new SystemFontSource(), new ResourceSteamFontSource() });
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

## Conclusion
In this tutorial, you learned how to use Resource Flow Font Source with Aspose.Words for .NET. This feature allows you to load fonts from a resource feed, which is useful when you want to embed custom fonts into your documents. Experiment with different fonts and explore the possibilities offered by Aspose.Words for font management.

