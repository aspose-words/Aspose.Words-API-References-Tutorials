---
title: 引用
linktitle: 引用
second_title: Aspose.Words for .NET API 参考
description: 了解如何通过 Aspose.Words for .NET 分步指南使用引号。
type: docs
weight: 10
url: /zh/net/working-with-markdown/quote/
---

在这个例子中，我们将解释如何使用 Aspose.Words for .NET 的引号功能 引号用于通过用特殊边框围绕文本部分来突出显示它们。

## 第 1 步：使用文档生成器

首先，我们将使用文档生成器将内容添加到我们的文档中。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 第 2 步：使用默认引用样式

我们将使用名为“引用”的默认段落样式将引用格式应用于文本。

```csharp
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");
```

## 第 3 步：为嵌套级别创建样式

我们可以使用`Styles.Add`的方法`Document`目的。在此示例中，我们正在创建一个名为“Quote1”的样式来表示嵌套引用级别。

```csharp
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

### 使用 Aspose.Words for .NET 的引用示例源代码


```csharp
	//使用文档生成器向文档添加内容。
	DocumentBuilder builder = new DocumentBuilder();

	//默认情况下，文档存储第一级的块引用样式。
	builder.ParagraphFormat.StyleName = "Quote";
	builder.Writeln("Blockquote");

	//通过样式继承为嵌套级别创建样式。
	Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
	builder.ParagraphFormat.Style = quoteLevel2;
	builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
	builder.Writeln("1. Nested blockquote");
            
```

恭喜！您现在已经学习了如何使用 Aspose.Words for .NET 的引用功能。

