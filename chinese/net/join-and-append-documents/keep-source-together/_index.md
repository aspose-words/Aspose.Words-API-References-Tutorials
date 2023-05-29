---
title: 保持源代码在一起
linktitle: 保持源代码在一起
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 加入和附加 Word 文档，同时将源内容与目标文档保持在一起。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/keep-source-together/
---

本教程将指导您完成使用 Aspose.Words for .NET 的 Keep Source Together 功能的过程。此功能允许您加入和附加多个 Word 文档，同时将源文档的内容与目标文档的内容保持在一起。 

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
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## 第 3 步：将源文档设置为在目标文档的内容之后显示

要确保源文档紧跟在目标文档的内容之后，您需要设置`SectionStart`源文档中第一节的属性`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## 第 4 步：为源文档设置“与下一个保持一致”段落格式

要将源文档中的段落保持在一起，您可以遍历文档中的每个段落并设置`KeepWithNext`财产给`true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## 第 5 步：将源文档附加到目标文档

现在，您可以使用`AppendDocument`的方法`Document`班级。这`ImportFormatMode.KeepSourceFormatting`参数确保在追加操作期间保留源格式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 第 6 步：保存最终文件

最后，使用启用的“Keep Source Together”功能保存合并的文档`Save`的方法`Document`班级。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### 使用 Aspose.Words for .NET 的 Keep Source Together 示例源代码 

下面是使用 Aspose.Words for .NET 的 C# 中“Keep Source Together”功能的完整源代码：


```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	//将源文档设置为紧跟在目标文档的内容之后。
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

就是这样！您已经使用 Aspose.Words for .NET 成功实现了 Keep Source Together 功能。最终文档将包含合并后的内容，源文档中的段落保持在一起。