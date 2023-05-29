---
title: 行内代码
linktitle: 行内代码
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 分步指南内联代码。
type: docs
weight: 10
url: /zh/net/working-with-markdown/inline-code/
---

在本例中，我们将带您了解如何使用 Aspose.Words for .NET 的内联代码功能。内联代码用于直观地表示段落中的代码片段。

## 第 1 步：使用文档生成器

首先，我们将使用文档生成器将内容添加到我们的文档中。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 第 2 步：为内联代码添加样式

我们将使用`Styles.Add`的方法`Document`目的。在这个例子中，我们正在为带有默认反引号的内联代码创建一个名为“InlineCode”的样式。

```csharp
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
```

## 第 3 步：添加内联代码

现在我们可以使用“InlineCode”自定义样式添加内联代码。在此示例中，我们添加了两段具有不同数量反引号的文本。

```csharp
builder.Writeln("Text with InlineCode style with 1 backtick");
```

```csharp
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```


### 使用 Aspose.Words for .NET 的内联代码示例源代码

```csharp
//使用文档生成器向文档添加内容。
DocumentBuilder builder = new DocumentBuilder();

//缺少反引号的数量，默认使用一个反引号。
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
builder.Writeln("Text with InlineCode style with 1 backtick");

//将有 3 个反引号。
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backtick");
```

恭喜！您现在已经了解了如何使用 Aspose.Words for .NET 的内联代码功能。

