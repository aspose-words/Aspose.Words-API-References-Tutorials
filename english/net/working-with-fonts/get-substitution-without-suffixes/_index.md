---
title: Get Substitution Without Suffixes
linktitle: Get Substitution Without Suffixes
second_title: Aspose.Words for .NET API Reference
description: In this tutorial, learn how to get suffixless overrides in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fonts/get-substitution-without-suffixes/
---

In this tutorial, we are going to show you how to get the overrides without suffixes in a Word document using the Aspose.Words library for .NET. Substitutions without suffixes are used to solve font substitution problems when displaying or printing documents. We'll take you step-by-step to help you understand and implement the code in your .NET project.

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

## Step 2: Load the document and configure substitutions without suffixes
Next, we'll load the document using the `Document` class and configure suffixless substitutions using the `DocumentSubstitutionWarnings` class. We will also add a font source by specifying a folder containing the fonts.

```csharp
// Load the document and configure substitutions without suffixes
Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;

List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

## Step 3: Save the document
Finally, we'll save the document with the no-suffix overrides applied.

```csharp
// Save the document
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

### Sample source code for Get Substitution Without Suffixes using Aspose.Words for .NET 
```csharp

// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");

```

## Conclusion
In this tutorial, we saw how to get the overrides without suffixes in a Word document with Aspose.Words for .NET. Substitutions without suffixes are useful for solving font substitution problems. Feel free to use this feature to improve the display and printing of your documents.

