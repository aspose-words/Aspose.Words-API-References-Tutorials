---
title: 使用 Aspose.Words Java 高级 HTML 文档保存选项
linktitle: 使用以下方法保存 HTML 文档
second_title: Aspose.Words Java 文档处理 API
description: 在本教程中，我们介绍了使用 Aspose.Words for Java 的各种高级 HTML 文档保存选项。这些选项使您能够创建高质量的 HTML
type: docs
weight: 16
url: /zh/java/document-loading-and-saving/advance-html-documents-saving-options/
---

在本教程中，我们将探索 Aspose.Words for Java 提供的高级 HTML 文档保存选项。Aspose.Words 是一个用于处理 Word 文档的强大的 Java API，它提供了广泛的文档操作和转换功能。

## 1. 简介
Aspose.Words for Java 允许您以编程方式处理 Word 文档。在本教程中，我们将重点介绍高级 HTML 文档保存选项，这些选项使您能够控制如何将 Word 文档转换为 HTML。

## 2. 导出往返信息
这`exportRoundtripInformation`此方法允许您将 Word 文档导出为 HTML，同时保留往返信息。当您想将 HTML 转换回 Word 格式而不丢失任何特定于文档的详细信息时，此信息非常有用。

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. 将字体导出为 Base64
随着`exportFontsAsBase64`方法，您可以将文档中使用的字体导出为 HTML 中的 Base64 编码数据。这可确保 HTML 表示保留与原始 Word 文档相同的字体样式。

```java
@Test
public void exportFontsAsBase64() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportFontsAsBase64(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
}
```

## 4. 导出资源
这`exportResources`方法允许您指定 CSS 样式表的类型并导出字体资源。您还可以在 HTML 中设置资源文件夹和资源别名。

```java
@Test
public void exportResources() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setExportFontResources(true);
    saveOptions.setResourceFolder("Your Directory Path" + "Resources");
    saveOptions.setResourceFolderAlias("http://example.com/resources”);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
}
```

## 5. 将图元文件转换为 EMF 或 WMF
这`convertMetafilesToEmfOrWmf`该方法允许您将文档中的元文件转换为 EMF 或 WMF 格式，确保兼容性和 HTML 中的流畅呈现。

```java
@Test
public void convertMetafilesToEmfOrWmf() throws Exception {
    //为简洁起见，未显示代码片段。
}
```

## 6. 将图元文件转换为 SVG
使用`convertMetafilesToSvg`将元文件转换为 SVG 格式的方法。此格式非常适合在 HTML 文档中显示矢量图形。

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    //为简洁起见，未显示代码片段。
}
```

## 7. 添加 CSS 类名前缀
随着`addCssClassNamePrefix`方法，您可以在导出的 HTML 中为 CSS 类名添加前缀。这有助于防止与现有样式发生冲突。

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

## 8. 导出 MHTML 资源的 CID URL
这`exportCidUrlsForMhtmlResources`方法用于将文档保存为 MHTML 格式。它允许导出资源的 Content-ID URL。

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    //为简洁起见，未显示代码片段。
}
```

## 9. 解析字体名称
这`resolveFontNames`方法有助于在以 HTML 格式保存文档时解析字体名称，确保在不同平台上的一致渲染。

```java
@Test
public void resolveFontNames() throws Exception {
    //为简洁起见，未显示代码片段。
}
```

## 10. 将文本输入表单字段导出为文本
这`exportTextInputFormFieldAsText`方法将表单字段导出为 HTML 中的纯文本，使其易于阅读和编辑。

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    //为简洁起见，未显示代码片段。
}
```

## 11. 结论
在本教程中，我们探索了 Aspose.Words for Java 提供的高级 HTML 文档保存选项。这些选项使您可以对转换过程进行细粒度控制，从而可以创建与原始 Word 文档非常相似的 HTML 文档。

## 12. 常见问题解答
以下是有关使用 Aspose.Words for Java 和 HTML 文档保存选项的一些常见问题：

### 问题 1：如何使用 Aspose.Words for Java 将 HTML 转换回 Word 格式？
要将 HTML 转换回 Word 格式，您可以使用 Aspose.Words API 的`load`方法加载HTML文档，然后将其保存为Word格式。

### 问题 2：导出为 HTML 时我可以自定义 CSS 样式吗？
是的，您可以通过修改 HTML 中使用的样式表或使用`addCssClassNamePrefix`方法为 CSS 类名添加前缀。

### Q3：有没有办法优化 HTML 输出以便在网页上显示？
是的，您可以通过配置诸如将字体导出为 Base64 和将元文件转换为 SVG 等选项来优化 HTML 输出以在网页上显示。

### Q4：将复杂的 Word 文档转换为 HTML 时有什么限制吗？
虽然 Aspose.Words for Java 提供了强大的转换功能，但布局复杂的复杂 Word 文档可能需要额外的后期处理才能实现所需的 HTML 输出。
