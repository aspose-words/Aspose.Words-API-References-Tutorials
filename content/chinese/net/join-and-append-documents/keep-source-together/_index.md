---
title: 保持源代码一致
linktitle: 保持源代码一致
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 合并 Word 文档并保留格式。本综合指南涵盖从设置到执行的所有内容。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/keep-source-together/
---
## 介绍

在当今的数字时代，以编程方式处理 Word 文档对于各个行业都至关重要。Aspose.Words for .NET 使开发人员能够高效地自动执行文档处理任务。本综合指南将引导您完成使用 Aspose.Words for .NET 合并文档并保留源格式的过程。

## 先决条件

在深入使用 Aspose.Words for .NET 进行文档合并之前，请确保您具有以下条件：

- Visual Studio：用于 .NET 开发的集成开发环境 (IDE)。
- Aspose.Words for .NET：在您的开发环境中安装并设置。
- 熟悉 C#：对 C# 编程语言有基本的了解。

## 导入命名空间

首先，导入必要的命名空间：

```csharp
using Aspose.Words;
using Aspose.Words.DocumentBuilder;
```

## 步骤 1：加载文档

首先，将源文档和目标文档加载到 Aspose.Words 中`Document`对象。

```csharp
//文档目录的路径
string dataDir = "YOUR_DOCUMENT_DIRECTORY/";

//加载源文档和目标文档
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## 第 2 步：设置章节开始

配置节开始以确保源文档内容在目标文档之后连续流动。

```csharp
//将源文档设置为紧接着目标文档的内容出现
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## 步骤 3：保持段落连贯

为了保持格式的完整性，请将源文档中的每个段落标记为与下一个段落保持一致。

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## 步骤 4：附加文件

使用合并文档`AppendDocument`方法，确保保留源文档的格式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 步骤 5：保存合并文档

最后，将合并的文档保存到所需位置。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

## 结论

总之，Aspose.Words for .NET 简化了合并 Word 文档的任务，同时无缝保留了原始格式。此功能对于需要自动文档处理的应用程序至关重要。

## 常见问题解答

### Aspose.Words for .NET 可以合并不同格式的文档吗？
是的，它可以合并文档，无论其格式如何，并保持源格式。

### Aspose.Words for .NET 是否支持有效合并大型文档？
当然，它以最佳性能处理大型文档。

### Aspose.Words for .NET 有试用版吗？
是的，您可以下载免费试用版[这里](https://releases.aspose.com/).

### 如何获得 Aspose.Words for .NET 的技术支持？
技术支持可通过[Aspose.Words 论坛](https://forum.aspose.com/c/words/8).

### 我可以购买 Aspose.Words for .NET 的临时许可证吗？
是的，你可以获得临时驾照[这里](https://purchase.aspose.com/temporary-license/).