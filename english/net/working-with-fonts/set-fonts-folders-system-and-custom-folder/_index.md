---
title: Set Fonts Folders System And Custom Folder
linktitle: Set Fonts Folders System And Custom Folder
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to setting system and custom font folders when rendering a document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---

In this tutorial, we'll walk you through the step-by-step process to set system font folders and a custom folder when rendering a document using Aspose.Words for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. By the end of this tutorial, you will know how to specify multiple font folders, including the system folder and a custom folder, to use when rendering your documents using Aspose.Words for .NET.

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

## Step 3: Set system and custom font folders
Now you can set system font folders and a custom folder using the `FontSettings` class and the `SetFontsSources()` method. First, you need to retrieve the list of environment-dependent font sources using `GetFontsSources()` and store it in a list. Then you can create a new instance of `FolderFontSource` specifying the path to the custom folder containing your fonts. Add this instance to the list of existing font sources. Finally, use `SetFontsSources()` to update the font sources with the new list.

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## Step 4: Apply Font Settings
Next, you need to apply the font settings to your document using the `FontSettings` property of the `Document` class.

```csharp
doc.FontSettings = fontSettings;
```

## Step 5: Save the rendered document
Finally, you can save the rendered document to a file by

  using the `Save()` method of the `Document` class. Be sure to specify the correct path and file name.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

### Sample source code for Set Fonts Folders System And Custom Folder using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Rendering.docx");
	FontSettings fontSettings = new FontSettings();
	// Retrieve the array of environment-dependent font sources that are searched by default.
	// For example this will contain a "Windows\Fonts\" source on a Windows machines.
	// We add this array to a new List to make adding or removing font entries much easier.
	List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
	// Add a new folder source which will instruct Aspose.Words to search the following folder for fonts.
	FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
	// Add the custom folder which contains our fonts to the list of existing font sources.
	fontSources.Add(folderFontSource);
	FontSourceBase[] updatedFontSources = fontSources.ToArray();
	fontSettings.SetFontsSources(updatedFontSources);
	doc.FontSettings = fontSettings;
	doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## Conclusion
In this tutorial, we learned how to set system font folders and a custom folder when rendering a document using Aspose.Words for .NET. By following this step-by-step guide, you can easily specify multiple font folders, including the system folder and a custom folder, to use when rendering your documents. Aspose.Words offers a powerful and flexible API for working with fonts in your documents. With this knowledge, you can control and customize the font sources used when rendering your documents to your specific needs.
