---
title: 保持源代码一致
linktitle: 保持源代码一致
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 合并和附加 Word 文档，同时将源内容与目标文档保存在一起。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/keep-source-together/
---

本教程将指导您完成使用 Aspose.Words for .NET 的“将源文件放在一起”功能的过程。此功能允许您合并和附加多个 Word 文档，同时将源文档的内容与目标文档的内容放在一起。 

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
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## 步骤 3：将源文档设置为显示在目标文档内容之后

为了确保源文档紧接着目标文档的内容出现，您需要设置`SectionStart`源文档第一节的属性`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## 步骤 4：为源文档设置“与下一篇保持一致”段落格式

为了使源文档中的段落保持在一起，您可以遍历文档中的每个段落并设置`KeepWithNext`财产`true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## 步骤 5：将源文档附加到目标文档

现在，您可以使用`AppendDocument`方法`Document`类。`ImportFormatMode.KeepSourceFormatting`参数确保在附加操作期间保留源格式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 步骤 6：保存最终文档

最后，使用启用“保持源文件在一起”功能的`Save`方法`Document`班级。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### 使用 Aspose.Words for .NET 保持源代码一致的示例源代码 

以下是使用 Aspose.Words for .NET 的 C# 中的“保持源在一起”功能的完整源代码：


```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	//将源文档设置为紧接着目标文档的内容出现。
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

就是这样！您已成功使用 Aspose.Words for .NET 实现了“保持源文件在一起”功能。最终文档将包含合并的内容，并将源文档中的段落保持在一起。