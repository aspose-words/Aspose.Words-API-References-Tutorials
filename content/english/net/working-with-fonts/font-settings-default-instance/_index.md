---
title: Font Settings Default Instance
linktitle: Font Settings Default Instance
second_title: Aspose.Words Document Processing API
description: In this tutorial, learn how to configure default font settings in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fonts/font-settings-default-instance/
---

In this tutorial, we will walk you through how to configure default font settings in a Word document using the Aspose.Words library for .NET. Default font settings allow you to specify the font sources used when loading and rendering documents. We'll take you step-by-step to help you understand and implement the code in your .NET project.

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

## Step 2: Configure Default Font Settings
Next, we'll create an instance of `FontSettings` using `FontSettings.DefaultInstance`, and then we'll specify the font sources used when loading and rendering documents. In this example, we are using a system font source and a folder font source.

```csharp
// Configure default font settings
FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## Step 3: Upload document with font settings
Now we'll load the document using `LoadOptions` and specifying the font settings to use.

```csharp
// Load the document with the font settings
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```


### Sample source code for Font Settings Default Instance using Aspose.Words for .NET 
```csharp

// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(),
	new FolderFontSource("C:\\MyFonts\\", true)
});
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Conclusion
In this tutorial, we saw how to configure default font settings in a Word document with Aspose.Words for .NET. By specifying the font sources used when loading and rendering documents, you can control the appearance of fonts in your documents. Feel free to use this feature to customize font settings in your projects.

### FAQ's

#### Q: How can I set the default font in Aspose.Words?

A: To set the default font in Aspose.Words, you can use the `FontSettings` class and the `DefaultFontName` property specifying the name of the desired font.

#### Q: Can I specify the default font size in Aspose.Words?

A: Yes, you can specify the default font size in Aspose.Words using the `DefaultFontSize` property of the `FontSettings` class. You can set the desired point size.

#### Q: Is it possible to set the default font color in Aspose.Words?

A: Yes, you can set the default font color in Aspose.Words using the `DefaultColor` property of the `FontSettings` class. You can specify the color using RGB values or predefined names.

#### Q: Do the default font settings apply to all documents?

A: Yes, default font settings apply to all documents created or edited in Aspose.Words, unless specific settings are set for an individual document.
