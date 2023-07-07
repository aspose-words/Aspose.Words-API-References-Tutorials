---
title: Get List Of Available Fonts
linktitle: Get List Of Available Fonts
second_title: Aspose.Words for .NET API Reference
description: In this tutorial, learn how to get the list of fonts available in Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fonts/get-list-of-available-fonts/
---
In this tutorial, we will explain how to get the list of fonts available in Aspose.Words for .NET. The list of available fonts lets you know which fonts you can use in your documents. We'll take you step-by-step to help you understand and implement the code in your .NET project.

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

## Step 2: Configure font sources
Next, we'll create an instance of `FontSettings` and get the existing font sources using the `GetFontsSources()` method. We will also add a new font source by specifying a folder containing fonts.

```csharp
// Configure font sources
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());

// Add a new font source
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

## Step 3: Get the list of available fonts
Now we will browse the available fonts using the `GetAvailableFonts()` method on the first updated font source.

```csharp
// Obtain the list of available fonts
foreach(PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
Console.WriteLine("Font Family Name: " + fontInfo.FontFamilyName);
Console.WriteLine("Full font name: " + fontInfo.FullFontName);
Console.WriteLine("Version: " + fontInfo.Version);
Console.WriteLine("Path: " + fontInfo.FilePath);
}
```


### Sample source code for Get List Of Available Fonts using Aspose.Words for .NET 

```csharp

// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Add a new folder source which will instruct Aspose.Words to search the following folder for fonts.
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
// Add the custom folder which contains our fonts to the list of existing font sources.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
	Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
	Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
	Console.WriteLine("Version  : " + fontInfo.Version);
	Console.WriteLine("FilePath : " + fontInfo.FilePath);
}

```

## Conclusion
In this tutorial, we saw how to get the list of fonts available in Aspose.Words for .NET. This lets you know which fonts you can use in your documents. Feel free to use this feature to choose appropriate fonts for your needs.

### FAQ's

#### Q: How can I retrieve the list of fonts available in Aspose.Words?

A: To retrieve the list of fonts available in Aspose.Words, you can use the `FontsProvider` class and the `GetAvailableFonts` method. This method will return a list of all fonts installed on your system.

#### Q: Can I filter the list of available fonts by certain criteria in Aspose.Words?

A: Yes, you can filter the list of fonts available in Aspose.Words using specific criteria. For example, you can filter fonts by family, style, or language.

#### Q: How can I use the list of available fonts in my Word documents?

A: To use the list of fonts available in your Word documents, you can browse the list and select the appropriate fonts using the methods and properties of the `FontSettings` class in Aspose.Words.
