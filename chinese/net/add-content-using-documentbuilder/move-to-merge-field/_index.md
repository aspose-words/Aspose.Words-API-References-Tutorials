---
title: 移动到合并字段
linktitle: 移动到合并字段
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用分步指南在 Aspose.Words for .NET 中实现移动到合并字段功能。
type: docs
weight: 10
url: /zh/net/add-content-using-documentbuilder/move-to-merge-field/
---

在这个例子中，我们将探索 Aspose.Words for .NET 的 Move To Merge Field 特性。 Aspose.Words 是一个强大的文档操作库，使开发人员能够以编程方式创建、修改和转换 Word 文档。移动到合并字段功能允许我们导航到文档中的合并字段并对它们执行各种操作。


## 逐步解释源代码

让我们逐步浏览源代码，了解如何使用 Aspose.Words for .NET 的“移动到合并字段”功能。

## 第 1 步：初始化文档和文档生成器

首先，初始化 Document 和 DocumentBuilder 对象：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步插入合并字段并在其后添加文本

使用 DocumentBuilder 类的 InsertField 方法插入合并字段，然后在其后添加文本：

```csharp
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");
```

## 第 3 步：构建器的光标当前位于文档的末尾。

```csharp
Assert.Null(builder.CurrentNode);
```
## 第 4 步：将文档构建器光标移动到合并字段

要将文档构建器光标移动到合并字段，请使用 DocumentBuilder 类的 MoveToField 方法：

```csharp
builder.MoveToField(field, true);
```

## 在合并字段后立即添加文本

一旦文档生成器光标位于合并字段内，您可以使用 Write 方法在其后立即添加文本：

```csharp
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

### 使用 Aspose.Words for .NET 的 Move To Merge Field 示例源代码

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	//使用 DocumentBuilder 插入一个字段并在其后添加一段文本。
	Field field = builder.InsertField("MERGEFIELD field");
	builder.Write(" Text after the field.");

	//构建器的光标当前位于文档末尾。
	Assert.Null(builder.CurrentNode);
	//我们可以像这样将构建器移动到一个字段，将光标放在该字段之后。
	builder.MoveToField(field, true);

	//请注意，光标位于字段的 FieldEnd 节点之后的位置，这意味着我们实际上并不在该字段内。
	//如果我们希望将 DocumentBuilder 移动到字段内部，
	//我们需要使用 DocumentBuilder.MoveTo() 方法将其移动到字段的 FieldStart 或 FieldSeparator 节点。
	Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
	builder.Write(" Text immediately after the field.");
	
```

## 结论

我们已经探索了 Aspose.Words for .NET 的 Move To Merge Field 特性。我们学习了如何使用 DocumentBuilder 类导航到文档中的合并字段并对它们执行操作。当以编程方式使用合并时，此功能很有用

