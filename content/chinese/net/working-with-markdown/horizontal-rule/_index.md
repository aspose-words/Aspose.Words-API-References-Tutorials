---
title: 水平线
linktitle: 水平线
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 分步指南插入水平线。
type: docs
weight: 10
url: /zh/net/working-with-markdown/horizontal-rule/
---

在此示例中，我们将向您展示如何将水平标尺功能与 Aspose.Words for .NET 一起使用。水平线用于在视觉上分隔文档的各个部分。

## 第 1 步：使用文档生成器

首先，我们将使用文档生成器将内容添加到文档中。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 步骤 2：插入水平线

我们可以使用插入水平线`InsertHorizontalRule`文档生成器的方法。

```csharp
builder. InsertHorizontalRule();
```

## 使用 Aspose.Words for .NET 进行水平标尺的示例源代码

```csharp
//使用文档生成器将内容添加到文档中。
DocumentBuilder builder = new DocumentBuilder();

//插入水平线。
builder.InsertHorizontalRule();
```

恭喜！您现在已经了解了如何将水平标尺功能与 Aspose.Words for .NET 一起使用。


### 常见问题解答

#### 问：如何在 Markdown 中创建水平标尺？

答：要在 Markdown 中创建水平标尺，您可以在空行上使用以下符号之一：三个星号（\***）、三个破折号（\---)，或三个下划线(\___）。

#### 问：我可以在 Markdown 中自定义水平标尺的外观吗？

答：在标准 Markdown 中，无法自定义水平标尺的外观。但是，一些高级 Markdown 编辑器和扩展提供了额外的自定义功能。

#### 问：所有 Markdown 编辑器都支持水平标尺吗？

答：是的，大多数流行的 Markdown 编辑器都支持水平标尺。但是，最好检查特定供应商的文档以确保其受支持。

#### 问：我还可以在 Markdown 中创建哪些其他元素？

答：除了水平标尺之外，您还可以在 Markdown 中创建标题、段落、列表、链接、图像、表格等。