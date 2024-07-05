---
title: 删除源页眉页脚
linktitle: 删除源页眉页脚
second_title: Aspose.Words 文档处理 API
description: 了解如何在使用 Aspose.Words for .NET 合并和附加 Word 文档时删除页眉和页脚。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/remove-source-headers-footers/
---

本教程将指导您完成使用 Aspose.Words for .NET 的“删除源页眉页脚”功能的过程。此功能允许您合并和附加 Word 文档，同时从源文档中删除页眉和页脚。

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

## 步骤 3：从源文档部分中删除页眉和页脚

要从源文档的每个部分中删除页眉和页脚，可以使用`foreach`循环并调用`ClearHeadersFooters`方法。

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## 步骤 4：禁用 HeadersFooters 的“LinkToPrevious”设置

即使清除了源文档中的页眉和页脚，仍有可能“LinkToPrevious”设置`HeadersFooters`仍然可以设置。为了避免此行为，您需要将其明确设置为`false`第一部分的`HeadersFooters`财产。

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## 步骤 5：将源文档附加到目标文档

现在，您可以使用`AppendDocument`方法`Document`类。`ImportFormatMode.KeepSourceFormatting`参数确保在附加操作期间保留源格式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 步骤 6：保存最终文档

最后，使用启用了“删除源页眉页脚”功能的按钮保存合并的文档`Save`方法`Document`班级。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

### 使用 Aspose.Words for .NET 删除源页眉页脚的示例源代码 

以下是使用 Aspose.Words for .NET 在 C# 中实现“删除源页眉页脚”功能的完整源代码：


```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//删除源文档中每个部分的页眉和页脚。
	foreach (Section section in srcDoc.Sections)
	{
		section.ClearHeadersFooters();
	}
	//即使从源文档中清除了页眉和页脚，“LinkToPrevious”设置
	//HeadersFooters 仍可设置。这将导致页眉和页脚从目标继续
	//文档。应将其设置为 false 以避免此行为。
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```
就是这样！您已成功使用 Aspose.Words for .NET 实现了“删除源页眉页脚”功能。最终文档将包含合并的内容，其中页眉和页脚已从源文档中删除。