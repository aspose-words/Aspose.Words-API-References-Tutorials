---
title: 比较粒度
linktitle: 比较粒度
second_title: Aspose.Words 文档处理 API
description: 了解 Aspose.Words for .NET 的比较粒度功能，该功能允许逐字符比较文档，报告所做的更改。
type: docs
weight: 10
url: /zh/net/compare-documents/comparison-granularity/
---
以下是解释下面 C# 源代码的分步指南，该源代码使用 Aspose.Words for .NET 的比较粒度功能。

## 第 1 步：简介

Aspose.Words for .NET 的比较粒度功能允许您在字符级别比较文档。这意味着将比较每个字符并相应地报告变化。

## 第2步：设置环境

在开始之前，您需要设置开发环境以使用 Aspose.Words for .NET。确保您已安装 Aspose.Words 库并拥有合适的 C# 项目来嵌入代码。

## 第 3 步：添加所需的程序集

要使用 Aspose.Words for .NET 的比较粒度功能，您需要将必要的程序集添加到项目中。确保您的项目中有对 Aspose.Words 的正确引用。

```csharp
using Aspose.Words;
using Aspose.Words.DocumentBuilder;
```

## 第 4 步：创建文档

在此步骤中，我们将使用 DocumentBuilder 类创建两个文档。这些文件将用于比较。

```csharp
//创建文档A。
DocumentBuilder builderA = new DocumentBuilder(new Document());
builderA.Writeln("This is a simple A word.");

//创建文档B。
DocumentBuilder builderB = new DocumentBuilder(new Document());
builderB.Writeln("This is simple B words.");
```

## 第 5 步：配置比较选项

在此步骤中，我们将配置比较选项以指定比较粒度。这里我们将使用字符级粒度。

```csharp
CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };
```

## 第六步：文档比较

现在让我们使用 Document 类的 Compare 方法来比较文档。更改将保存在文档 A 中。

```csharp
builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);
```

这`Compare`方法将文档 A 与文档 B 进行比较，并将更改保存到文档 A。您可以指定作者姓名和比较日期以供参考。

## 结论

在本文中，我们探讨了 Aspose.Words for .NET 的比较粒度功能。此功能允许您在字符级别比较文档并报告更改。您可以使用这些知识在项目中执行详细的文档比较。

### 使用 Aspose.Words for .NET 进行比较粒度的示例源代码

```csharp
            
DocumentBuilder builderA = new DocumentBuilder(new Document());
DocumentBuilder builderB = new DocumentBuilder(new Document());

builderA.Writeln("This is A simple word");
builderB.Writeln("This is B simple words");

CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };

builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);            
        
```
