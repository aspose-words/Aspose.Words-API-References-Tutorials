---
title: 不同的页面设置
linktitle: 不同的页面设置
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 附加具有不同页面设置设置的文档。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/different-page-setup/
---

本教程介绍如何使用 Aspose.Words for .NET 将具有不同页面设置设置的文档附加到另一个文档。提供的源代码演示了如何为源文档和目标文档设置不同的页面设置并确保正确的连续性和编号。

## 第 1 步：设置项目

确保您具备以下先决条件：

- 已安装 Aspose.Words for .NET 库。您可以从以下位置下载：[Aspose.Releases]https://releases.aspose.com/words/net/ 或使用 NuGet 包管理器来安装它。
- 源文档和目标文档所在的文档目录路径。

## 步骤 2：打开源文档和目标文档

使用以下命令打开源文档和目标文档`Document`类构造函数。代替`"YOUR DOCUMENT DIRECTORY"`与文档目录的实际路径。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 步骤 3：设置源文档的页面设置

调整源文档的页面设置以确保正确的连续性和编号。在此示例中，我们将部分开始设置为`SectionStart.Continuous`并重新开始页码编号。我们还确保页面宽度、高度和方向与目标文档的最后一部分相匹配。

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## 步骤 4：修改段落格式

要保持正确的格式，请遍历源文档中的所有段落并设置`KeepWithNext`财产给`true`。这可确保段落在附加过程中保持在一起。

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## 步骤 5：将源文档附加到目标文档

使用`AppendDocument`目标文档的方法，将修改后的源文档附加到目标文档，并保留源格式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 步骤 6：保存目标文档

最后，使用以下命令保存修改后的目标文档`Save`的方法`Document`目的。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

这样就完成了使用 Aspose.Words for .NET 附加具有不同页面设置设置的文档的实现。

### 使用 Aspose.Words for .NET 进行不同页面设置的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//将源文档设置为在目标文档末尾后直接继续。
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	//在源文档的开头重新开始页码编号。
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	//为确保当源文档具有不同的页面设置设置时不会发生这种情况，请确保
	//目标文档最后一部分的设置是相同的。
	//如果源文档中还有后续的连续部分，
	//需要对这些部分重复此操作。
	srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
	srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
	srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
	//迭代源文档中的所有部分。
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```