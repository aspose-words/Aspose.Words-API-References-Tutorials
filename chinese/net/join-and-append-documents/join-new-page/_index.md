---
title: 加入新页面
linktitle: 加入新页面
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在保留格式的同时在新页面上加入两个文档。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/join-new-page/
---

本教程解释了如何使用 Aspose.Words for .NET 在新页面上加入两个文档。提供的源代码演示了如何在新页面上开始附加文档时将文档附加到另一个文档的末尾。

## 第 1 步：设置项目

确保您具有以下先决条件：

- 安装了 Aspose.Words for .NET 库。您可以从 Aspose 官方网站下载或使用 NuGet 包管理器安装它。
- 源文档和目标文档所在的文档目录路径。

## 第 2 步：打开源文档和目标文档

使用打开源文档和目标文档`Document`类构造函数。代替`"YOUR DOCUMENT DIRECTORY"`使用文档目录的实际路径。

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 第 3 步：设置新页面部分开始

要在新页面上开始附加文档，请设置`SectionStart`源文档中第一节的属性`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## 第 4 步：附加源文档

使用将源文档附加到目标文档`AppendDocument`的方法`Document`班级。设置导入格式模式为`ImportFormatMode.KeepSourceFormatting`保留源文档中的原始样式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 第五步：保存修改后的文件

最后，使用保存修改后的目标文档`Save`的方法`Document`目的。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```

这样就完成了使用 Aspose.Words for .NET 在新页面上连接两个文档的实现。

### 使用 Aspose.Words for .NET 加入新页面的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//将附加文档设置为在新页面上开始。
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	//使用在源文档中找到的原始样式附加源文档。
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```