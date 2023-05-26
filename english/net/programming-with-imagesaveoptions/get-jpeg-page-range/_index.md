---
title: Get Jpeg Page Range
linktitle: Get Jpeg Page Range
second_title: Aspose.Words for .NET API Reference
description: Learn how to get a range of JPEG pages with Aspose.Words for .NET. Complete tutorial for extracting custom images.
type: docs
weight: 10
url: /net/programming-with-imagesaveoptions/get-jpeg-page-range/
---

In this tutorial, we will explore the C# source code provided for the "Get Range of JPEG Pages" feature with Aspose.Words for .NET. This feature allows you to convert a specific range of pages of a document into images in JPEG format.

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
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);
options. PageSet = new PageSet(0);
options. ImageBrightness = 0.3f;
options. ImageContrast = 0.7f;
options. HorizontalResolution = 72f;
```

In this step, we configure backup options for images. We create a new `ImageSaveOptions` object specifying the desired save format, here "Jpeg" for the JPEG format. We also set the range of pages to convert using the `PageSet` object. Finally, we adjust the brightness and contrast of the image using the `ImageBrightness` and `ImageContrast` properties, respectively. We also change the horizontal resolution using the `HorizontalResolution` property.

## Step 4: Backing up images

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
```

In this last step, we save the images of the specified page range in the JPEG format using the `Save` method and passing the path to the output file, along with the specified save options.

Now you can run the source code to convert a specific range of pages in your document to JPEG images. The resulting file will be saved in the specified directory with the name "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg".

### Sample source code for Get Jpeg Page Range using Aspose.Words For .NET

```csharp 
 // Path to your document directory 
 string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

// Set the "PageSet" to "0" to convert only the first page of a document.
options.PageSet = new PageSet(0);

// Change the image's brightness and contrast.
// Both are on a 0-1 scale and are at 0.5 by default.
options.ImageBrightness = 0.3f;
options.ImageContrast = 0.7f;

// Change the horizontal resolution.
// The default value for these properties is 96.0, for a resolution of 96dpi.
options.HorizontalResolution = 72f;

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
            
        
```

## Conclusion

In this tutorial, we explored the functionality of getting a JPEG page range with Aspose.Words for .NET. We learned how to convert a specific range of pages of a document into images in JPEG format, while customizing the save options.

This feature is useful when you want to extract specific pages from a document and save them as JPEG images. You can also adjust the brightness, contrast, and horizontal resolution of images to achieve personalized results.

Aspose.Words for .NET offers an extensive range of advanced features for document manipulation and generation. Getting a JPEG page range is one of the many powerful tools it puts at your disposal.

Feel free to integrate this feature into your Aspose.Words for .NET projects to get high quality JPEG images from your documents.
