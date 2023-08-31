---
title: 引用
linktitle: 引用
second_title: Aspose.Words 文档处理 API
description: 了解如何通过 Aspose.Words for .NET 分步指南使用引用。
type: docs
weight: 10
url: /zh/net/working-with-markdown/quote/
---

在此示例中，我们将解释如何使用 Aspose.Words for .NET Quote 的引用功能，通过用特殊边框包围文本部分来突出显示它们。

## 第 1 步：使用文档生成器

首先，我们将使用文档生成器将内容添加到文档中。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 第 2 步：使用默认引文样式

我们将使用名为“引用”的默认段落样式将引用格式应用于文本。

```csharp
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");
```

## 步骤 3：为嵌套级别创建样式

我们可以使用以下命令为嵌套级别创建样式`Styles.Add`的方法`Document`目的。在此示例中，我们创建一个名为“Quote1”的样式来表示嵌套报价级别。

```csharp
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

### 使用 Aspose.Words for .NET 进行引用的示例源代码


```csharp
//使用文档生成器将内容添加到文档中。
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

恭喜！您现在已经了解了如何使用 Aspose.Words for .NET 的引文功能。


### 常见问题解答

#### 问：Markdown 中的引用是什么？

答：Markdown 中的引用是一种突出显示其他来源的文本段落或引用著名引用的方法。

#### 问：如何在 Markdown 中使用引号？

答：要在 Markdown 中使用引用，请将引用文本括在尖括号中 (`>`）。引文的每一行必须以 V 形开头。

#### 问：Markdown 引号支持属性吗？

答：Markdown 引用不支持特定属性。它们只是通过引用文本的格式来突出显示。

#### 问：可以在 Markdown 中嵌入引号吗？

答：是的，可以通过添加额外的尖括号（`>`）。