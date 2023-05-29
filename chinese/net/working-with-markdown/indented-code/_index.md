---
title: 缩进代码
linktitle: 缩进代码
second_title: Aspose.Words for .NET API 参考
description: 通过 Aspose.Words for .NET 分步指南了解如何使用缩进代码。
type: docs
weight: 10
url: /zh/net/working-with-markdown/indented-code/
---

在这个例子中，我们将解释如何使用 Aspose.Words for .NET 的缩进代码功能。缩进代码用于直观地表示具有特定格式的代码块。

## 第 1 步：使用文档生成器

首先，我们将使用文档生成器将内容添加到我们的文档中。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 第 2 步：为缩进代码添加样式

我们将使用以下代码为缩进代码添加自定义样式`Styles.Add`的方法`Document`目的。在这个例子中，我们正在为缩进代码创建一个名为“IndentedCode”的样式。

```csharp
Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
```

## 第 3 步：添加缩进代码

现在我们可以使用“IndentedCode”自定义样式添加缩进代码块。

```csharp
builder.Writeln("This is an indented code block");
```

### 使用 Aspose.Words for .NET 的缩进代码示例源代码

```csharp
//使用文档生成器向文档添加内容。
DocumentBuilder builder = new DocumentBuilder();

Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
builder.Writeln("This is an indented code");
```

恭喜！您现在已经了解了如何使用 Aspose.Words for .NET 的缩进代码功能。

