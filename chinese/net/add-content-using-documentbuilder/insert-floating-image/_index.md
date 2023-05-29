---
title: 插入浮动图像
linktitle: 插入浮动图像
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中插入浮动图像。分步指南。
type: docs
weight: 10
url: /zh/net/add-content-using-documentbuilder/insert-floating-image/
---

在这个综合示例中，您将学习如何使用 Aspose.Words for .NET 将浮动图像插入到 Word 文档中。我们将指导您完成整个过程，并为您提供必要的 C# 代码片段。在本指南结束时，您将能够将具有可自定义定位和环绕选项的图像添加到您的文档中。

## 先决条件
在我们开始之前，请确保您具备以下先决条件：
- Aspose.Words for .NET 库安装在您的系统上。

## 第 1 步：创建新文档和 DocumentBuilder
首先，使用 Document 类创建一个新文档并初始化一个 DocumentBuilder 对象：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：插入浮动图像
接下来，使用 DocumentBuilder 类的 InsertImage 方法插入浮动图像。提供图像文件路径、相对水平和垂直位置、宽度、高度和环绕选项作为参数：

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);
```

## 第 3 步：保存文档
插入浮动图像后，使用 Document 类的 Save 方法将文档保存到文件：

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

## 使用 Aspose.Words for .NET 插入浮动图像的示例源代码
下面是使用 Aspose.Words for .NET 插入浮动图像的完整源代码：
浮动图像适用于各种场景，例如添加徽标、插图或可以独立于文档文本定位的装饰元素。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

请记住根据您的具体要求调整代码，包括图像文件路径和所需的定位和环绕选项。

## 结论
恭喜！您已经成功学习了如何使用 Aspose.Words for .NET 将浮动图像插入到 Word 文档中。按照分步指南并利用提供的源代码，您现在可以使用具有视觉吸引力和可自定义的浮动图像来增强您的文档。

