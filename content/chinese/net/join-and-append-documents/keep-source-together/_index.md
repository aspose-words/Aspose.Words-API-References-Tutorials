---
title: 将源代码放在一起
linktitle: 将源代码放在一起
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 加入和附加 Word 文档，同时将源内容与目标文档保留在一起。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/keep-source-together/
---

本教程将指导您完成使用 Aspose.Words for .NET 的“保持源代码在一起”功能的过程。此功能允许您加入和追加多个 Word 文档，同时将源文档的内容与目标文档的内容保留在一起。 

## 先决条件

在开始之前，请确保您具备以下条件：

1. Aspose.Words for .NET 已安装。您可以从 Aspose 网站下载它或通过 NuGet 安装它。
2. Visual Studio 或任何其他 C# 开发环境。

## 第 1 步：初始化文档目录

首先，您需要设置文档目录的路径。修改值`dataDir`变量到您的文档所在的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：加载源文档和目标文档

接下来，您需要使用 Aspose.Words 加载源文档和目标文档。`Document`班级。更新文件名`Document`根据您的文档名称构造函数。

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## 步骤 3：将源文档设置为显示在目标文档内容之后

为了确保源文档紧跟在目标文档内容之后出现，您需要设置`SectionStart`源文档中第一部分的属性`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## 步骤 4：为源文档设置“与下一个保持一致”段落格式

要将源文档中的段落保留在一起，您可以迭代文档中的每个段落并设置`KeepWithNext`财产给`true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## 步骤 5：将源文档附加到目标文档

现在，您可以使用以下命令将源文档附加到目标文档`AppendDocument`的方法`Document`班级。这`ImportFormatMode.KeepSourceFormatting`参数确保在追加操作期间保留源格式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 第 6 步：保存最终文档

最后，使用启用的“将源保持在一起”功能保存合并的文档`Save`的方法`Document`班级。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### 使用 Aspose.Words for .NET 将源代码保持在一起的示例源代码 

以下是使用 Aspose.Words for .NET 在 C# 中实现“保持源代码在一起”功能的完整源代码：


```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	//将源文档设置为直接显示在目标文档内容之后。
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

就是这样！您已使用 Aspose.Words for .NET 成功实现了“保持源代码在一起”功能。最终文档将包含与源文档中的段落合并在一起的合并内容。