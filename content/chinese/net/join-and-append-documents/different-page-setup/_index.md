---
title: 不同的页面设置
linktitle: 不同的页面设置
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 附加具有不同页面设置的文档。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/different-page-setup/
---

本教程讲解如何使用 Aspose.Words for .NET 将具有不同页面设置的文档附加到另一个文档。提供的源代码演示了如何为源文档和目标文档设置不同的页面设置，并确保正确的连续性和编号。

## 步骤 1：设置项目

确保您满足以下先决条件：

- 已安装 Aspose.Words for .NET 库。您可以从以下位置下载[Aspose.Releases]https://releases.aspose.com/words/net/ 或使用 NuGet 包管理器来安装。
- 源文档和目标文档所在的文档目录路径。

## 步骤 2：打开源文档和目标文档

使用打开源文档和目标文档`Document`类构造函数。替换`"YOUR DOCUMENT DIRECTORY"`使用您的文档目录的实际路径。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 步骤 3：设置源文档的页面设置

调整源文档的页面设置以确保正确的连续性和编号。在此示例中，我们将节开始设置为`SectionStart.Continuous`并重新开始页码编号。我们还确保页面宽度、高度和方向与目标文档的最后一节相匹配。

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## 步骤 4：修改段落格式

为了保持正确的格式，请遍历源文档中的所有段落并设置`KeepWithNext`财产`true`.这可确保段落在附加过程中保持在一起。

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## 步骤 5：将源文档附加到目标文档

使用`AppendDocument`方法将修改后的源文档附加到目标文档，并保留源格式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 步骤 6：保存目标文档

最后，使用`Save`方法`Document`目的。

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
	//将源文档设置为在目标文档结束后直接继续。
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	//从源文档的开始处重新开始页码编号。
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	//为了确保在源文档具有不同的页面设置时不会发生这种情况，请确保
	//目标文档的最后一部分的设置相同。
	//如果源文档中还有其他连续的部分，
	//对于这些部分，需要重复此操作。
	srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
	srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
	srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
	//遍历源文档中的所有部分。
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```