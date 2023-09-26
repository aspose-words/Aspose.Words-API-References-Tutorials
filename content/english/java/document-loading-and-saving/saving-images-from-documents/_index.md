---
title: Saving Images from Documents in Aspose.Words for Java
linktitle: Saving Images from Documents in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 17
url: /java/document-loading-and-saving/saving-images-from-documents/
---

## Complete Source Code
```java
        Document doc = new Document(getMyDir() + "Rendering.docx");
        ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.TIFF);
        {
            saveOptions.setTiffCompression(TiffCompression.CCITT_3);
            saveOptions.setImageColorMode(ImageColorMode.GRAYSCALE);
            saveOptions.setTiffBinarizationMethod(ImageBinarizationMethod.FLOYD_STEINBERG_DITHERING);
            saveOptions.setThresholdForFloydSteinbergDithering((byte) 254);
        }
        doc.save(getArtifactsDir() + "WorkingWithImageSaveOptions.ExposeThresholdControlForTiffBinarization.tiff", saveOptions);
    }
    @Test
    public void getTiffPageRange() throws Exception
    {
        Document doc = new Document(getMyDir() + "Rendering.docx");
        doc.save(getArtifactsDir() + "WorkingWithImageSaveOptions.MultipageTiff.tiff");
        ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.TIFF);
        {
            saveOptions.setPageSet(new PageSet(new PageRange(0, 1))); saveOptions.setTiffCompression(TiffCompression.CCITT_4); saveOptions.setResolution(160f);
        }
        doc.save(getArtifactsDir() + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
    }
    @Test
    public void format1BppIndexed() throws Exception
    {
        Document doc = new Document(getMyDir() + "Rendering.docx");
        ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.PNG);
        {
            saveOptions.setPageSet(new PageSet(1));
            saveOptions.setImageColorMode(ImageColorMode.BLACK_AND_WHITE);
            saveOptions.setPixelFormat(ImagePixelFormat.FORMAT_1_BPP_INDEXED);
        }
        doc.save(getArtifactsDir() + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
    }
    @Test
    public void getJpegPageRange() throws Exception
    {
        Document doc = new Document(getMyDir() + "Rendering.docx");
        ImageSaveOptions options = new ImageSaveOptions(SaveFormat.JPEG);
        // Set the "PageSet" to "0" to convert only the first page of a document.
        options.setPageSet(new PageSet(0));
        // Change the image's brightness and contrast.
        // Both are on a 0-1 scale and are at 0.5 by default.
        options.setImageBrightness(0.3f);
        options.setImageContrast(0.7f);
        // Change the horizontal resolution.
        // The default value for these properties is 96.0, for a resolution of 96dpi.
        options.setHorizontalResolution(72f);
        doc.save(getArtifactsDir() + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
    }
    @Test
    public static void pageSavingCallback() throws Exception
    {
        Document doc = new Document(getMyDir() + "Rendering.docx");
        ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.PNG);
        {
            imageSaveOptions.setPageSet(new PageSet(new PageRange(0, doc.getPageCount() - 1)));
            imageSaveOptions.setPageSavingCallback(new HandlePageSavingCallback());
        }
        doc.save(getArtifactsDir() + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
    }
    private static class HandlePageSavingCallback implements IPageSavingCallback
    {
        public void pageSaving(PageSavingArgs args)
        {
            args.setPageFileName(MessageFormat.format(getArtifactsDir() + "Page_{0}.png", args.getPageIndex()));
        }
```
