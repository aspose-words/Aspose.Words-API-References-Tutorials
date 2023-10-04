---
title: Saving Documents as PDF in Aspose.Words for Java
linktitle: Saving Documents as PDF in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 22
url: /java/document-loading-and-saving/saving-documents-as-pdf/
---

## Complete Source Code
```java
        Document doc = new Document(getMyDir() + "Rendering.docx");
        PdfSaveOptions saveOptions = new PdfSaveOptions(); { saveOptions.setDisplayDocTitle(true); }
        doc.save(getArtifactsDir() + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
    }
    @Test
    public void pdfRenderWarnings() throws Exception
    {
        Document doc = new Document(getMyDir() + "WMF with image.docx");
        MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions();
        {
            metafileRenderingOptions.setEmulateRasterOperations(false); metafileRenderingOptions.setRenderingMode(MetafileRenderingMode.VECTOR_WITH_FALLBACK);
        }
        PdfSaveOptions saveOptions = new PdfSaveOptions(); { saveOptions.setMetafileRenderingOptions(metafileRenderingOptions); }
        // If Aspose.Words cannot correctly render some of the metafile records
        // to vector graphics then Aspose.Words renders this metafile to a bitmap.
        HandleDocumentWarnings callback = new HandleDocumentWarnings();
        doc.setWarningCallback(callback);
        doc.save(getArtifactsDir() + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);
        // While the file saves successfully, rendering warnings that occurred during saving are collected here.
        for (WarningInfo warningInfo : callback.mWarnings)
        {
            System.out.println(warningInfo.getDescription());
        }
    }
    public static class HandleDocumentWarnings implements IWarningCallback
    {
        /// <summary>
        /// Our callback only needs to implement the "Warning" method. This method is called whenever there is a
        /// potential issue during document processing. The callback can be set to listen for warnings generated during
        /// document load and/or document save.
        /// </summary>
        public void warning(WarningInfo info)
        {
            // For now type of warnings about unsupported metafile records changed
            // from DataLoss/UnexpectedContent to MinorFormattingLoss.
            if (info.getWarningType() == WarningType.MINOR_FORMATTING_LOSS)
            {
                System.out.println("Unsupported operation: " + info.getDescription());
                mWarnings.warning(info);
            }
        }
        public WarningInfoCollection mWarnings = new WarningInfoCollection();
    }
    @Test
    public void digitallySignedPdfUsingCertificateHolder() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.writeln("Test Signed PDF.");
        PdfSaveOptions saveOptions = new PdfSaveOptions();
        {
            saveOptions.setDigitalSignatureDetails(new PdfDigitalSignatureDetails(
                CertificateHolder.create(getMyDir() + "morzal.pfx", "aw"), "reason", "location",
                new Date()));
        }
        doc.save(getArtifactsDir() + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
    }
    @Test
    public void embeddedAllFonts() throws Exception
    {
        Document doc = new Document(getMyDir() + "Rendering.docx");
        // The output PDF will be embedded with all fonts found in the document.
        PdfSaveOptions saveOptions = new PdfSaveOptions(); { saveOptions.setEmbedFullFonts(true); }
        doc.save(getArtifactsDir() + "WorkingWithPdfSaveOptions.EmbeddedFontsInPdf.pdf", saveOptions);
    }
    @Test
    public void embeddedSubsetFonts() throws Exception
    {
        Document doc = new Document(getMyDir() + "Rendering.docx");
        // The output PDF will contain subsets of the fonts in the document.
        // Only the glyphs used in the document are included in the PDF fonts.
        PdfSaveOptions saveOptions = new PdfSaveOptions(); { saveOptions.setEmbedFullFonts(false); }
        doc.save(getArtifactsDir() + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
    }
    @Test
    public void disableEmbedWindowsFonts() throws Exception
    {
        Document doc = new Document(getMyDir() + "Rendering.docx");
        // The output PDF will be saved without embedding standard windows fonts.
        PdfSaveOptions saveOptions = new PdfSaveOptions(); { saveOptions.setFontEmbeddingMode(PdfFontEmbeddingMode.EMBED_NONE); }
        doc.save(getArtifactsDir() + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
    }
    @Test
    public void skipEmbeddedArialAndTimesRomanFonts() throws Exception
    {
        Document doc = new Document(getMyDir() + "Rendering.docx");
        PdfSaveOptions saveOptions = new PdfSaveOptions(); { saveOptions.setFontEmbeddingMode(PdfFontEmbeddingMode.EMBED_ALL); }
        doc.save(getArtifactsDir() + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
    }
    @Test
    public void avoidEmbeddingCoreFonts() throws Exception
    {
        Document doc = new Document(getMyDir() + "Rendering.docx");
        // The output PDF will not be embedded with core fonts such as Arial, Times New Roman etc.
        PdfSaveOptions saveOptions = new PdfSaveOptions(); { saveOptions.setUseCoreFonts(true); }
        doc.save(getArtifactsDir() + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
    }
    @Test
    public void escapeUri() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.insertHyperlink("Testlink", 
            "https://www.google.com/search?q=%2Fthe%20test", false);
        builder.writeln();
        builder.insertHyperlink("https://www.google.com/search?q=%2Fthe%20test", 
            "https://www.google.com/search?q=%2Fthe%20test", false);
        doc.save(getArtifactsDir() + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
    }
    @Test
    public void exportHeaderFooterBookmarks() throws Exception
    {
        Document doc = new Document(getMyDir() + "Bookmarks in headers and footers.docx");
        PdfSaveOptions saveOptions = new PdfSaveOptions();
        saveOptions.getOutlineOptions().setDefaultBookmarksOutlineLevel(1);
        saveOptions.setHeaderFooterBookmarksExportMode(HeaderFooterBookmarksExportMode.FIRST);
        doc.save(getArtifactsDir() + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
    }
    @Test
    public void scaleWmfFontsToMetafileSize() throws Exception
    {
        Document doc = new Document(getMyDir() + "WMF with text.docx");
        MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions();
        {
            metafileRenderingOptions.setScaleWmfFontsToMetafileSize(false);
        }
        // If Aspose.Words cannot correctly render some of the metafile records to vector graphics
        // then Aspose.Words renders this metafile to a bitmap.
        PdfSaveOptions saveOptions = new PdfSaveOptions(); { saveOptions.setMetafileRenderingOptions(metafileRenderingOptions); }
        doc.save(getArtifactsDir() + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
    }
    @Test
    public void additionalTextPositioning() throws Exception
    {
        Document doc = new Document(getMyDir() + "Rendering.docx");
        PdfSaveOptions saveOptions = new PdfSaveOptions(); { saveOptions.setAdditionalTextPositioning(true); }
        doc.save(getArtifactsDir() + "WorkingWithPdfSaveOptions.AdditionalTextPositioning.pdf", saveOptions);
    }
    @Test
    public void conversionToPdf17() throws Exception
    {
        Document doc = new Document(getMyDir() + "Rendering.docx");
        PdfSaveOptions saveOptions = new PdfSaveOptions(); { saveOptions.setCompliance(PdfCompliance.PDF_17); }
        doc.save(getArtifactsDir() + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);
    }
    @Test
    public void downsamplingImages() throws Exception
    {
        Document doc = new Document(getMyDir() + "Rendering.docx");
        // We can set a minimum threshold for downsampling.
        // This value will prevent the second image in the input document from being downsampled.
        PdfSaveOptions saveOptions = new PdfSaveOptions();
        {
            saveOptions.getDownsampleOptions().setResolution(36);
            saveOptions.getDownsampleOptions().setResolutionThreshold(128);
        }
        doc.save(getArtifactsDir() + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
    }
    @Test
    public void setOutlineOptions() throws Exception
    {
        Document doc = new Document(getMyDir() + "Rendering.docx");
        PdfSaveOptions saveOptions = new PdfSaveOptions();
        saveOptions.getOutlineOptions().setHeadingsOutlineLevels(3);
        saveOptions.getOutlineOptions().setExpandedOutlineLevels(1);
        doc.save(getArtifactsDir() + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
    }
    @Test
    public void customPropertiesExport() throws Exception
    {
        Document doc = new Document();
        doc.getCustomDocumentProperties().add("Company", "Aspose");
        PdfSaveOptions saveOptions = new PdfSaveOptions(); { saveOptions.setCustomPropertiesExport(PdfCustomPropertiesExport.STANDARD); }
        doc.save(getArtifactsDir() + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);
    }
    @Test
    public void exportDocumentStructure() throws Exception
    {
        Document doc = new Document(getMyDir() + "Paragraphs.docx");
        // The file size will be increased and the structure will be visible in the "Content" navigation pane
        // of Adobe Acrobat Pro, while editing the .pdf.
        PdfSaveOptions saveOptions = new PdfSaveOptions(); { saveOptions.setExportDocumentStructure(true); }
        doc.save(getArtifactsDir() + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
    }
    @Test
    public void pdfImageComppression() throws Exception
    {
        Document doc = new Document(getMyDir() + "Rendering.docx");
        PdfSaveOptions saveOptions = new PdfSaveOptions();
        {
            saveOptions.setImageCompression(PdfImageCompression.JPEG); saveOptions.setPreserveFormFields(true);
        }
        doc.save(getArtifactsDir() + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
        PdfSaveOptions saveOptionsA1B = new PdfSaveOptions();
        {
            saveOptionsA1B.setCompliance(PdfCompliance.PDF_A_1_B);
            saveOptionsA1B.setImageCompression(PdfImageCompression.JPEG);
            saveOptionsA1B.setJpegQuality(100); // Use JPEG compression at 50% quality to reduce file size.
            saveOptionsA1B.setImageColorSpaceExportMode(PdfImageColorSpaceExportMode.SIMPLE_CMYK);
        }
        doc.save(getArtifactsDir() + "WorkingWithPdfSaveOptions.PdfImageCompression.Pdf_A1b.pdf", saveOptionsA1B);
    }
    @Test
    public void updateLastPrintedProperty() throws Exception
    {
        Document doc = new Document(getMyDir() + "Rendering.docx");
        PdfSaveOptions saveOptions = new PdfSaveOptions(); { saveOptions.setUpdateLastPrintedProperty(true); }
        doc.save(getArtifactsDir() + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);
    }
    @Test
    public void dml3DEffectsRendering() throws Exception
    {
        Document doc = new Document(getMyDir() + "Rendering.docx");
        PdfSaveOptions saveOptions = new PdfSaveOptions(); { saveOptions.setDml3DEffectsRenderingMode(Dml3DEffectsRenderingMode.ADVANCED); }
        doc.save(getArtifactsDir() + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
    }
    @Test
    public void interpolateImages() throws Exception
    {
        Document doc = new Document(getMyDir() + "Rendering.docx");
        PdfSaveOptions saveOptions = new PdfSaveOptions(); { saveOptions.setInterpolateImages(true); }
        doc.save(getArtifactsDir() + "WorkingWithPdfSaveOptions.InterpolateImages.pdf", saveOptions);
```