---
title: 取消链接页眉页脚
linktitle: 取消链接页眉页脚
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 加入和附加 Word 文档，同时取消链接页眉和页脚。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/unlink-headers-footers/
---

本教程将指导您完成使用 Aspose.Words for .NET 的 Unlink Headers Footers 功能的过程。此功能允许您加入和附加 Word 文档，同时取消链接源文档的页眉和页脚。

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

## 第 3 步：取消链接源文档中的页眉和页脚

要取消源文档中的页眉和页脚与目标文档的页眉和页脚的链接，您需要设置`LinkToPrevious`的财产`HeadersFooters`源文档第一部分中的集合`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## 第 4 步：将源文档附加到目标文档

现在，您可以使用`AppendDocument`的方法`Document`班级。这`ImportFormatMode.KeepSourceFormatting`参数确保在追加操作期间保留源格式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 第 5 步：保存最终文件

最后，使用启用的 Unlink Headers Footers 功能保存合并文档`Save`的方法`Document`班级。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

### 使用 Aspose.Words for .NET 取消链接页眉页脚的示例源代码

下面是在 C# 中使用 Aspose.Words for .NET 的“Unlink Headers Footers”功能的完整源代码：

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//取消链接源文档中的页眉和页脚以停止此操作
	//从继续目标文档的页眉和页脚。
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

就是这样！您已经使用 Aspose.Words for .NET 成功实现了 Unlink Headers Footers 功能。最终文档将包含合并后的内容，其中源文档的页眉和页脚未与目标文档链接。