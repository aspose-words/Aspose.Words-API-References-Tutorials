---
title: 标题
linktitle: 标题
second_title: Aspose.Words for .NET API 参考
description: 通过 Aspose.Words for .NET 分步指南了解如何使用标题。
type: docs
weight: 10
url: /zh/net/working-with-markdown/heading/
---

在这个例子中，我们将向您展示如何使用 Aspose.Words for .NET 的标题功能。标题用于对文档内容进行结构化和优先级排序。

## 第 1 步：使用文档生成器

首先，我们将使用文档生成器将内容添加到我们的文档中。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 第 2 步：自定义标题样式

默认情况下，Word 中的标题样式可以采用粗体和斜体格式。如果我们不想强制执行这些属性，我们需要将它们显式设置为“false”。

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## 第 3 步：添加 1 级标题

我们可以通过指定适当的段落样式名称并使用`Writeln`标题内容的写法。

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

### 使用 Aspose.Words for .NET 标题的示例源代码


```csharp
	//使用文档生成器向文档添加内容。
	DocumentBuilder builder = new DocumentBuilder();

	//默认情况下，Word 中的标题样式可能具有粗体和斜体格式。
	//如果我们不想被强调，请将这些属性显式设置为 false。
	builder.Font.Bold = false;
	builder.Font.Italic = false;

	builder.ParagraphFormat.StyleName = "Heading 1";
	builder.Writeln("This is an H1 tag");
            
```

恭喜！您现在已经了解了如何使用 Aspose.Words for .NET 的标题功能。


