---
title: 在替换模式中识别和替换
linktitle: 在替换模式中识别和替换
second_title: Aspose.Words for .NET API 参考
description: 了解如何在 Aspose.Words for .NET 中使用带有识别和替换的替换模式来操作 Word 文档。
type: docs
weight: 10
url: /zh/net/find-and-replace-text/recognize-and-substitutions-within-replacement-patterns/
---

在本文中，我们将探索上述 C# 源代码，以了解如何在 Aspose.Words for .NET 库中使用 Recognize And Substitutions Within Replacement Patterns 功能。此功能有助于识别复杂的搜索模式并根据在文档操作期间捕获的组执行替换。

## 先决条件

- C# 语言的基础知识。
- 安装了 Aspose.Words 库的 .NET 开发环境。

## 第 1 步：创建新文档

在我们开始在替换模式中使用匹配和替换之前，我们需要使用 Aspose.Words for .NET 创建一个新文档。这可以通过实例化一个`Document`目的：

```csharp
Document doc = new Document();
```

## 第 2 步：在文档中插入文本

一旦我们有了文档，我们就可以使用`DocumentBuilder`目的。在我们的示例中，我们使用`Write`插入短语“Jason gives Paul some money”的方法。 :

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

## 第 3 步：替换模式中的识别和替换

现在我们将使用`Range.Replace`函数执行文本搜索和替换使用正则表达式来识别特定模式。在我们的示例中，我们使用正则表达式`([A-z]+) gives money to ([A-z]+)`识别某人给别人钱的句子。我们使用替换模式`$2 takes money from $1`通过颠倒角色来执行替换。指某东西的用途`$1`和`$2`引用正则表达式捕获的组：

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");

FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

### Recognize And Substitutions Within Replacement Patterns using Aspose.Words for .NET 示例源代码

下面是完整的示例源代码，用于说明在 Aspose.Words for .NET 的替换模式中匹配和替换的使用：

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Jason give money to Paul.");

	Regex regex = new Regex(@"([A-z]+) give money to ([A-z]+)");

	FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

	doc.Range.Replace(regex, @"$2 take money from $1", options);

```

## 结论

在本文中，我们研究了 C# 源代码以了解如何使用 Aspose.Words for .NET 的 Recognize And Substitutions Within Replacement Patterns 功能。我们按照分步指南创建文档、插入文本、使用正则表达式和基于捕获的组的替换模式执行搜索和替换，以及操作文档。
