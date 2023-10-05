---
title: 在 Aspose.Words for Java 中使用文档水印
linktitle: 使用文档水印
second_title: Aspose.Words Java 文档处理 API
description: 了解如何在 Aspose.Words for Java 中向文档添加水印。为具有专业外观的文档自定义文本和图像水印。
type: docs
weight: 15
url: /zh/java/document-conversion-and-export/using-watermarks-to-documents/
---

## 在 Aspose.Words for Java 中向文档添加水印简介

在本教程中，我们将探讨如何使用 Aspose.Words for Java API 向文档添加水印。水印是用文本或图形标记文档的有用方法，以指示其状态、机密性或其他相关信息。我们将在本指南中介绍文本和图像水印。

## 设置 Aspose.Words for Java

在开始向文档添加水印之前，我们需要设置 Aspose.Words for Java。请按照以下步骤开始：

1. 下载 Aspose.Words for Java 从[这里](https://releases.aspose.com/words/java/).
2. 将 Aspose.Words for Java 库添加到您的 Java 项目中。
3. 在 Java 代码中导入必要的类。

现在我们已经设置了库，让我们继续添加水印。

## 添加文本水印

当您想要向文档添加文本信息时，文本水印是常见的选择。以下是使用 Aspose.Words for Java 添加文本水印的方法：

```java
//创建文档实例
Document doc = new Document("Document.docx");

//定义文本水印选项
TextWatermarkOptions options = new TextWatermarkOptions();
options.setFontFamily("Arial");
options.setFontSize(36f);
options.setColor(Color.BLACK);
options.setLayout(WatermarkLayout.HORIZONTAL);
options.setSemitransparent(false);

//设置水印文本和选项
doc.getWatermark().setText("Test", options);

//保存带水印的文档
doc.save("DocumentWithWatermark.docx");
```

## 添加图像水印

除了文本水印之外，您还可以将图像水印添加到文档中。添加图片水印的方法如下：

```java
//创建文档实例
Document doc = new Document("Document.docx");

//加载水印图像
byte[] imageBytes = Files.readAllBytes(Paths.get("watermark.png"));
Shape watermark = new Shape(doc, ShapeType.IMAGE);
watermark.getImageData().setImage(imageBytes);

//设置水印大小和位置
watermark.setWidth(200.0);
watermark.setHeight(100.0);
watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.CENTER);
watermark.setRelativeVerticalPosition(RelativeVerticalPosition.CENTER);

//将水印添加到文档中
doc.getFirstSection().getBody().getFirstParagraph().appendChild(watermark);

//保存带水印的文档
doc.save("DocumentWithImageWatermark.docx");
```

## 自定义水印

您可以通过调整水印的外观和位置来自定义水印。对于文本水印，您可以更改字体、大小、颜色和布局。对于图像水印，您可以修改其大小和位置，如前面的示例所示。

## 去除水印

要从文档中删除水印，可以使用以下代码：

```java
//创建文档实例
Document doc = new Document("DocumentWithWatermark.docx");

//去除水印
for (Shape shape : doc.getShapes())
{
    if (shape.getName().contains("Watermark"))
    {
        shape.remove();
    }
}

//保存无水印的文档
doc.save("DocumentWithoutWatermark.docx");
```


## 结论

在本教程中，我们学习了如何使用 Aspose.Words for Java 向文档添加水印。无论您需要添加文本还是图像水印，Aspose.Words 都提供了有效自定义和管理它们的工具。您还可以在不再需要水印时将其删除，确保您的文档干净且专业。

## 常见问题解答

### 如何更改文本水印的字体？

要更改文本水印的字体，请修改`setFontFamily`财产在`TextWatermarkOptions`。例如：

```java
options.setFontFamily("Times New Roman");
```

### 我可以在单个文档中添加多个水印吗？

是的，您可以通过创建多个水印来向文档添加多个水印`Shape`具有不同设置的对象并将它们添加到文档中。

### 可以旋转水印吗？

是的，您可以通过设置旋转水印`setRotation`财产在`Shape`目的。正值顺时针旋转水印，负值逆时针旋转水印。

### 如何使水印半透明？

要使水印半透明，请设置`setSemitransparent`财产给`true`在里面`TextWatermarkOptions`.

### 我可以将水印添加到文档的特定部分吗？

是的，您可以通过迭代各个部分并将水印添加到所需部分来将水印添加到文档的特定部分。