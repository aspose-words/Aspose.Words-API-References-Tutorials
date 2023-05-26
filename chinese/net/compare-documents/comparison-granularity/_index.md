---
title: 比较粒度
linktitle: 比较粒度
second_title: Aspose.Words for .NET API 参考
description: 了解 Aspose.Words for .NET 的比较粒度功能，它允许逐个字符地比较文档，报告所做的更改。
type: docs
weight: 10
url: /zh/net/compare-documents/comparison-granularity/
---
这是一个分步指南，用于解释下面的 C# 源代码，它使用 Aspose.Words for .NET 的比较粒度功能。

## 第 1 步：介绍

Aspose.Words for .NET 的比较粒度功能允许您在字符级别比较文档。这意味着将比较每个字符并相应地报告更改。

## 第 2 步：设置环境

在开始之前，您需要设置您的开发环境以使用 Aspose.Words for .NET。确保你已经安装了 Aspose.Words 库并且有一个合适的 C# 项目来嵌入代码。

## 第 3 步：添加所需的程序集

要使用 Aspose.Words for .NET 的比较粒度功能，您需要将必要的程序集添加到您的项目中。确保您在项目中正确引用了 Aspose.Words。

```csharp
using Aspose.Words;
using Aspose.Words.DocumentBuilder;
```

## 第 4 步：创建文档

在此步骤中，我们将使用 DocumentBuilder 类创建两个文档。这些文件将用于比较。

```csharp
//创建文档 A。
DocumentBuilder builderA = new DocumentBuilder(new Document());
builderA.Writeln("This is a simple A word.");

//创建文档 B。
DocumentBuilder builderB = new DocumentBuilder(new Document());
builderB.Writeln("This is simple B words.");
```

## 第 5 步：配置比较选项

在此步骤中，我们将配置比较选项以指定比较粒度。这里我们将使用字符级粒度。

```csharp
CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };
```

## 第 6 步：文件比较

现在让我们使用 Document 类的 Compare 方法比较文档。更改将保存在文档 A 中。

```csharp
builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);
```

这`Compare`方法将文档A与文档B进行比较，并将更改保存到文档A中。您可以指定作者姓名和比较日期以供参考。

## 结论

在本文中，我们探索了 Aspose.Words for .NET 的比较粒度特性。此功能允许您在字符级别比较文档并报告更改。您可以使用这些知识在您的项目中执行详细的文档比较。

### 使用 Aspose.Words for .NET 的比较粒度示例源代码

```csharp
            
DocumentBuilder builderA = new DocumentBuilder(new Document());
DocumentBuilder builderB = new DocumentBuilder(new Document());

builderA.Writeln("This is A simple word");
builderB.Writeln("This is B simple words");

CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };

builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);            
        
```
