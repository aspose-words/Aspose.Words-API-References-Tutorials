---
title: 横线格式
linktitle: 横线格式
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中设置水平线的格式。分步指南。
type: docs
weight: 10
url: /zh/net/add-content-using-documentbuilder/horizontal-rule-format/
---

在这个综合示例中，您将学习如何使用 Aspose.Words for .NET 在 Word 文档中设置水平线的格式。我们将指导您完成整个过程，并为您提供必要的 C# 代码片段。在本指南结束时，您将能够自定义水平标尺的对齐方式、宽度、高度、颜色和其他属性。

## 先决条件
在我们开始之前，请确保您具备以下先决条件：
- Aspose.Words for .NET 库安装在您的系统上。

## 第 1 步：创建一个 DocumentBuilder 并插入一条水平线
首先，创建一个 DocumentBuilder 对象并使用 InsertHorizontalRule 方法插入一条水平线：

```csharp
DocumentBuilder builder = new DocumentBuilder();
Shape shape = builder.InsertHorizontalRule();
```

## 第 2 步：访问水平标尺格式
接下来，访问 Shape 对象的 HorizontalRuleFormat 属性以检索格式化选项：

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
```

## 第 3 步：自定义格式选项
现在，您可以为水平线自定义各种格式选项。例如，您可以调整对齐方式、宽度、高度、颜色和阴影：

```csharp
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

## 第 4 步：保存文档
格式化水平线后，使用 Document 对象的 Save 方法将文档保存到文件：

```csharp
builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

### 使用 Aspose.Words for .NET 的水平标尺格式示例源代码
下面是使用 Aspose.Words for .NET 格式化水平线的完整源代码：

```csharp
DocumentBuilder builder = new DocumentBuilder();

Shape shape = builder.InsertHorizontalRule();

HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;

builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

请记住根据您的特定要求调整代码，并根据需要使用其他功能对其进行增强。

## 结论
恭喜！您已经成功学习了如何使用 Aspose.Words for .NET 在 Word 文档中设置水平线的格式。按照分步指南并利用提供的源代码，您现在可以自定义水平线的外观以增强文档的视觉布局。

尝试不同的格式设置选项以获得所需的水平规则样式和效果。
