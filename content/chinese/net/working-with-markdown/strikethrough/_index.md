---
title: 删除线
linktitle: 删除线
second_title: Aspose.Words 文档处理 API
description: 通过我们的分步指南学习如何使用 Aspose.Words for .NET 将删除线格式应用于文本。增强您的文档处理技能。
type: docs
weight: 10
url: /zh/net/working-with-markdown/strikethrough/
---
## 介绍

欢迎阅读本详细指南，了解如何使用 Aspose.Words for .NET 将删除线格式应用于文本。如果您希望增强文档处理技能并为您的文本添加独特的风格，那么您来对地方了。让我们开始吧！

## 先决条件

在开始之前，请确保您已准备好以下物品：

-  Aspose.Words for .NET：下载[这里](https://releases.aspose.com/words/net/).
- .NET Framework：确保您的系统上安装了 .NET Framework。
- 开发环境：像 Visual Studio 这样的 IDE。
- C# 基础知识：必须熟悉 C# 编程。

## 导入命名空间

首先，您需要导入必要的命名空间。这些对于访问 Aspose.Words 库及其功能至关重要。

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## 步骤 1：初始化 DocumentBuilder

这`DocumentBuilder`类是 Aspose.Words 中的一个强大工具，可以让您轻松地向文档中添加内容。

```csharp
//初始化一个 DocumentBuilder。
DocumentBuilder builder = new DocumentBuilder();
```

## 步骤 2：设置删除线属性

现在，让我们将删除线属性应用于文本。这涉及设置`StrikeThrough`的财产`Font`反对`true`.

```csharp
//给文本添加删除线。
builder.Font.StrikeThrough = true;
```

## 步骤 3：使用删除线书写文字

设置删除线属性后，我们现在可以添加文本。`Writeln`方法会将文本添加到文档中。

```csharp
//写带有删除线的文字。
builder.Writeln("This text will be StrikeThrough");
```

## 结论

就这样！您已成功使用 Aspose.Words for .NET 为文本添加了删除线格式。这个强大的库为文档处理和自定义开辟了无限可能。无论您是创建报告、信函还是任何其他类型的文档，掌握这些功能无疑会提高您的工作效率和输出质量。

## 常见问题解答

### 什么是 Aspose.Words for .NET？
Aspose.Words for .NET 是一个强大的文档处理库，允许开发人员以编程方式创建、操作和转换 Word 文档。

### 我可以在商业项目中使用 Aspose.Words for .NET 吗？
是的，您可以在商业项目中使用 Aspose.Words for .NET。有关购买选项，请访问[购买页面](https://purchase.aspose.com/buy).

### Aspose.Words for .NET 有免费试用版吗？
是的，您可以下载免费试用版[这里](https://releases.aspose.com/).

### 如何获得 Aspose.Words for .NET 的支持？
您可以从 Aspose 社区和专家处获得支持[支持论坛](https://forum.aspose.com/c/words/8).

### 我可以使用 Aspose.Words for .NET 应用其他文本格式选项吗？
当然！Aspose.Words for .NET 支持多种文本格式选项，包括粗体、斜体、下划线等。