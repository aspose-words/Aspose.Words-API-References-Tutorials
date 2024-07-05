---
title: 智能风格行为
linktitle: 智能风格行为
second_title: Aspose.Words 文档处理 API
description: 了解如何在使用 Aspose.Words for .NET 连接和附加 Word 文档时保持智能样式行为。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/smart-style-behavior/
---

本教程将指导您完成使用 Aspose.Words for .NET 的智能样式行为功能的过程。此功能允许您合并和附加 Word 文档，同时保持智能样式行为。

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

## 步骤 3：在目标文档中插入分页符

为了确保附加的内容出现在目标文档的新页面上，您可以使用`DocumentBuilder`.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## 步骤 4：设置智能样式行为选项

要在附加操作期间启用智能样式行为，您需要创建一个实例`ImportFormatOptions`并设置`SmartStyleBehavior`财产`true`.

```csharp
ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
```

## 步骤 5：将源文档附加到目标文档

现在，您可以使用`InsertDocument`方法`DocumentBuilder`类。使用`ImportFormatMode.UseDestinationStyles`参数并传递`ImportFormatOptions`对象来保持智能风格行为。

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## 步骤 6：保存最终文档

最后，使用启用了“智能样式行为”功能的`Save`方法`Document`班级。

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

### 使用 Aspose.Words for .NET 的智能样式行为示例源代码

以下是使用 Aspose.Words for .NET 的 C# 中的“智能样式行为”功能的完整源代码：
 
```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
	builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

就是这样！您已成功使用 Aspose.Words for .NET 实现智能样式行为功能。最终文档将包含合并的内容并保留智能样式行为。