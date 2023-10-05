---
title: 在 Aspose.Words for Java 中将文档保存为 PDF
linktitle: 将文档另存为 PDF
second_title: Aspose.Words Java 文档处理 API
description: 了解如何使用 Aspose.Words for Java 将 Word 文档另存为 PDF。自定义字体、属性和图像质量。 PDF 转换的综合指南。
type: docs
weight: 22
url: /zh/java/document-loading-and-saving/saving-documents-as-pdf/
---

## 在 Aspose.Words for Java 中将文档保存为 PDF 的简介

在本分步指南中，我们将探讨如何使用 Aspose.Words for Java 将文档另存为 PDF。我们将介绍 PDF 转换的各个方面，并提供代码示例以使该过程更容易。

## 先决条件

在我们开始之前，请确保您具备以下先决条件：

- 您的系统上安装了 Java 开发工具包 (JDK)。
-  Aspose.Words for Java 库。您可以从以下位置下载：[这里](https://releases.aspose.com/words/java/).

## 将文档转换为 PDF

要将Word文档转换为PDF，您可以使用以下代码片段：

```java
Document doc = new Document("input.docx");
PdfSaveOptions saveOptions = new PdfSaveOptions();
doc.save("output.pdf", saveOptions);
```

代替`"input.docx"`以及 Word 文档的路径和`"output.pdf"`与所需的输出 PDF 文件路径。

## 控制 PDF 保存选项

您可以使用以下命令控制各种 PDF 保存选项`PdfSaveOptions`班级。例如，您可以按如下方式设置 PDF 文档的显示标题：

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setDisplayDocTitle(true);
doc.save("output.pdf", saveOptions);
```

## 在 PDF 中嵌入字体

要在生成的 PDF 中嵌入字体，请使用以下代码：

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setEmbedFullFonts(true);
doc.save("output.pdf", saveOptions);
```

## 自定义文档属性

您可以在生成的 PDF 中自定义文档属性。例如：

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setCustomPropertiesExport(PdfCustomPropertiesExport.STANDARD);
doc.save("output.pdf", saveOptions);
```

## 导出文档结构

要导出文档结构，请设置`exportDocumentStructure`选项`true`:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setExportDocumentStructure(true);
doc.save("output.pdf", saveOptions);
```

## 图像压缩

您可以使用以下代码控制图像压缩：

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setImageCompression(PdfImageCompression.JPEG);
doc.save("output.pdf", saveOptions);
```

## 更新最后打印的属性

要更新 PDF 中的“上次打印”属性，请使用：

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setUpdateLastPrintedProperty(true);
doc.save("output.pdf", saveOptions);
```

## 渲染 DML 3D 效果

对于DML 3D效果的高级渲染，设置渲染模式：

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setDml3DEffectsRenderingMode(Dml3DEffectsRenderingMode.ADVANCED);
doc.save("output.pdf", saveOptions);
```

## 插值图像

您可以启用图像插值来提高图像质量：

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setInterpolateImages(true);
doc.save("output.pdf", saveOptions);
```

## 结论

Aspose.Words for Java 提供了将 Word 文档转换为 PDF 格式的全面功能，并具有灵活性和自定义选项。您可以控制 PDF 输出的各个方面，包括字体、文档属性、图像压缩等。

## 常见问题解答

### 如何使用 Aspose.Words for Java 将 Word 文档转换为 PDF？

要将 Word 文档转换为 PDF，请使用以下代码：

```java
Document doc = new Document("input.docx");
PdfSaveOptions saveOptions = new PdfSaveOptions();
doc.save("output.pdf", saveOptions);
```

代替`"input.docx"`以及 Word 文档的路径和`"output.pdf"`与所需的输出 PDF 文件路径。

### 我可以在 Aspose.Words for Java 生成的 PDF 中嵌入字体吗？

是的，您可以通过设置在 PDF 中嵌入字体`setEmbedFullFonts`选项`true`在`PdfSaveOptions`。这是一个例子：

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setEmbedFullFonts(true);
doc.save("output.pdf", saveOptions);
```

### 如何在生成的 PDF 中自定义文档属性？

您可以使用以下命令自定义 PDF 中的文档属性`setCustomPropertiesExport`选项中`PdfSaveOptions`。例如：

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setCustomPropertiesExport(PdfCustomPropertiesExport.STANDARD);
doc.save("output.pdf", saveOptions);
```

### Aspose.Words for Java 中图像压缩的目的是什么？

图像压缩允许您控制生成的 PDF 中图像的质量和大小。您可以使用设置图像压缩模式`setImageCompression`在`PdfSaveOptions`.

### 如何更新 PDF 中的“上次打印”属性？

您可以通过设置更新 PDF 中的“上次打印”属性`setUpdateLastPrintedProperty`到`true`在`PdfSaveOptions`。这将反映 PDF 元数据中的最后打印日期。

### 转换为 PDF 时如何提高图像质量？

要提高图像质量，请通过设置启用图像插值`setInterpolateImages`到`true`在`PdfSaveOptions`。这将使 PDF 中的图像更平滑、质量更高。