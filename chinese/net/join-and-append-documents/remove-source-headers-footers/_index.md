---
title: 删除源页眉页脚
linktitle: 删除源页眉页脚
second_title: Aspose.Words for .NET API 参考
description: 了解如何在使用 Aspose.Words for .NET 加入和附加 Word 文档时删除页眉和页脚。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/remove-source-headers-footers/
---

本教程将指导您完成使用 Aspose.Words for .NET 的删除源页眉页脚功能的过程。此功能允许您加入和附加 Word 文档，同时从源文档中删除页眉和页脚。

## 先决条件

在开始之前，请确保您具备以下条件：

1. 安装了 Aspose.Words for .NET。您可以从 Aspose 网站下载它或通过 NuGet 安装它。
2. Visual Studio 或任何其他 C# 开发环境。

## 第 1 步：初始化文档目录

首先，您需要设置文档目录的路径。修改值`dataDir`变量到您的文档所在的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：加载源文档和目标文档

接下来，您需要使用 Aspose.Words 加载源文档和目标文档`Document`班级。更新文件名在`Document`根据您的文档名称构造函数。

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 第 3 步：从源文档节中删除页眉和页脚

要从源文档的每个部分中删除页眉和页脚，您可以使用`foreach`循环并调用`ClearHeadersFooters`方法。

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## 第 4 步：禁用 HeadersFooters 的“LinkToPrevious”设置

即使从源文档中清除了页眉和页脚之后，“LinkToPrevious”设置也有可能`HeadersFooters`仍然可以设置。为避免这种行为，您需要将其显式设置为`false`对于第一部分的`HeadersFooters`财产。

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## 第 5 步：将源文档附加到目标文档

现在，您可以使用`AppendDocument`的方法`Document`班级。这`ImportFormatMode.KeepSourceFormatting`参数确保在追加操作期间保留源格式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 第 6 步：保存最终文件

最后，使用启用的删除源页眉页脚功能保存合并的文档`Save`的方法`Document`班级。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

### 使用 Aspose.Words for .NET 删除源页眉页脚的示例源代码 

以下是使用 Aspose.Words for .NET 在 C# 中“删除源页眉页脚”功能的完整源代码：


```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//从源文档的每个部分中删除页眉和页脚。
	foreach (Section section in srcDoc.Sections)
	{
		section.ClearHeadersFooters();
	}
	//即使在从源文档中清除了页眉和页脚之后，“LinkToPrevious”设置
	//仍然可以设置 HeadersFooters。这将导致页眉和页脚从目的地继续
	//文档。这应该设置为 false 以避免这种行为。
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```
就是这样！您已经使用 Aspose.Words for .NET 成功实现了删除源页眉页脚功能。最终文档将包含从源文档中删除页眉和页脚的合并内容。