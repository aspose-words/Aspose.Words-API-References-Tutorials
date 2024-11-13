---
title: 使用 Google AI 模型
linktitle: 使用 Google AI 模型
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 和 Google AI 提升您的文档处理能力，轻松创建简洁的摘要。
type: docs
weight: 10
url: /zh/net/ai-powered-document-processing/working-with-google-ai-model/
---
## 介绍

在本文中，我们将逐步探索如何使用 Aspose.Words 和 Google 的 AI 模型来总结文档。无论您是想压缩冗长的报告还是从多个来源提取见解，我们都能满足您的需求。

## 先决条件

在深入实践部分之前，让我们先确保您已为成功做好准备。以下是您需要做的：

1. C# 和 .NET 的基础知识：熟悉编程概念将帮助您更好地掌握示例。
   
2.  Aspose.Words for .NET Library：这个功能强大的库可让您无缝创建和操作 Word 文档。您可以[点击下载](https://releases.aspose.com/words/net/).

3. Google AI 模型的 API 密钥：要使用 AI 模型，您需要一个 API 密钥进行身份验证。将其安全地存储在您的环境变量中。

4. 开发环境：确保您已设置好可用的 .NET 环境（Visual Studio 或任何其他 IDE）。

5. 示例文档：您需要示例 Word 文档（例如“Big document.docx”、“Document.docx”）来测试摘要。

现在我们已经介绍了基础知识，让我们深入研究代码！

## 导入包

要使用 Aspose.Words 并集成 Google AI 模型，您需要导入必要的命名空间。具体操作如下：

```csharp
using System.Text;
using Aspose.Words;
using System;
using Aspose.Words.AI;
```

现在您已经导入了必要的包，让我们逐步分解汇总文档的过程。

## 步骤 1：设置文档目录

在处理文档之前，我们需要指定文件所在的位置。此步骤对于确保 Aspose.Words 可以访问文档至关重要。

```csharp
//您的文档目录
string MyDir = "YOUR_DOCUMENT_DIRECTORY";
//你的 ArtifactsDir 目录
string ArtifactsDir = "YOUR_ARTIFACTS_DIRECTORY";
```

代替`"YOUR_DOCUMENT_DIRECTORY"`和`"YOUR_ARTIFACTS_DIRECTORY"`与您系统中存储文档的实际路径一致。这将作为阅读和保存文档的基准。

## 步骤 2：加载文档

接下来，我们需要加载要汇总的文档。在本例中，您将加载我们之前指定的两个文档。

```csharp
Document firstDoc = new Document(MyDir + "Big document.docx");
Document secondDoc = new Document(MyDir + "Document.docx");
```

这`Document` Aspose.Words 中的类允许您将 Word 文件加载到内存中。请确保文件名与目录中的实际文档相匹配，否则您将遇到文件未找到错误！

## 步骤 3：检索 API 密钥

要使用 AI 模型，您需要检索 API 密钥。这是您访问 Google AI 服务的通行证。

```csharp
string apiKey = Environment.GetEnvironmentVariable("API_KEY");
```

这行代码会获取您存储在环境变量中的 API 密钥。出于安全原因，最好将 API 密钥等敏感信息保留在代码之外。

## 步骤 4：创建 AI 模型实例

现在，是时候创建 AI 模型的实例了。在这里，您可以选择要使用的模型 - 在此示例中，我们选择 GPT-4 Mini 模型。

```csharp
IAiModelText model = (IAiModelText)AiModel.Create(AiModelType.Gpt4OMini).WithApiKey(apiKey);
```

此行设置了您将用于文档摘要的 AI 模型。请务必咨询[文档](https://reference.aspose.com/words/net/)了解不同模型及其功能的详细信息。

## 步骤 5：总结单个文档

让我们重点总结一下第一份文件。我们可以选择在这里获取一个简短的摘要。

```csharp
Document oneDocumentSummary = model.Summarize(firstDoc, new SummarizeOptions() { SummaryLength = SummaryLength.Short });
oneDocumentSummary.Save(ArtifactsDir + "AI.AiSummarize.One.docx");
```

在此步骤中，我们使用`Summarize`方法从 AI 模型实例中获取第一个文档的缩略图。摘要长度设置为短，但您可以根据需要自定义。最后，摘要文档将保存到您的工件目录中。

## 步骤 6：汇总多个文档

想要一次性汇总多个文档？Aspose.Words 也让这变得简单！

```csharp
Document multiDocumentSummary = model.Summarize(new Document[] { firstDoc, secondDoc }, new SummarizeOptions() { SummaryLength = SummaryLength.Long });
multiDocumentSummary.Save(ArtifactsDir + "AI.AiSummarize.Multi.docx");
```

在这里，我们称之为`Summarize`方法，但这次使用的是文档数组。这将为您提供一个较长的摘要，其中概括了两个文件的精髓。与之前一样，结果保存在指定的工件目录中。

## 结论

就这样！您已成功设置了一个使用 Aspose.Words for .NET 和 Google 的 AI 模型来汇总文档的环境。从加载文档到创建简明摘要，这些步骤提供了一种有效管理大量文本的简化方法。

## 常见问题解答

### 什么是 Aspose.Words？
Aspose.Words 是一个功能强大的库，可以使用 .NET 创建、修改和转换 Word 文档。

### 如何获取 Google AI 的 API 密钥？
您通常可以通过注册 Google Cloud 并启用必要的 API 服务来获取 API 密钥。

### 我可以一次汇总多个文件吗？
是的！如示例所示，您可以将文档数组传递给摘要方法。

### 我可以创建哪些类型的摘要？
您可以根据需要选择简短、中期或长篇摘要。

### 在哪里可以找到更多 Aspose.Words 资源？
查看[文档](https://reference.aspose.com/words/net/)以获取更多示例和指导。
