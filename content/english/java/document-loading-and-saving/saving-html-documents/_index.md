---
title: Saving HTML Documents with Aspose.Words for Java
linktitle: Saving HTML Documents with Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: Optimize your HTML document saving with Aspose.Words for Java. Learn how to export documents effectively. Explore roundtrip info, font handling, and more.
type: docs
weight: 16
url: /java/document-loading-and-saving/saving-html-documents/
---

## Introduction to Saving HTML Documents with Aspose.Words for Java

In this comprehensive guide, we will explore how to save HTML documents using Aspose.Words for Java. We will cover various scenarios and provide step-by-step instructions along with Java source code examples to help you master this process.

## Prerequisites

Before we begin, ensure you have the following prerequisites in place:

- Aspose.Words for Java library installed.
- Java development environment set up.

## 1. Saving HTML Documents

### Exporting Roundtrip Information

To export roundtrip information when saving an HTML document, you can use the following code:

```java
Document doc = new Document(getMyDir() + "Rendering.docx");
HtmlSaveOptions saveOptions = new HtmlSaveOptions();
saveOptions.setExportRoundtripInformation(true);
doc.save(getArtifactsDir() + "ExportRoundtripInformation.html", saveOptions);
```

This code ensures that the exported HTML document contains roundtrip information for further processing.

### Exporting Fonts as Base64

When saving HTML documents, you can choose to export fonts as Base64 data. Here's how:

```java
Document doc = new Document(getMyDir() + "Rendering.docx");
HtmlSaveOptions saveOptions = new HtmlSaveOptions();
saveOptions.setExportFontsAsBase64(true);
doc.save(getArtifactsDir() + "ExportFontsAsBase64.html", saveOptions);
```

This option can be useful when you want to embed fonts directly into the HTML for consistent rendering.

### Exporting Resources

To export resources like CSS stylesheets and images, you can use the following code:

```java
Document doc = new Document(getMyDir() + "Rendering.docx");
HtmlSaveOptions saveOptions = new HtmlSaveOptions();
saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
saveOptions.setExportFontResources(true);
saveOptions.setResourceFolder(getArtifactsDir() + "Resources");
saveOptions.setResourceFolderAlias("http://example.com/resources");
doc.save(getArtifactsDir() + "ExportResources.html", saveOptions);
```

This code ensures that resources are properly included in the exported HTML document.

### Converting Metafiles to EMF or WMF

You can convert metafiles to EMF or WMF format when exporting HTML documents. Here's how:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.write("Here is an image as is: ");
builder.insertHtml("<img src=\"data:image/png;base64, ...\" />");

HtmlSaveOptions saveOptions = new HtmlSaveOptions();
saveOptions.setMetafileFormat(HtmlMetafileFormat.EMF_OR_WMF);
doc.save(getArtifactsDir() + "ConvertMetafilesToEmfOrWmf.html", saveOptions);
```

This code converts metafiles within the document to EMF or WMF format for better compatibility.

### Converting Metafiles to SVG

To convert metafiles to SVG format when exporting HTML documents, use the following code:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.write("Here is an SVG image: ");
builder.insertHtml("<svg height='210' width='500'> ... </svg>");

HtmlSaveOptions saveOptions = new HtmlSaveOptions();
saveOptions.setMetafileFormat(HtmlMetafileFormat.SVG);
doc.save(getArtifactsDir() + "ConvertMetafilesToSvg.html", saveOptions);
```

This code ensures that metafiles are converted to SVG format for scalability.

### Adding CSS Class Name Prefix

To add a CSS class name prefix when exporting HTML documents, use the following code:

```java
Document doc = new Document(getMyDir() + "Rendering.docx");
HtmlSaveOptions saveOptions = new HtmlSaveOptions();
saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
saveOptions.setCssClassNamePrefix("pfx_");
doc.save(getArtifactsDir() + "AddCssClassNamePrefix.html", saveOptions);
```

This code adds a prefix to CSS class names for better styling control.

### Exporting CID URLs for MHTML Resources

When exporting HTML documents in MHTML format, you can export CID URLs for resources. Here's how:

```java
Document doc = new Document(getMyDir() + "Content-ID.docx");
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.MHTML);
saveOptions.setExportCidUrlsForMhtmlResources(true);
doc.save(getArtifactsDir() + "ExportCidUrlsForMhtmlResources.mhtml", saveOptions);
```

This code ensures that CID URLs are included in the MHTML document for resource referencing.

### Resolving Font Names

To resolve font names when exporting HTML documents, use the following code:

```java
Document doc = new Document(getMyDir() + "Missing font.docx");
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.HTML);
saveOptions.setResolveFontNames(true);
doc.save(getArtifactsDir() + "ResolveFontNames.html", saveOptions);
```

This code ensures that font names are properly resolved in the exported HTML.

### Exporting Text Input Form Fields as Text

To export text input form fields as plain text, use the following code:

```java
Document doc = new Document(getMyDir() + "Rendering.docx");
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.HTML);
saveOptions.setExportTextInputFormFieldAsText(true);
saveOptions.setImagesFolder(imagesDir.getPath());
doc.save(getArtifactsDir() + "ExportTextInputFormFieldAsText.html", saveOptions);
```

This code exports text input form fields as plain text instead of HTML input elements.

## Complete Source Code For Saving HTML Documents with Aspose.Words for Java

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

## Conclusion

In this guide, we've explored various aspects of saving HTML documents using Aspose.Words for Java. You've learned how to export roundtrip information, fonts, resources, metafiles, and more. These capabilities empower you to create web-friendly documents effortlessly.

## FAQ's

### How do I include images in the exported HTML document?

To include images in the exported HTML document, ensure that you set the appropriate image paths or URLs in your document and use the correct save options to export them.

### Can I customize the CSS styles in the exported HTML?

Yes, you can customize the CSS styles by editing the CSS stylesheet or by applying inline styles to specific elements in your Word document before exporting to HTML.

### How can I handle missing fonts when exporting HTML?

You can use the "ResolveFontNames" option to ensure that missing fonts are handled gracefully during the HTML export process.

### Is it possible to export form fields as plain text in HTML?

Yes, you can export form fields as plain text in HTML by setting the "ExportTextInputFormFieldAsText" option to true in the save options.

### Where can I find more information and documentation for Aspose.Words for Java?

For detailed documentation and API references, visit [Aspose.Words for Java Documentation](https://reference.aspose.com/words/java/).
