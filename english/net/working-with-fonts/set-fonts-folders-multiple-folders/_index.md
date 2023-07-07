---
title: Set Fonts Folders Multiple Folders
linktitle: Set Fonts Folders Multiple Folders
second_title: Aspose.Words for .NET API Reference
description: Step by step guide to set multiple font folders when rendering a document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fonts/set-fonts-folders-multiple-folders/
---

In this tutorial, we'll walk you through the step-by-step process to set multiple font folders when rendering a document using Aspose.Words for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. By the end of this tutorial, you will know how to specify multiple font folders to use when rendering your documents using Aspose.Words for .NET.

## Step 1: Define the document directory
First, you need to set the path to your documents directory. This is the location where you want to save your edited rendered document. Replace "YOUR DOCUMENTS DIRECTORY" with the appropriate path.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Load the document to render
Then you can load the document to render using the `Document` class. Be sure to specify the correct document path.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Step 3: Set Font Folders
Now you can set multiple font folders using the `FontSettings` class and the `SetFontsFolders()` method. You can specify the paths to font folders you want to use in an array. In this example, we have specified two font folders: "C:\MyFonts\" and "D:\Misc\Fonts\".

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
```

## Step 4: Apply Font Settings
Next, you need to apply the font settings to your document using the `FontSettings` property of the `Document` class.

```csharp
doc.FontSettings = fontSettings;
```

## Step 5: Save the rendered document
Finally, you can save the rendered document to a file using the `Save()` method of the `Document` class. Be sure to specify the correct path and file name.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

### Sample source code for Set Fonts Folders Multiple Folders using Aspose.Words for .NET 

```csharp
// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Note that this setting will override any default font sources that are being searched by default. Now only these folders will be searched for
// fonts when rendering or embedding fonts. To add an extra font source while keeping system font sources then use both FontSettings.GetFontSources and
// FontSettings.SetFontSources instead.
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

## Conclusion
In this tutorial, we learned how to set multiple font folders when rendering a document using Aspose.Words for .NET. By following this step-by-step guide, you can easily specify multiple font folders to use when rendering your documents. Aspose.Words offers a powerful and flexible API for working with fonts in your documents. With this knowledge, you can control and customize the font sources used when rendering your documents to your specific needs.

### FAQ's

#### Q: How can I set multiple font folders in Aspose.Words?

A: To set multiple font folders in Aspose.Words, you can use the `SetFontsFolders` method of the `Fonts` class providing a list of custom font folder locations.

#### Q: Does setting multiple font folders affect all documents processed with Aspose.Words?

A: Yes, setting multiple font folders affects all documents processed with Aspose.Words. Once you have defined the font folders, Aspose.Words will use these locations to search for fonts in all documents.

#### Q: How many font folders can I define in Aspose.Words?

A: You can define as many font folders as needed in Aspose.Words. There is no specific limit to the number of font folders you can define.

#### Q: How can I check the font folders defined in Aspose.Words?

A: To check the font folders defined in Aspose.Words, you can use the `GetFolders` method of the `Fonts` class to get the locations of the configured font folders.

#### Q: Do font folders need to contain specific fonts?

A: Yes, font folders should contain the fonts you want to use in your Word documents. Aspose.Words will look for fonts in the specified folders when processing documents.
