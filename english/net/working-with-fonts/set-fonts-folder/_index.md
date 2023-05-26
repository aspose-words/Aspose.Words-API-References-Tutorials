---
title: Set Fonts Folder
linktitle: Set Fonts Folder
second_title: Aspose.Words for .NET API Reference
description: Learn how to set the font directory in Aspose.Words for .NET and ensure the availability of fonts used in your documents.
type: docs
weight: 10
url: /net/working-with-fonts/set-fonts-folder/
---
In this tutorial, we will show you how to set fonts directory in Aspose.Words for .NET. You will learn how to specify the directory containing the fonts used in your Word document.

## Prerequisites
Before you begin, make sure you have the following items:
- A working knowledge of the C# programming language
- The Aspose.Words library for .NET installed in your project

## Step 1: Define the document directory
Start by setting the directory path to the location of your Word document. Replace `"YOUR DOCUMENT DIRECTORY"` in the code with the appropriate path.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Set font directory
Create an instance of the `FontSettings` class and use the `SetFontsFolder` method to specify the directory containing the fonts. Replace `"Fonts"` with the name of the actual fonts directory.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
```

## Step 3: Load the document with font settings
Use the `LoadOptions` class to specify font settings in the `FontSettings` option. Then use the `Document` class to load the document using these options.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

### Sample source code for Set Fonts Folder using Aspose.Words for .NET 

```csharp

// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Conclusion
Congratulation ! You now know how to set the fonts directory in Aspose.Words for .NET. You can use this feature to ensure the availability of fonts used in your document and to ensure consistency in the display of fonts.

