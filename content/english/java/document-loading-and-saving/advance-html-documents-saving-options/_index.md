---
title: Advance HTML Documents Saving Options with Aspose.Words Java
linktitle: Saving HTML Documents with Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: In this tutorial, we have covered various advanced HTML document saving options with Aspose.Words for Java. These options empower you to create high-quality HTML
type: docs
weight: 16
url: /java/document-loading-and-saving/advance-html-documents-saving-options/
---

In this tutorial, we will explore the advanced HTML document saving options provided by Aspose.Words for Java. Aspose.Words is a powerful Java API for working with Word documents, and it offers a wide range of features for document manipulation and conversion.

## 1. Introduction
Aspose.Words for Java allows you to work with Word documents programmatically. In this tutorial, we will focus on advanced HTML document saving options, which enable you to control how Word documents are converted to HTML.

## 2. Export Roundtrip Information
The `exportRoundtripInformation` method allows you to export Word documents to HTML while preserving roundtrip information. This information can be useful when you want to convert HTML back to Word format without losing any document-specific details.

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. Export Fonts as Base64
With the `exportFontsAsBase64` method, you can export fonts used in the document as Base64-encoded data in the HTML. This ensures that the HTML representation retains the same font styles as the original Word document.

```java
@Test
public void exportFontsAsBase64() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportFontsAsBase64(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
}
```

## 4. Export Resources
The `exportResources` method allows you to specify the type of CSS stylesheet and export font resources. You can also set a resource folder and an alias for resources in the HTML.

```java
@Test
public void exportResources() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setExportFontResources(true);
    saveOptions.setResourceFolder("Your Directory Path" + "Resources");
    saveOptions.setResourceFolderAlias("http://example.com/resources");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
}
```

## 5. Convert Metafiles to EMF or WMF
The `convertMetafilesToEmfOrWmf` method allows you to convert metafiles in the document to either EMF or WMF format, ensuring compatibility and smooth rendering in HTML.

```java
@Test
public void convertMetafilesToEmfOrWmf() throws Exception {
    // Code snippet not shown for brevity.
}
```

## 6. Convert Metafiles to SVG
Use the `convertMetafilesToSvg` method to convert metafiles to SVG format. This format is ideal for displaying vector graphics in HTML documents.

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    // Code snippet not shown for brevity.
}
```

## 7. Add CSS Class Name Prefix
With the `addCssClassNamePrefix` method, you can add a prefix to CSS class names in the exported HTML. This helps prevent conflicts with existing styles.

```java
@Test
public void addCssClassNamePrefix() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setCssClassNamePrefix("pfx_");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
}
```

## 8. Export CID URLs for MHTML Resources
The `exportCidUrlsForMhtmlResources` method is used when saving documents in MHTML format. It allows exporting Content-ID URLs for resources.

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    // Code snippet not shown for brevity.
}
```

## 9. Resolve Font Names
The `resolveFontNames` method helps resolve font names when saving documents in HTML format, ensuring consistent rendering across different platforms.

```java
@Test
public void resolveFontNames() throws Exception {
    // Code snippet not shown for brevity.
}
```

## 10. Export Text Input Form Field as Text
The `exportTextInputFormFieldAsText` method exports form fields as plain text in the HTML, making them easily readable and editable.

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    // Code snippet not shown for brevity.
}
```

## 11. Conclusion
In this tutorial, we explored the advanced HTML document saving options provided by Aspose.Words for Java. These options give you fine-grained control over the conversion process, allowing you to create HTML documents that closely resemble the original Word documents.

## 12. FAQs
Here are some frequently asked questions about working with Aspose.Words for Java and HTML document saving options:

### Q1: How can I convert HTML back to Word format using Aspose.Words for Java?
To convert HTML back to Word format, you can use the Aspose.Words API's `load` method to load the HTML document and then save it in Word format.

### Q2: Can I customize the CSS styles when exporting to HTML?
Yes, you can customize CSS styles by modifying the stylesheets used in the HTML or by using the `addCssClassNamePrefix` method to add a prefix to CSS class names.

### Q3: Is there a way to optimize the HTML output for web display?
Yes, you can optimize the HTML output for web display by configuring options like exporting fonts as Base64 and converting metafiles to SVG.

### Q4: Are there any limitations when converting complex Word documents to HTML?
While Aspose.Words for Java provides powerful conversion capabilities, complex Word documents with intricate layouts may require additional post-processing to achieve the desired HTML output.

