---
title: Set Fonts Folders With Priority
linktitle: Set Fonts Folders With Priority
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to setting font folders with priority when rendering a document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fonts/set-fonts-folders-with-priority/
---

In this tutorial, we'll walk you through the step-by-step process to set font folders with priority when rendering a document using Aspose.Words for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. At the end of this tutorial, you will know how to specify multiple font folders with custom search priority when rendering your documents using Aspose.Words for .NET.

## Step 1: Define the document directory
First, you need to set the path to your documents directory. This is the location where you want to save your edited rendered document. Replace "YOUR DOCUMENTS DIRECTORY" with the appropriate path.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Set font folders with priority
Then you can set the font folders with priority using the `FontSettings` class and the `SetFontsSources()` method. You can specify multiple font sources using instances of `SystemFontSource` and `FolderFontSource`. In this example, we have defined two font sources: the default system font source and a custom font folder with a priority of 1.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

## Step 3: Load the document to render
Now you can load the document to render using the `Document` class. Be sure to specify the correct document path.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Step 4: Save the rendered document
Finally, you can save the rendered document to a file using the `Save()` method of the `Document` class. Be sure to specify the correct path and file name.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

### Sample source code for Set Fonts Folders With Priority using Aspose.Words for .NET 
```csharp
// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true,1)
});
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

## Conclusion
In this tutorial, we learned how to set font folders with priority when rendering a document using Aspose.Words for .NET. By following this step-by-step guide, you can easily specify multiple font folders with custom search priority when rendering your documents. Aspose.Words offers a powerful and flexible API for working with fonts in your documents. With this knowledge, you can control and customize the font sources used when rendering your documents to your specific needs.

### FAQ's

#### Q: How can I set font folders with priority in Aspose.Words?

A: To set font folders with priority in Aspose.Words, you can use the `SetFontsFoldersWithPriority` method of the `Fonts` class by specifying the font folder locations and their order of priority.

#### Q: What happens if a font is present in several folders with different priority?

A: If a font is present in multiple folders with different priority, Aspose.Words will use the version from the folder with the highest priority when processing documents.

#### Q: Can I specify multiple font folders with the same priority in Aspose.Words?

A: Yes, you can specify multiple font folders with the same priority in Aspose.Words. Aspose.Words will consider them all with equal priority when searching for fonts in your documents.

#### Q: How can I check the font folders defined with priority in Aspose.Words?

A: To check the font folders defined with priority in Aspose.Words, you can use the `GetFolders` method of the `Fonts` class to get the list of configured font folders including their priority order.

#### Q: What is the use of setting font folders with priority in Aspose.Words?

A: Setting font folders with priority in Aspose.Words allows you to control the search order of fonts in your Word documents. This helps you ensure that the fonts you want are used and avoid unwanted font substitution issues.
