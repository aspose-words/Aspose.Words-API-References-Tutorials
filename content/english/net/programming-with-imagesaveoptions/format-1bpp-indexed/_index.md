---
title: Format 1Bpp Indexed
linktitle: Format 1Bpp Indexed
second_title: Aspose.Words Document Processing API
description: Learn how to format images in 1 bpp indexed with Aspose.Words for .NET. Complete tutorial for low color depth images.
type: docs
weight: 10
url: /net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
In this tutorial, we will explore the C# source code provided for the "Format 1Bpp Indexed" functionality with Aspose.Words for .NET. This feature allows you to format images in a document in PNG format with a color depth of 1 bit per pixel (1 bpp) and an indexed color mode.

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
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(1),
     ImageColorMode = ImageColorMode.BlackAndWhite,
     PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

In this step, we configure backup options for images. We create a new `ImageSaveOptions` object specifying the desired save format, here "Png" for the PNG format. We also define the page to include in the image, the black and white color mode and the indexed 1 bpp pixel format.

## Step 4: Backing up images

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

In this last step, we save the document images in the PNG format using the `Save` method and passing the path to the output file, along with the specified save options.

Now you can run the source code to format the document images in the PNG format with a color depth of 1 bpp indexed. The resulting file will be saved in the specified directory with the name "WorkingWithImageSaveOptions.Format1BppIndexed.Png".

### Sample source code for Format 1Bpp Indexed using Aspose.Words for .NET

```csharp 
 
			 // Path to your document directory 
			 string dataDir = "YOUR DOCUMENT DIRECTORY"; 
            
            Document doc = new Document(dataDir + "Rendering.docx");

            ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
            {
                PageSet = new PageSet(1),
                ImageColorMode = ImageColorMode.BlackAndWhite,
                PixelFormat = ImagePixelFormat.Format1bppIndexed
            };

            doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
            
        
```

### Conclusion

In this tutorial, we explored the 1Bpp Indexed format feature with Aspose.Words for .NET. We learned how to format images in a document in PNG format with a color depth of 1 bit per pixel (1 bpp) and an indexed color mode.

This feature is useful when you want to get images with low color depth and small file size. The 1Bpp Indexed format allows images to be represented using an indexed color palette, which can be beneficial for some specific applications.

Aspose.Words for .NET offers a wide range of advanced features for document manipulation and generation. The 1Bpp Indexed format is one of the many powerful tools it puts at your disposal.