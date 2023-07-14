---
title: 围栏代码
linktitle: 围栏代码
second_title: Aspose.Words 文档处理 API
description: 了解如何通过 Aspose.Words for .NET 分步指南使用隔离代码功能。
type: docs
weight: 10
url: /zh/net/working-with-markdown/fenced-code/
---

在此示例中，我们将引导您了解如何通过 Aspose.Words for .NET 使用隔离代码功能。围栏代码用于表示具有特定格式的代码块。

## 第 1 步：使用文档生成器

首先，我们将使用文档生成器将内容添加到文档中。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 第 2 步：添加受防护代码的样式

我们将使用以下命令为受防护的代码添加自定义样式`Styles.Add`的方法`Document`目的。在此示例中，我们为受保护的代码创建一个名为“FencedCode”的样式。

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
```

## 第 3 步：添加不带信息的防护代码

现在我们可以使用“FencedCode”自定义样式添加一个没有信息字符串的隔离代码块。

```csharp
builder.Writeln("This is an fenced code");
```

## 第 4 步：添加带有信息字符串的防护代码

我们还可以使用另一种自定义样式添加带有一串信息的围栏代码块。在此示例中，我们将创建一个名为“FencedCode.C#”的样式来表示 C# 代码块。

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### 使用 Aspose.Words for .NET 的 Fenced Code 的示例源代码

```csharp
//使用文档生成器将内容添加到文档中。
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

答：Markdown 中的分隔代码是一种用于在 Markdown 文档中显示代码的格式化方法。它包括使用特定分隔符构建代码。

#### 问：Markdown 中分隔代码有什么好处？

答：Markdown 中的分隔代码提高了代码的可读性，让读者更容易理解。它还允许在某些 Markdown 编辑器中保留语法突出显示。

#### 问：Markdown 中分隔代码和缩进代码有什么区别？

答：分隔代码使用特定的分隔符将代码括起来，而缩进代码则涉及使用空格或制表符缩进每行代码。

#### 问：所有 Markdown 编辑器都支持 Markdown 中的分隔代码吗？

答：Markdown 中对分隔代码的支持可能因 Markdown 编辑器而异。请检查您的发布商的具体文档以确保确定。

