---
title: 围栏代码
linktitle: 围栏代码
second_title: Aspose.Words for .NET API 参考
description: 通过 Aspose.Words for .NET 分步指南了解如何使用隔离代码功能。
type: docs
weight: 10
url: /zh/net/working-with-markdown/fenced-code/
---

在这个例子中，我们将带您了解如何使用 Aspose.Words for .NET 的防护代码功能。围栏代码用于表示具有特定格式的代码块。

## 第 1 步：使用文档生成器

首先，我们将使用文档生成器将内容添加到我们的文档中。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 第 2 步：为防护代码添加样式

我们将使用`Styles.Add`的方法`Document`目的。在此示例中，我们正在为受防护的代码创建一个名为“FencedCode”的样式。

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
```

## 第 3 步：添加没有信息的防护代码

现在我们可以使用“FencedCode”自定义样式添加一个没有信息字符串的围栏代码块。

```csharp
builder.Writeln("This is an fenced code");
```

## 第 4 步：添加带有信息字符串的防护代码

我们还可以使用另一种自定义样式添加带有一串信息的围栏代码块。在此示例中，我们正在创建一个名为“FencedCode.C#”的样式来表示 C# 代码块。

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


