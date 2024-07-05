---
title: 更新页面布局
linktitle: 更新页面布局
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 合并和附加 Word 文档时更新页面布局。
type: docs
weight: 10
url: /zh/net/join-and-append-documents/update-page-layout/
---

本教程将指导您完成使用 Aspose.Words for .NET 的更新页面布局功能的过程。此功能可确保在合并和附加 Word 文档时正确更新页面布局。

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
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 步骤 3：更新目标文档的页面布局

为了确保在附加源文档之前正确更新页面布局，您可以调用`UpdatePageLayout`目标文档上的方法。

```csharp
dstDoc.UpdatePageLayout();
```

## 步骤 4：将源文档附加到目标文档

现在，您可以使用`AppendDocument`方法`Document`类。`ImportFormatMode.KeepSourceFormatting`参数确保在附加操作期间保留源格式。

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 步骤 5：再次更新页面布局

附加源文档后，您需要调用`UpdatePageLayout`方法，以确保附加操作后所做的任何更改都反映在呈现的输出中。

```csharp
dstDoc.UpdatePageLayout();
```

## 步骤 6：保存最终文档

最后，使用启用了“更新页面布局”功能的`Save`方法`Document`班级。

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

### 使用 Aspose.Words for .NET 更新页面布局的示例源代码

以下是使用 Aspose.Words for .NET 的 C# 中的“更新页面布局”功能的完整源代码：

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//如果目标文档呈现为 PDF、图像等。
	//或在源文档之前调用 UpdatePageLayout。附加到源文档，
	//那么之后所做的任何更改都不会反映在渲染的输出中
	dstDoc.UpdatePageLayout();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	//为了将更改更新到呈现的输出，必须再次调用 UpdatePageLayout。
	//如果没有再次调用，附加的文档将不会出现在下一次渲染的输出中。
	dstDoc.UpdatePageLayout();
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

就是这样！您已成功使用 Aspose.Words for .NET 实现更新页面布局功能。最终文档将包含合并的内容，并且页面布局已正确更新。