---
title: Set Font Fallback Settings
linktitle: Set Font Fallback Settings
second_title: Aspose.Words Document Processing API
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

### FAQ's

#### Q: How can I set font substitution settings in a Word document with Aspose.Words?

A: To set font substitution settings in a Word document with Aspose.Words, you can use API to specify fallback fonts to use when required fonts are not available. This ensures consistent text visualization, even without the original fonts.

#### Q: Is it possible to handle fallback fonts when overriding in a Word document with Aspose.Words?

A: Yes, with Aspose.Words you can manage fallback fonts when substituting in a Word document. The API allows you to detect missing fonts and specify appropriate fallback fonts to maintain consistent text appearance even when fonts are substituted.

#### Q: Why is it important to correctly configure font substitution settings in a Word document?

A: It is important to correctly configure font substitution settings in a Word document to maintain the visual integrity of the text. By setting the appropriate fallback fonts with Aspose.Words, you ensure that the text will be displayed consistently, even if the required fonts are not available.

#### Q: How can I detect missing fonts when substituting in a Word document with Aspose.Words?

A: Aspose.Words allows you to detect missing fonts during substitution in a Word document using the API. You can use methods provided by Aspose.Words to check the availability of required fonts and take appropriate action in case of missing fonts.

#### Q: Does font substitution affect the layout of my Word document?

A: Font substitution can affect the layout of your Word document if the fallback fonts have different dimensions than the original fonts. However, by choosing fallback fonts wisely and configuring font substitution settings with Aspose.Words, you can minimize layout impacts.
