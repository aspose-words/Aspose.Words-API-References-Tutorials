---
title: Saving Images As Wmf
linktitle: Saving Images As Wmf
second_title: Aspose.Words for .NET API Reference
description: Learn how to save images as WMF when converting to RTF with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-rtfsaveoptions/saving-images-as-wmf/
---

In this tutorial, we will explore the C# source code provided for the "Saving images as WMF with RTF save options" feature with Aspose.Words for .NET. This feature allows you to save document images in Windows Metafile (WMF) format when converting to RTF format.

## Step 1: Setting up the environment

Before you begin, make sure you've set up your development environment with Aspose.Words for .NET. Make sure you've added the necessary references and imported the appropriate namespaces.

## Step 2: Loading the document

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

In this step, we load the document using the `Document` method and passing the path to the DOCX file to load.

## Step 3: Configuring backup options

```csharp
RtfSaveOptions saveOptions = new RtfSaveOptions { SaveImagesAsWmf = true };
```

In this step, we configure the RTF backup options. We create a new `RtfSaveOptions` object and set the `SaveImagesAsWmf` property to `true`. This tells Aspose.Words to save the document images as WMF when converting to RTF.

## Step 4: Saving the document

```csharp
doc.Save(dataDir + "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf", saveOptions);
```

In this last step, we save the resulting document in RTF format using the `Save` method and passing the path to the output file, along with the specified save options.

Now you can run source code to save document images in WMF format while converting to RTF format. The resulting document will be saved in the specified directory with the name "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf".

### Sample source code for functionality of saving WMF images with RTF save options with Aspose.Words for .NET".

```csharp

            
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");

RtfSaveOptions saveOptions = new RtfSaveOptions { SaveImagesAsWmf = true };

doc.Save(dataDir + "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf", saveOptions);
            
        
```
## Conclusion

In this tutorial, we explored the functionality of saving images as WMF with RTF save options in Aspose.Words for .NET. We learned how to save images from a document in WMF format when converting to RTF format.

This feature is useful when you want to maintain the quality and resolution of images in your RTF documents. By saving images in WMF format, you can ensure that their appearance and sharpness remain intact.

Aspose.Words for .NET offers many advanced features for document manipulation and generation. Saving images in WMF format while converting to RTF format is one of the many powerful tools it gives you.
