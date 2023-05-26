---
title: Set Font Fallback Settings
linktitle: Set Font Fallback Settings
second_title: Aspose.Words for .NET API Reference
description: Learn how to set font substitution settings in Aspose.Words for .NET and customize font substitution in your Word documents.
type: docs
weight: 10
url: /net/working-with-fonts/set-font-fallback-settings/
---
In this tutorial, we will show you how to set font substitution settings in a Word document using Aspose.Words for .NET. Font substitution settings allow you to specify replacement fonts to use when the specified fonts are not available.

## Prerequisites
Before you begin, make sure you have the following items:
- A working knowledge of the C# programming language
- The Aspose.Words library for .NET installed in your project

## Step 1: Define the document directory
Start by setting the directory path to the location of your Word document. Replace `"YOUR DOCUMENT DIRECTORY"` in the code with the appropriate path.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Load font substitution settings
Create an instance of the `FontSettings` class and use the `Load` method to load font override settings from an XML file. The specified XML file must contain the font substitution rules to use.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font Fallback Rules.xml");
```

## Step 3: Apply font substitution settings
Associate font substitution settings with the document by assigning them to the document's `FontSettings` property.

```csharp
doc.FontSettings = fontSettings;
```

## Step 4: Save the document
Save the document using the `Save` method of the `Document` with the appropriate path and filename.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

### Sample source code for Set Font Fallback Settings using Aspose.Words for .NET 
```csharp
// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font fallback rules.xml");
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

## Conclusion
In this tutorial, you learned how to set font substitution settings in a Word document using Aspose.Words for .NET. Experiment with different font substitution rules to ensure your document looks consistent, even when the specified fonts aren't available.

