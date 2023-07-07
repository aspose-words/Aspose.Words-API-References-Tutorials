---
title: 重新开始页码编号
linktitle: 重新开始页码编号
second_title: Aspose.Words for .NET API 参考
description: 了解如何在使用 Aspose.Words for .NET 加入和附加 Word 文档时重新开始页码编号。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/restart-page-numbering/
---

本教程将指导您完成使用 Aspose.Words for .NET 的重新启动页码功能的过程。此功能允许您在源文档中重新启动页码编号的同时加入和附加 Word 文档。

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

接下来，您需要使用 Aspose.Words 加载源文档和目标文档`Document`班级。更新文件名`Document`根据您的文档名称构造函数。

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 步骤 3：设置源文档以重新开始页码编号

要在源文档中重新开始页码编号，您需要设置`SectionStart`源文档中第一部分的属性`SectionStart.NewPage`并设置`RestartPageNumbering`财产给`true`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
```

## 步骤 4：将源文档附加到目标文档

现在，您可以使用以下命令将源文档附加到目标文档`AppendDocument`的方法`Document`班级。这`ImportFormatMode.KeepSourceFormatting`参数确保在追加操作期间保留源格式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 第 5 步：保存最终文档

最后，使用启用重新启动页码编号功能保存合并的文档`Save`的方法`Document`班级。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

### 使用 Aspose.Words for .NET 重新启动页码的示例源代码

以下是使用 Aspose.Words for .NET 在 C# 中实现“重新启动页码编号”功能的完整源代码：
 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

就是这样！您已使用 Aspose.Words for .NET 成功实现了重新启动页码编号功能。最终文档将包含合并的内容，并在源文档中重新启动页码。