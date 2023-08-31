---
title: Word文档中的比较粒度
linktitle: Word文档中的比较粒度
second_title: Aspose.Words 文档处理 API
description: 了解 Aspose.Words for .NET 的 Word 文档功能中的比较粒度，该功能允许逐个字符比较文档，报告所做的更改。
type: docs
weight: 10
url: /zh/net/compare-documents/comparison-granularity/
---
以下是解释下面 C# 源代码的分步指南，该源代码使用 Aspose.Words for .NET 的 Word 文档中的比较粒度功能。

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

## 结论

在本教程中，我们探索了 Aspose.Words for .NET 的比较粒度功能。此功能允许您在比较文档时指定详细程度。通过选择不同的粒度级别，您可以根据您的具体要求在字符、单词或块级别执行详细比较。 Aspose.Words for .NET提供了灵活而强大的文档比较功能，可以轻松识别不同粒度级别的文档中的差异。

### 常见问题解答

#### 问：在 Aspose.Words for .NET 中使用比较粒度的目的是什么？

答：Aspose.Words for .NET 中的比较粒度允许您在比较文档时指定详细程度。通过此功能，您可以比较不同级别的文档，例如字符级、单词级甚至块级。每个粒度级别在比较结果中提供不同级别的详细信息。

#### 问：如何在 Aspose.Words for .NET 中使用比较粒度？

答：要在 Aspose.Words for .NET 中使用比较粒度，请按照下列步骤操作：
1. 使用 Aspose.Words 库设置您的开发环境。
2. 通过引用 Aspose.Words 将必要的程序集添加到您的项目中。
3. 使用以下命令创建要比较的文档`DocumentBuilder`班级。
4. 通过创建一个来配置比较选项`CompareOptions`对象并设置`Granularity`属性达到所需的水平（例如，`Granularity.CharLevel`用于字符级比较）。
5. 使用`Compare`一个文档上的方法，传递另一个文档和`CompareOptions`对象作为参数。该方法将根据指定的粒度比较文档，并将更改保存在第一个文档中。

#### 问：Aspose.Words for .NET 中的比较粒度有哪些可用级别？

答：Aspose.Words for .NET 提供三个级别的比较粒度：
- `Granularity.CharLevel`：在字符级别比较文档。
- `Granularity.WordLevel`：在单词级别比较文档。
- `Granularity.BlockLevel`：在块级别比较文档。

#### 问：如何解读字符级粒度的比较结果？

答：通过字符级粒度，分析比较文档中的每个字符是否存在差异。比对结果将显示单个字符级别的变化，包括添加、删除和修改。