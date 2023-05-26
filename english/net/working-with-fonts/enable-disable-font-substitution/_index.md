---
title: Enable Disable Font Substitution
linktitle: Enable Disable Font Substitution
second_title: Aspose.Words for .NET API Reference
description: In this tutorial, learn how to enable or disable font substitution in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fonts/enable-disable-font-substitution/
---
In this tutorial, we will walk you through how to enable or disable font substitution in a Word document when rendering it using the Aspose.Words library for .NET. Enabling or disabling font substitution allows you to control whether missing fonts are automatically replaced with a default font. We'll take you step-by-step to help you understand and implement the code in your .NET project.

## Prerequisites
Before you begin, make sure you have the following items:
- A working knowledge of the C# programming language
- The Aspose.Words library for .NET installed in your project
- A Word document that you want to render with or without font substitution

## Step 1: Define the document directory
First, you need to set the directory path to the location of your Word document. Replace `"YOUR DOCUMENT DIRECTORY"` in the code with the appropriate path.

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Upload the document and configure the font settings
Next, we'll load the Word document you want to render and create an instance of the `FontSettings` class to handle the font settings. We'll set the default font override by specifying the font name in `DefaultFontName` and disable font information override with `Enabled` set to `false`.

```csharp
// Load the document
Document doc = new Document(dataDir + "Rendering.docx");

// Configure font settings
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;

// Apply the font settings to the document
doc.FontSettings = fontSettings;
```

## Step 3: Save the rendered document
Finally, we'll save the rendered document, which will respect the defined font override settings.

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```


### Sample source code for Enable Disable Font Substitution using Aspose.Words for .NET 

```csharp

// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");

```

## Conclusion
In this tutorial, we saw how to enable or disable font substitution in a Word document when rendering it with Aspose.Words for .NET. By controlling font substitution, you can influence how missing fonts are handled in your rendered documents. Do not hesitate to use this feature to customize the management of fonts in your Word documents.