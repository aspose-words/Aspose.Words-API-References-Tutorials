---
title: 在 Word 文档中插入内嵌图像
linktitle: 在 Word 文档中插入内嵌图像
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中插入内联图像。
type: docs
weight: 10
url: /zh/net/add-content-using-documentbuilder/insert-inline-image/
---
在这个综合教程中，您将学习如何使用 Aspose.Words for .NET 将内嵌图像插入到 Word 文档中。我们将指导您完成整个过程，并为您提供必要的 C# 代码片段。在本指南结束时，您将能够将图像直接添加到文档的文本中。

## 先决条件
在我们开始之前，请确保您满足以下先决条件：
- Aspose.Words for .NET 库安装在您的系统上。

## 第 1 步：创建新文档和 DocumentBuilder
首先，使用 Document 类创建一个新文档并初始化 DocumentBuilder 对象：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：插入内嵌图像
接下来，使用 DocumentBuilder 类的 InsertImage 方法将内联图像插入到文档中。提供图像文件路径作为参数：

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## 第 3 步：保存文档
插入内嵌图像后，使用 Document 类的 Save 方法将文档保存到文件中：

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

### 使用 Aspose.Words for .NET 插入内联图像的示例源代码
以下是使用 Aspose.Words for .NET 插入内联图像的完整源代码：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

## 结论
恭喜！您已成功学习如何使用 Aspose.Words for .NET 将内嵌图像插入到 Word 文档中。通过遵循分步指南并利用提供的源代码，您现在可以在文档文本中无缝添加图像。

内嵌图像适用于各种场景，例如将插图、徽标或其他视觉元素直接添加到文档流中。

### 在Word文档中插入内嵌图像的常见问题解答

#### 问：我可以调整 Word 文档中内嵌图像的大小吗？

答：是的，您可以使用 Aspose.Words for .NET 调整内嵌图像的大小。插入图像后，您可以通过调整表示图像的 Shape 对象的宽度和高度属性来控制其大小。

#### 问：是否可以向内嵌图像添加替代文本以实现辅助功能？

答：是的，您可以向内嵌图像添加替代文本以增强可访问性。 Aspose.Words for .NET 支持向图像添加替代文本，允许屏幕阅读器和其他辅助技术向视障用户描述图像内容。

#### 问：我可以对内嵌图像应用格式或样式吗？

答：当然！ Aspose.Words for .NET 为内嵌图像提供了广泛的格式化选项。您可以对图像应用各种样式、边框、效果和其他格式属性，以匹配文档的视觉设计。

#### 问：Aspose.Words for .NET 支持从流或字节数组插入图像吗？

答：是的，您可以使用 Aspose.Words for .NET 从流或字节数组插入内联图像。这允许您使用从外部源加载的图像或动态生成的图像。

#### 问：我可以在文本内容的特定位置插入图片吗？

答：是的，Aspose.Words for .NET 中的 DocumentBuilder 类提供了对内联图像插入位置的精确控制。您可以指定文本中应插入图像的确切位置。