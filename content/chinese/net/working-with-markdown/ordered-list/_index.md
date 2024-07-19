---
title: 有序列表
linktitle: 有序列表
second_title: Aspose.Words 文档处理 API
description: 通过我们的分步指南学习如何使用 Aspose.Words for .NET 在 Word 文档中创建有序列表。非常适合自动创建文档。
type: docs
weight: 10
url: /zh/net/working-with-markdown/ordered-list/
---
## 介绍

因此，您已决定深入研究 Aspose.Words for .NET，以编程方式创建出色的 Word 文档。绝佳选择！今天，我们将详细介绍如何在 Word 文档中创建有序列表。我们将一步一步讲解，因此无论您是编码新手还是经验丰富的专业人士，您都会发现本指南非常有用。让我们开始吧！

## 先决条件

在深入研究代码之前，您需要准备一些东西：

1.  Aspose.Words for .NET：确保已安装 Aspose.Words for .NET。如果没有，您可以下载[这里](https://releases.aspose.com/words/net/).
2. 开发环境：Visual Studio 或任何其他.NET 兼容 IDE。
3. C# 基础知识：您应该熟悉 C# 基础知识，以便轻松跟进。

## 导入命名空间

要在项目中使用 Aspose.Words，您需要导入必要的命名空间。这就像在开始工作之前设置工具箱一样。

```csharp
using Aspose.Words;
using Aspose.Words.Lists;
```

让我们将代码分解成几个小步骤并解释每个部分。准备好了吗？开始吧！

## 步骤 1：初始化文档

首先，您需要创建一个新文档。这就像在计算机上打开一个空白的 Word 文档。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

这里，我们初始化一个新文档和一个 DocumentBuilder 对象。DocumentBuilder 就像你的笔，让你可以将内容写入文档。

## 步骤 2：应用编号列表格式

现在，让我们应用默认的编号列表格式。这就像将 Word 文档设置为使用编号项目符号一样。

```csharp
builder.ListFormat.ApplyNumberDefault();
```

这行代码设置了列表的编号。很简单，对吧？

## 步骤 3：添加列表项

接下来，让我们将一些物品添加到列表中。想象一下你正在记下购物清单。

```csharp
builder.Writeln("Item 1");
builder.Writeln("Item 2");
```

通过这几行，您可以将前两项添加到列表中。

## 步骤 4：缩进列表

如果你想在某个项目下添加子项目怎么办？让我们来做吧！

```csharp
builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

这`ListIndent`方法缩进列表，创建子列表。现在，您正在创建一个分层列表，就像嵌套的待办事项列表一样。

## 结论

一开始，以编程方式在 Word 文档中创建有序列表似乎很困难，但使用 Aspose.Words for .NET，这很容易。通过遵循这些简单的步骤，您可以轻松地在文档中添加和管理列表。无论您是生成报告、创建结构化文档，还是只是自动化工作流程，Aspose.Words for .NET 都能满足您的需求。那么，还等什么？开始编码，看看奇迹是如何发生的吧！

## 常见问题解答

### 我可以自定义列表的编号样式吗？  
是的，你可以使用`ListFormat`属性。您可以设置不同的编号样式，如罗马数字、字母等。

### 如何添加更多级别的缩进？  
您可以使用`ListIndent`方法多次创建更深层次的子列表。每次调用`ListIndent`添加一级缩进。

### 我可以混合使用项目符号和编号列表吗？  
当然可以！您可以使用`ListFormat`财产。

### 是否可以从先前的列表继续编号？  
是的，您可以使用相同的列表格式继续编号。Aspose.Words 允许您控制不同段落的列表编号。

### 我怎样才能删除列表格式？  
您可以通过调用删除列表格式`ListFormat.RemoveNumbers()`。这会将列表项变回常规段落。