---
title: 项目符号列表
linktitle: 项目符号列表
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 分步指南创建项目符号列表。
type: docs
weight: 10
url: /zh/net/working-with-markdown/bulleted-list/
---

在本教程中，我们将告诉您如何使用 Aspose.Words for .NET 创建项目符号列表。项目符号列表用于在不使用编号的情况下列出项目。

## 第 1 步：使用文档生成器

首先，我们将使用文档生成器将内容添加到我们的文档中。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 第 2 步：应用默认项目符号列表

我们可以使用文档生成器的应用默认项目符号列表`ApplyBulletDefault`方法。

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## 第 3 步：自定义项目符号格式

我们可以通过访问的属性来自定义项目符号格式`ListFormat.List.ListLevels[0]`.在本例中，我们使用破折号“-”作为项目符号。

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## 第 4 步：将项目添加到列表

现在我们可以使用文档生成器的将项目添加到项目符号列表`Writeln`方法。

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## 第 5 步：从列表中删除缩进

如果我们想创建一个子列表，我们可以使用`ListFormat.ListIndent()`方法。在此示例中，我们向项目 2a 和 2b 添加了一个子列表。

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

恭喜！您现在已经学习了如何使用 Aspose.Words for .NET 创建项目符号列表。

