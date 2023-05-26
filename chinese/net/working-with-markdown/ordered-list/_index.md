---
title: 有序列表
linktitle: 有序列表
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 分步指南创建有序列表。
type: docs
weight: 10
url: /zh/net/working-with-markdown/ordered-list/
---

在这个例子中，我们将解释如何使用 Aspose.Words for .NET 的有序列表功能。有序列表允许您按顺序组织项目。

## 第 1 步：使用文档生成器

首先，我们将使用文档生成器来创建一个新文档。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：应用有序列表格式

我们将使用文档生成器的应用有序列表格式`ApplyBulletDefault`方法。我们还可以通过转到列表级别并设置我们想要的格式来自定义编号格式。

```csharp
builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";
```

## 第 3 步：将项目添加到列表

我们可以使用文档生成器的`Writeln`方法。

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## 第 4 步：缩进列表

我们可以使用文档生成器的缩进列表`ListIndent`方法。

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

## 第 5 步：保存文档

最后，我们可以将文档保存为所需的格式。

### 使用 Aspose.Words for .NET 的有序列表示例源代码

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

恭喜！您现在已经了解了如何使用 Aspose.Words for .NET 的有序列表功能。

