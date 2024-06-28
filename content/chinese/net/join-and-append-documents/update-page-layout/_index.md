---
title: 更新页面布局
linktitle: 更新页面布局
second_title: Aspose.Words 文档处理 API
description: 了解如何在使用 Aspose.Words for .NET 加入和附加 Word 文档时更新页面布局。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/update-page-layout/
---

本教程将指导您完成使用 Aspose.Words for .NET 的更新页面布局功能的过程。此功能可确保在加入和附加 Word 文档时正确更新页面布局。

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
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 步骤 3：更新目标文档的页面布局

为了确保在附加源文档之前正确更新页面布局，您可以调用`UpdatePageLayout`目标文档上的方法。

```csharp
dstDoc.UpdatePageLayout();
```

## 步骤 4：将源文档附加到目标文档

现在，您可以使用以下命令将源文档附加到目标文档`AppendDocument`的方法`Document`班级。这`ImportFormatMode.KeepSourceFormatting`参数确保在追加操作期间保留源格式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 第5步：再次更新页面布局

附加源文档后，您需要调用`UpdatePageLayout`再次在目标文档上调用方法，以确保追加操作后所做的任何更改都反映在渲染的输出中。

```csharp
dstDoc.UpdatePageLayout();
```

## 第 6 步：保存最终文档

最后，使用启用的更新页面布局功能保存合并的文档`Save`的方法`Document`班级。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

### 使用 Aspose.Words for .NET 更新页面布局的示例源代码

以下是使用 Aspose.Words for .NET 在 C# 中“更新页面布局”功能的完整源代码：

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//如果目标文档呈现为 PDF、图像等。
	//或在源文档之前调用 UpdatePageLayout。附上，
	//那么之后所做的任何更改都不会反映在渲染输出中
	dstDoc.UpdatePageLayout();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	//为了将更改更新到呈现的输出，必须再次调用 UpdatePageLayout。
	//如果不再调用，附加文档将不会出现在下一次渲染的输出中。
	dstDoc.UpdatePageLayout();
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

就是这样！您已使用 Aspose.Words for .NET 成功实现了更新页面布局功能。最终文档将包含合并的内容以及正确更新的页面布局。