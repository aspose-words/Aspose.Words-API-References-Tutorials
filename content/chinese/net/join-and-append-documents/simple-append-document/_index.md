---
title: 简单追加文档
linktitle: 简单追加文档
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 合并和附加具有保留格式的 Word 文档。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/simple-append-document/
---

本教程将指导您完成使用 Aspose.Words for .NET 的简单附加文档功能的过程。此功能允许您加入和附加 Word 文档，而无需其他选项。

## 先决条件

开始之前，请确保您已准备好以下物品：

1. 已安装 Aspose.Words for .NET。您可以从 Aspose 网站下载它或通过 NuGet 安装它。
2. Visual Studio 或任何其他 C# 开发环境。

## 步骤 1：初始化文档目录

首先，您需要设置文档目录的路径。修改`dataDir`变量为您的文档所在的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步骤 2：加载源文档和目标文档

接下来，您需要使用 Aspose.Words 加载源文档和目标文档`Document`类。更新`Document`根据您的文档名称构造函数。

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 步骤 3：将源文档附加到目标文档

现在，您可以使用`AppendDocument`方法`Document`类。`ImportFormatMode.KeepSourceFormatting`参数确保在附加操作期间保留源格式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 步骤 4：保存最终文档

最后，使用简单附加文档功能保存合并的文档`Save`方法`Document`班级。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

### 使用 Aspose.Words for .NET 的简单附加文档的示例源代码

以下是使用 Aspose.Words for .NET 的 C# 中的“简单附加文档”功能的完整源代码：

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//不使用任何额外选项将源文档附加到目标文档。
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

就是这样！您已成功使用 Aspose.Words for .NET 实现了简单附加文档功能。最终文档将包含合并的内容并保留源格式。