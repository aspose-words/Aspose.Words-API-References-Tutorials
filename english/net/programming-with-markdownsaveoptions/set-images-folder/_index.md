---
title: Set Images Folder
linktitle: Set Images Folder
second_title: Aspose.Words for .NET API Reference
description: Learn how to set the images folder when exporting to Markdown with Aspose.Words for .NET. Customize the placement of images for better organization and integration.
type: docs
weight: 10
url: /net/programming-with-markdownsaveoptions/set-images-folder/
---

Here is a step by step guide to explain the following C# source code which helps to set images folder for Markdown export options using Aspose.Words library for .NET. Make sure you have included the Aspose.Words library in your project before using this code.

## Step 1: Set document directory path

```csharp
// The path to the documents directory.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Be sure to specify the correct path to your documents directory where the document containing the images is located.

## Step 2: Load the document containing the images

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

We load the specified document that contains the images we want to export with Markdown options.

## Step 3: Set images folder for Markdown export options

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };
```

We create an instance of `MarkdownSaveOptions` and set the path to the images folder using the `ImagesFolder` property. Make sure to specify the correct path to the folder where you want to save the exported images.

## Step 4: Save the document with Markdown export options

```csharp
using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

We save the document to a memory stream using the specified Markdown export options. You can then use the flow to perform other operations, such as saving Markdown content to a file.

### Example source code to set images folder for MarkdownSaveOptions with Aspose.Words for .NET

```csharp
// The path to the documents directory.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Image bullet points.docx");

MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };

using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

This source code demonstrates how to load a document that contains images and then set the images folder for Markdown export options. Using the options specified, the document is then saved to a memory stream. This allows you to customize the location of the images folder when exporting Markdown content.
