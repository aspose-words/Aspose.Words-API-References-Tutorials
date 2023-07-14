---
title: Do Not Save Picture Bullet
linktitle: Do Not Save Picture Bullet
second_title: Aspose.Words Document Processing API
description: Learn how to disable saving image bullets in Word documents using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-docsaveoptions/do-not-save-picture-bullet/
---

Picture bullets are a commonly used feature in Word documents to add custom bullets. However, in some cases it may be necessary to disable image bullet registration when manipulating documents using the Aspose.Words Library for .NET. In this step-by-step guide, we will explain how to use Aspose.Words C# source code for .NET to disable image bullet saving using DocSaveOptions save options.

## Understanding the Aspose.Words library

Before diving into the code, it's important to understand the Aspose.Words library for .NET. Aspose.Words is a powerful library to create, edit, convert and protect Word documents in different platforms including .NET. It offers many features for manipulating documents, such as inserting text, changing formatting, adding sections and much more.

## Step 1: Setting the Documents Directory

The first step is to define the directory where your documents are located. You must specify the full directory path. For example :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to your documents directory.

## Step 2: Loading the Document with Image Bullets

Next, you need to load the document with image bullets. Use the Document class to load the document from a file. For example :

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

In this example we are loading the document from the file "Image bullet points.docx"

  located in the documents directory.

## Step 3: Configure recording options

Now let's configure the save options for our document. Use the DocSaveOptions class to specify save settings. For example :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };
```

In this example, we create a new DocSaveOptions object and set the SavePictureBullet property to false to disable saving picture bullets.

## Step 4: Enable "Do Not Save Picture Bullet" Feature

To enable the "Do Not Save Picture Bullet" feature, we have already configured the save options with SavePictureBullet set to false. This ensures that image bullets are not saved in the final document.

## Step 5: Save the document

Finally, you can save the document using the Save method of the Document class. Specify the full path to the file and the desired file name. For example :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

Be sure to replace "dataDir" with the directory path to your documents.

## Example source code for DocSaveOptions save options with "Do Not Save Picture Bullet" functionality using Aspose.Words for .NET

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the document with image bullets
Document doc = new Document(dataDir + "Image bullet points.docx");

// Configure save options with the "Do Not Save Picture Bullet" feature
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };

// Save the document with the specified options
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

## Conclusion

In this guide, we covered how to disable saving image bullets in a document using the Aspose.Words library for .NET. By following the provided steps and using the provided C# source code, you can easily apply this functionality in your C# application. Disabling picture bullet saving can be useful in some situations to preserve document structure and formatting without saving picture bullets.
