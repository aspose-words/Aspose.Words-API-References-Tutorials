---
title: 项目符号列表
linktitle: 项目符号列表
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 分步指南创建项目符号列表。
type: docs
weight: 10
url: /zh/net/working-with-markdown/bulleted-list/
---

在本教程中，我们将告诉您如何使用 Aspose.Words for .NET 创建项目符号列表。项目符号列表用于列出不使用编号的项目。

## 步骤 1：使用文档生成器

首先，我们将使用文档生成器向文档添加内容。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 步骤 2：应用默认项目符号列表

我们可以使用文档生成器的`ApplyBulletDefault`方法。

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## 步骤 3：自定义项目符号格式

我们可以通过访问以下属性来自定义项目符号格式`ListFormat.List.ListLevels[0]`在本例中，我们使用破折号“-”作为项目符号。

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## 步骤 4：将项目添加到列表

现在我们可以使用文档生成器的`Writeln`方法。

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## 步骤 5：从列表中删除缩进

如果我们想创建一个子列表，我们可以使用`ListFormat.ListIndent()`方法。在此示例中，我们向项目 2a 和 2b 添加子列表。

```csharp
builder.ListFormat.ListIndent();
builder. Writeln("Element 2a");
builder.Writeln("Element 2b");
```
### 使用 Aspose.Words for .NET 的项目符号列表示例源代码


```csharp
//使用文档生成器向文档添加内容。
DocumentBuilder builder = new DocumentBuilder();

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

恭喜！您现在已经了解了如何使用 Aspose.Words for .NET 创建项目符号列表。

### 常见问题解答

#### 问：如何在 Markdown 中创建项目符号列表？

答：要在 Markdown 中创建项目符号列表，请用项目符号符号 (`-`, `*`， 或者`+`)，后面跟着一个空格。

#### 问：Markdown 中可以嵌套项目符号列表吗？

答：是的，可以在 Markdown 中嵌套项目符号列表，通过在每个嵌套列表项前面添加四个偏移空格。

#### 问：如何自定义项目符号？

A：在标准 Markdown 中，项目符号是预定义的。但是，有些 Markdown 编辑器允许您使用特定扩展来自定义它们。

#### 问：Markdown 中的项目符号列表支持缩进吗？

答：是的，Markdown 中的项目符号列表支持缩进。您可以使用空格或制表符添加左移。

#### 问：列表项中可以添加链接或内联文本吗？

答：是的，您可以使用适当的 Markdown 语法向列表项添加链接或内联文本。
