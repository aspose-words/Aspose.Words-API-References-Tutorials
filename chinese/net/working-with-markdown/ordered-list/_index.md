---
title: 有序列表
linktitle: 有序列表
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 分步指南创建有序列表。
type: docs
weight: 10
url: /zh/net/working-with-markdown/ordered-list/
---

在此示例中，我们将解释如何通过 Aspose.Words for .NET 使用有序列表功能。有序列表允许您用数字按顺序组织项目。

## 第 1 步：使用文档生成器

首先，我们将使用文档生成器来创建一个新文档。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步骤 2：应用有序列表格式

我们将使用文档生成器应用有序列表格式`ApplyBulletDefault`方法。我们还可以通过转到列表级别并设置我们想要的格式来自定义编号格式。

```csharp
builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";
```

## 第 3 步：将项目添加到列表中

我们可以使用文档生成器将项目添加到列表中`Writeln`方法。

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## 步骤 4：缩进列表

我们可以使用文档生成器来缩进列表`ListIndent`方法。

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

## 第 5 步：保存文档

最后，我们可以将文档保存为所需的格式。

### 使用 Aspose.Words for .NET 排序列表的示例源代码

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

恭喜！您现在已经了解了如何将有序列表功能与 Aspose.Words for .NET 结合使用。


### 常见问题解答

#### 问：如何在 Markdown 中创建有序列表？

答：要在 Markdown 中创建有序列表，请以数字开头，后跟句点 (`1.`, `2.`, `3.`)，后跟一个空格。

#### 问：我们可以在 Markdown 中嵌套有序列表吗？

答：是的，通过在每个嵌套列表项前面添加四个偏移空格，可以在 Markdown 中嵌套有序列表。

#### 问：如何自定义有序列表的编号？

答：在标准 Markdown 中，有序列表编号是自动生成的。但是，某些 Markdown 编辑器允许您使用特定扩展来自定义它。

#### 问：Markdown 中的有序列表支持缩进吗？

答：是的，Markdown 中的有序列表支持缩进。您可以使用空格或制表符添加左移。

#### 问：可以将链接或内嵌文本添加到列表项吗？

答：是的，您可以使用适当的 Markdown 语法添加链接或内联文本以列出项目。