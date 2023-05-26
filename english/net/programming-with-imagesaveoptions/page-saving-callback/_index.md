---
title: Page Saving Callback
linktitle: Page Saving Callback
second_title: Aspose.Words for .NET API Reference
description: Learn how to customize saving document pages to images with Aspose.Words for .NET. 
type: docs
weight: 10
url: /net/programming-with-imagesaveoptions/page-saving-callback/
---

In this tutorial, we will explore the C# source code provided for using the page save callback with Aspose.Words image save options for .NET. This feature allows you to perform custom actions when saving each page of a document as an image.

## Step 1: Setting up the environment

Before you begin, make sure you've set up your development environment with Aspose.Words for .NET. Make sure you've added the necessary references and imported the appropriate namespaces.

## Step 2: Loading the document

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

In this step, we load the document using the `Document` method and passing the path to the DOCX file to load.

## Step 3: Configure image backup options

```csharp
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
     PageSavingCallback = new HandlePageSavingCallback()
};
```

In this step, we configure the image save options by creating a new `ImageSaveOptions` object. We specify the desired backup format, here "Png" for the PNG format. We use `PageSet` to specify the range of pages to save, here from the first page to the last page of the document (`doc.PageCount - 1`). We also set `PageSavingCallback` to an instance of `HandlePageSavingCallback`, which is a custom class to handle the page saving callback.

## Step 4: Implementing the Save Page Callback

```csharp
public class HandlePageSavingCallback : IPageSavingCallback
{
     public void PageSaving(PageSavingArgs args)
     {
         // Implement your custom actions here
         // You can access page information through the "args.PageIndex" property
         // You can also change save options for each page individually
     }
}
```

In this step, we implement the `HandlePageSavingCallback` class which implements the `IPageSavingCallback` interface. You can customize this class by adding your specific actions in the `PageSaving` method. You can access page information through the `args.PageIndex` property of the `PageSavingArgs` object passed as an argument.

## Step 5: Saving pages as images

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

In this final step, we save each page of the document as an image using the `Save` method and passing the path to the output file with the `.png` extension, along with the save options specified.

Now you can run the source code to perform custom actions when saving each page of the document as an image. The resulting file will be saved in the specified directory with the name "WorkingWithImageSaveOptions.PageSavingCallback.png".

### Sample source code for Page Saving Callback using Aspose.Words for .NET


```csharp 
// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY"; 


Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
	PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
	PageSavingCallback = new HandlePageSavingCallback()
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
        
```

## Conclusion

In this tutorial, we explored the page save callback functionality with Aspose.Words image save options for .NET. We learned how to perform custom actions when saving each page of a document as an image.

This feature is useful when you want to perform specific operations on each page when converting to images. You can access page information and use it to customize backup options or perform other page-specific processing.

Aspose.Words for .NET offers an extensive range of advanced features for document manipulation and generation. The Save Page Reminder is one of many powerful tools it gives you to customize the process of saving pages to images.