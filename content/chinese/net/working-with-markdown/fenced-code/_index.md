---
title: 围栏代码
linktitle: 围栏代码
second_title: Aspose.Words 文档处理 API
description: 了解如何通过 Aspose.Words for .NET 分步指南使用隔离代码功能。
type: docs
weight: 10
url: /zh/net/working-with-markdown/fenced-code/
---

在此示例中，我们将引导您了解如何使用 Aspose.Words for .NET 的隔离代码功能。隔离代码用于表示具有特定格式的代码块。

## 步骤 1：使用文档生成器

首先，我们将使用文档生成器向文档添加内容。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 步骤 2：添加隔离代码的样式

我们将使用以下代码为围栏代码添加自定义样式：`Styles.Add`方法`Document`对象。在此示例中，我们为隔离代码创建一个名为“FencedCode”的样式。

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
```

## 步骤 3：添加不含信息的隔离代码

现在我们可以使用“FencedCode”自定义样式添加没有信息字符串的围栏代码块。

```csharp
builder.Writeln("This is an fenced code");
```

## 步骤 4：添加带有信息字符串的隔离代码

我们还可以使用另一种自定义样式添加带有信息字符串的隔离代码块。在此示例中，我们创建了一个名为“FencedCode.C#”的样式来表示一段 C# 代码。

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### 使用 Aspose.Words for .NET 的 Fenced Code 示例源代码

```csharp
//使用文档生成器向文档添加内容。
DocumentBuilder builder = new DocumentBuilder();

Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is an fenced code");

Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### 常见问题解答

#### 问：Markdown 中的分隔代码是什么？

A：Markdown 中的分隔代码是一种用于在 Markdown 文档中显示代码的格式化方法。它包括使用特定分隔符来框住代码。

#### 问：Markdown 中分隔代码有什么好处？

答：Markdown 中的分隔代码可提高代码的可读性，使读者更容易理解。它还允许在某些 Markdown 编辑器中保留语法突出显示。

#### 问：Markdown 中的分隔代码和缩进代码有什么区别？

答：分隔代码使用特定的分隔符来括住代码，而缩进代码则使用空格或制表符来缩进每行代码。

#### 问：Markdown 中的分隔代码是否所有 Markdown 编辑器都支持？

答：不同 Markdown 编辑器对 Markdown 中分隔代码的支持可能有所不同。请查看发布商的具体文档以确保无误。

