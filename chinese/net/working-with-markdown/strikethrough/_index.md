---
title: 删除线
linktitle: 删除线
second_title: Aspose.Words for .NET API 参考
description: 通过 Aspose.Words for .NET 分步指南了解如何应用删除线文本样式。
type: docs
weight: 10
url: /zh/net/working-with-markdown/strikethrough/
---


在本例中，我们将向您介绍如何使用 Aspose.Words for .NET 应用删除线文本样式。删除线文本用于指示文本已删除或不再有效。

## 第 1 步：使用文档生成器

首先，我们将使用文档生成器将内容添加到我们的文档中。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 第 2 步：应用删除线文本样式

我们将通过设置`StrikeThrough`的财产`Font`反对`true`.

```csharp
builder.Font.StrikeThrough = true;
```

## 第 3 步：添加删除线文本

我们现在可以使用文档生成器的添加删除线文本`Writeln`方法。

```csharp
builder.Writeln("This text will be StrikeThrough");
```


### 使用 Aspose.Words for .NET 的删除线文本示例源代码

```csharp
	//使用文档生成器向文档添加内容。
	DocumentBuilder builder = new DocumentBuilder();

	//使文本删除线。
	builder.Font.StrikeThrough = true;
	builder.Writeln("This text will be StrikeThrough");
            
```

恭喜！您现在已经了解了如何使用 Aspose.Words for .NET 应用删除线文本样式。
