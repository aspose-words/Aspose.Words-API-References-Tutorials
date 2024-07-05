---
title: 加入连续
linktitle: 加入连续
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 连续连接两个文档同时保留格式。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/join-continuous/
---

本教程讲解如何使用 Aspose.Words for .NET 连续连接两个文档。提供的源代码演示了如何将一个文档附加到另一个文档的末尾，同时保持原始格式。

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

## 步骤 3：设置连续部分开始

要使源文档紧接着目标文档的内容出现，请设置`SectionStart`源文档第一节的属性`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## 步骤 4：附加源文档

使用`AppendDocument`方法`Document`类。将导入格式模式设置为`ImportFormatMode.KeepSourceFormatting`保留源文档的原始样式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 步骤5：保存修改后的文档

最后，使用`Save`方法`Document`目的。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```

这样就完成了使用 Aspose.Words for .NET 连续连接两个文档的实现。

### 使用 Aspose.Words for .NET 进行 Join Continuous 的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//使文档直接出现在目标文档内容之后。
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	//使用在源文档中找到的原始样式附加源文档。
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```