---
title: Get Tiff Page Range
linktitle: Get Tiff Page Range
second_title: Aspose.Words for .NET API Reference
description: Learn how to extract a range of TIFF pages with Aspose.Words for .NET. Complete tutorial for custom TIFF files.
type: docs
weight: 10
url: /net/programming-with-imagesaveoptions/get-tiff-page-range/
---

In this tutorial, we will explore the provided C# source code to get a range of TIFF pages with Aspose.Words for .NET. This feature allows you to extract a specific range of pages from a document and save them as a TIFF file.

## Step 1: Setting up the environment

Before you begin, make sure you've set up your development environment with Aspose.Words for .NET. Make sure you've added the necessary references and imported the appropriate namespaces.

## Step 2: Loading the document

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

In this step, we load the document using the `Document` method and passing the path to the DOCX file to load.

## Step 3: Saving the complete document in TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");
```

In this step, we save the complete document in TIFF format using the `Save` method and specifying the path to the output file with the extension `.tiff`.

## Step 4: Configure backup options for the page range

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
PageSet = new PageSet(new PageRange(0, 1)),
TiffCompression = TiffCompression.Ccitt4,
Resolution = 160
};
```

In this step, we configure backup options for the specific page range. We create a new `ImageSaveOptions` object specifying the desired save format, here "Tiff" for the TIFF format. We use `PageSet` to specify the range of pages we want to extract, here from page 0 to page 1 (inclusive). We also set the TIFF compression to `Ccitt4` and the resolution to 160 dpi.

## Step 5: Saving the page range to TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
```

In this last step, we save the specified page range in TIFF format using the `Save` method and passing the path to the output file with `.tiff` extension, along with the specified save options .

Now you can run the source code to get a specific range of pages from your document and save them as a TIFF file. The resulting files will be saved in the specified directory with the names "WorkingWithImageSaveOptions.MultipageTiff.tiff" for the full document and "WorkingWithImageSaveOptions.GetTiffPageRange.tiff" for the specified page range.

### Sample source code of Get Tiff Page Range using Aspose.Words for .NET

```csharp 

// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");



ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
	PageSet = new PageSet(new PageRange(0, 1)), TiffCompression = TiffCompression.Ccitt4, Resolution = 160
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
            
            
        
```

## Conclusion

In this tutorial, we explored the functionality of getting a range of TIFF pages with Aspose.Words for .NET. We learned how to extract a specific range of pages from a document and save them as a TIFF file.

This feature is useful when you want to extract only certain pages from a document and save them in a standard image format such as TIFF. You can also customize the compression and resolution options to get the best quality TIFF files.

Aspose.Words for .NET offers an extensive range of advanced features for document manipulation and generation. Getting a TIFF page range is one of the many powerful tools it puts at your disposal.

Feel free to integrate this functionality into your Aspose.Words for .NET projects to extract and save specific ranges of pages from your documents in TIFF format.
