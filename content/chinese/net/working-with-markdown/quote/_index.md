---
title: 引用
linktitle: 引用
second_title: Aspose.Words 文档处理 API
description: 了解如何通过 Aspose.Words for .NET 分步指南使用引用。
type: docs
weight: 10
url: /zh/net/working-with-markdown/quote/
---

在这个例子中，我们将解释如何使用 Aspose.Words for .NET 的引用功能。引用用于通过用特殊边框包围文本部分来突出显示文本部分。

## 步骤 1：使用文档生成器

首先，我们将使用文档生成器向文档添加内容。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 步骤 2：使用默认引用样式

我们将使用名为“Quote”的默认段落样式将引号格式应用于文本。

```csharp
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");
```

## 步骤 3：创建嵌套级别的样式

我们可以使用以下方式创建嵌套级别的样式`Styles.Add`方法`Document`对象。在此示例中，我们创建一个名为“Quote1”的样式来表示嵌套的引用级别。

```csharp
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

### 使用 Aspose.Words for .NET 进行引用的示例源代码


```csharp
//使用文档生成器向文档添加内容。
DocumentBuilder builder = new DocumentBuilder();

//默认情况下，文档存储第一级的 blockquote 样式。
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");

//通过样式继承为嵌套级别创建样式。
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

恭喜！您现在已经了解了如何使用 Aspose.Words for .NET 的引文功能。


### 常见问题解答

#### 问：Markdown 中的引用是什么？

答：Markdown 中的引用是一种突出显示来自其他来源的文本段落或引用名人名言的方式。

#### 问：如何在 Markdown 中使用引号？

答：要在 Markdown 中使用引文，请将引文文本括在尖括号中 (`>`）。引文的每一行都必须以 V 形符号开头。

#### Q：Markdown 引文支持属性吗？

A：Markdown 引用不支持指定属性，只是通过引用文本的格式来高亮显示。

#### 问：你能在 Markdown 中嵌入引号吗？

答：是的，可以在 Markdown 中嵌套引号，只需添加额外的尖括号 (`>`）。