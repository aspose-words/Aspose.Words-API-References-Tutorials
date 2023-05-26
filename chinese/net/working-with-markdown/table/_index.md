---
title: 桌子
linktitle: 桌子
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 分步指南创建表格。
type: docs
weight: 10
url: /zh/net/working-with-markdown/table/
---


在本例中，我们将带您了解如何使用 Aspose.Words for .NET 创建表格。表是一种将信息组织成行和列的数据结构。

## 第 1 步：使用文档生成器

首先，我们将使用文档生成器将内容添加到我们的文档中。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```


## 第 2 步：添加单元格和数据

我们将使用`InsertCell`方法和`Writeln`文档生成器的方法。

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
	//使用文档生成器向文档添加内容。
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
