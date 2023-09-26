---
title: Saving HTML Documents with Aspose.Words for Java
linktitle: Saving HTML Documents with Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: 
type: docs
weight: 16
url: /java/document-loading-and-saving/saving-html-documents/
---

## Complete Source Code
```java
        Document doc = new Document(getMyDir() + "Rendering.docx");
        HtmlSaveOptions saveOptions = new HtmlSaveOptions(); { saveOptions.setExportRoundtripInformation(true); }
        doc.save(getArtifactsDir() + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
    }
    @Test
    public void exportFontsAsBase64() throws Exception
    {
        Document doc = new Document(getMyDir() + "Rendering.docx");
        HtmlSaveOptions saveOptions = new HtmlSaveOptions(); { saveOptions.setExportFontsAsBase64(true); }
        doc.save(getArtifactsDir() + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
    }
    @Test
    public void exportResources() throws Exception
    {
        Document doc = new Document(getMyDir() + "Rendering.docx");
        HtmlSaveOptions saveOptions = new HtmlSaveOptions();
        {
            saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
            saveOptions.setExportFontResources(true);
            saveOptions.setResourceFolder(getArtifactsDir() + "Resources");
            saveOptions.setResourceFolderAlias("http://example.com/resources");
        }
        doc.save(getArtifactsDir() + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
    }
    @Test
    public void convertMetafilesToEmfOrWmf() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.write("Here is an image as is: ");
        builder.insertHtml(
            "<img src=\"data:image/png;base64,\r\n                    iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP\r\n                    C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA\r\n                    AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J\r\n                    REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq\r\n                    ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0\r\n                    vr4MkhoXe0rZigAAAABJRU5ErkJggg==\" alt=\"Red dot\" />");
        HtmlSaveOptions saveOptions = new HtmlSaveOptions(); { saveOptions.setMetafileFormat(HtmlMetafileFormat.EMF_OR_WMF); }
        doc.save(getArtifactsDir() + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);
    }
    @Test
    public void convertMetafilesToSvg() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.write("Here is an SVG image: ");
        builder.insertHtml(
            "<svg height='210' width='500'>\r\n                <polygon points='100,10 40,198 190,78 10,78 160,198' \r\n                    style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />\r\n            </svg> ");
        HtmlSaveOptions saveOptions = new HtmlSaveOptions(); { saveOptions.setMetafileFormat(HtmlMetafileFormat.SVG); }
        doc.save(getArtifactsDir() + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
    }
    @Test
    public void addCssClassNamePrefix() throws Exception
    {
        Document doc = new Document(getMyDir() + "Rendering.docx");
        HtmlSaveOptions saveOptions = new HtmlSaveOptions();
        {
            saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL); saveOptions.setCssClassNamePrefix("pfx_");
        }
        doc.save(getArtifactsDir() + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
    }
    @Test
    public void exportCidUrlsForMhtmlResources() throws Exception
    {
        Document doc = new Document(getMyDir() + "Content-ID.docx");
        HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.MHTML);
        {
            saveOptions.setPrettyFormat(true); saveOptions.setExportCidUrlsForMhtmlResources(true);
        }
        doc.save(getArtifactsDir() + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);
    }
    @Test
    public void resolveFontNames() throws Exception
    {
        Document doc = new Document(getMyDir() + "Missing font.docx");
        HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.HTML);
        {
            saveOptions.setPrettyFormat(true); saveOptions.setResolveFontNames(true);
        }
        doc.save(getArtifactsDir() + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);
    }
    @Test
    public void exportTextInputFormFieldAsText() throws Exception
    {
        Document doc = new Document(getMyDir() + "Rendering.docx");
        File imagesDir = new File(Paths.get(getArtifactsDir(), "Images").toString());
        // The folder specified needs to exist and should be empty.
        if (imagesDir.exists())
            imagesDir.delete();
        imagesDir.mkdir();
        // Set an option to export form fields as plain text, not as HTML input elements.
        HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.HTML);
        {
            saveOptions.setExportTextInputFormFieldAsText(true); saveOptions.setImagesFolder(imagesDir.getPath());
        }
        doc.save(getArtifactsDir() + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);
```
