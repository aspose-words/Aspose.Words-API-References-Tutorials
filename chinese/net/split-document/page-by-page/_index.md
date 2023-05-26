---
title: 一页一页
linktitle: 一页一页
second_title: Aspose.Words for .NET API 参考
description: 分步指南解释 Aspose.Words .NET 逐页功能的 C# 源代码
type: docs
weight: 10
url: /zh/net/split-document/page-by-page/
---

在本教程中，我们将向您介绍如何使用 Aspose.Words for .NET 的逐页功能将 Word 文档拆分为单独的页面。按照以下步骤了解源代码并获取每个页面的单独文档。

## 第 1 步：装入文档

首先，指定文档的目录并将文档加载到 Document 对象中。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## 第 2 步：按页划分文档

现在我们将遍历文档的每一页并将文档分成单独的页面。就是这样：

```csharp
int pageCount = doc. PageCount;

for (int page = 0; page < pageCount; page++)
{
//将每一页另存为单独的文档。
Document extractedPage = doc.ExtractPages(page, 1);
extractedPage.Save(dataDir + $"SplitDocument.PageParPage_{page + 1}.docx");
}
```

## 第 3 步：合并文档

为每个页面创建单独的文档后，您可以根据需要合并它们。就是这样：

```csharp
MergeDocuments();
```

### 使用 Aspose.Words for .NET 的逐页示例源代码

以下是 Aspose.Words for .NET 的逐页功能的完整源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Big document.docx");

	int pageCount = doc.PageCount;

	for (int page = 0; page < pageCount; page++)
	{
		//将每一页另存为单独的文档。
		Document extractedPage = doc.ExtractPages(page, 1);
		extractedPage.Save(dataDir + $"SplitDocument.PageByPage_{page + 1}.docx");
	}
	

	MergeDocuments();

```

使用此代码，您将能够使用 Aspose.Words for .NET 将 Word 文档拆分为单独的页面。如果需要，您还可以合并单独的文档。

