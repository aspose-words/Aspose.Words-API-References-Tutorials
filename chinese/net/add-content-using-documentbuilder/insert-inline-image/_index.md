---
title: 插入内嵌图像
linktitle: 插入内嵌图像
second_title: Aspose.Words for .NET API 参考
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
