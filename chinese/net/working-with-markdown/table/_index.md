---
title: 桌子
linktitle: 桌子
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 分步指南创建表格。
type: docs
weight: 10
url: /zh/net/working-with-markdown/table/
---


在此示例中，我们将引导您了解如何使用 Aspose.Words for .NET 创建表格。表是一种将信息组织成行和列的数据结构。

## 第 1 步：使用文档生成器

首先，我们将使用文档生成器将内容添加到文档中。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```


## 第 2 步：添加单元格和数据

我们将使用以下命令将单元格和数据添加到表格中`InsertCell`方法和`Writeln`文档生成器的方法。

```csharp
builder. InsertCell();
builder.Writeln("a");
builder. InsertCell();
builder.Writeln("b");

builder. InsertCell();
builder.Writeln("c");
builder. InsertCell();
builder.Writeln("d");
```

### 使用 Aspose.Words for .NET 创建表格的示例源代码

```csharp
//使用文档生成器将内容添加到文档中。
DocumentBuilder builder = new DocumentBuilder();

//添加第一行。
builder.InsertCell();
builder.Writeln("a");
builder.InsertCell();
builder.Writeln("b");

//添加第二行。
builder.InsertCell();
builder.Writeln("c");
builder.InsertCell();
builder.Writeln("d");
```

恭喜！您现在已经学习了如何使用 Aspose.Words for .NET 创建表格。

### 常见问题解答

#### 问：如何在 Markdown 中创建表格？

答：要在 Markdown 中创建表格，请使用管道语法 (`|`) 来分隔单元格和破折号 (`-`) 来分隔表头。

#### 问：我们可以在 Markdown 中自定义表格的外观吗？

答：在标准 Markdown 中，表格自定义选项是有限的。但是，某些 Markdown 编辑器允许您向表格添加 CSS 样式以自定义其外观。

#### 问：如何在 Markdown 中合并表格中的单元格？

答：在 Markdown 中合并表格中的单元格取决于所使用的 Markdown 编辑器。一些 Markdown 编辑器支持使用特定语法合并单元格。

#### 问：Markdown 中的表格支持 CSS 样式吗？

答：在标准 Markdown 中，表格不提供对 CSS 样式的直接支持。但是，某些 Markdown 编辑器允许您向表格添加 CSS 样式以自定义其外观。

#### 问：我们可以在 Markdown 表格的单元格中添加内联格式的链接或文本吗？

答：是的，您可以使用适当的 Markdown 语法将链接或内联文本添加到 Markdown 中的表格单元格。