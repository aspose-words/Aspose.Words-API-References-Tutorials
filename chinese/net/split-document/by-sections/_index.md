---
title: 按章节
linktitle: 按章节
second_title: Aspose.Words for .NET API 参考
description: 通过完整的代码示例了解如何使用 Aspose.Words for .NET 将 Word 文档拆分为单独的部分。
type: docs
weight: 10
url: /zh/net/split-document/by-sections/
---

在本例中，我们将向您展示如何使用 Aspose.Words for .NET 的按部分功能将 Word 文档分成单独的部分。按照以下步骤了解源代码并获取每个部分的单独文档。

## 第 1 步：装入文档

首先，我们需要指定文档的目录并将文档加载到 Document 对象中。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## 第 2 步：将文档分成多个部分

现在我们将遍历文档的每个部分，并将文档分成更小的部分，逐节进行。方法如下：

```csharp
for (int i = 0; i < doc. Sections. Count; i++)
{
//将文档拆分成更小的部分，在本例中，按部分分隔。
Section section = doc.Sections[i].Clone();

Document newDoc = new Document();
newDoc.Sections.Clear();

Section newSection = (Section) newDoc.ImportNode(section, true);
newDoc.Sections.Add(newSection);

//将每个部分另存为单独的文档。
newDoc.Save(dataDir + $"SplitDocument.ParSections_{i}.docx");
}
```

### 使用 Aspose.Words for .NET 的 By Sections 示例源代码

以下是 Aspose.Words for .NET 的 By Sections 功能的完整源代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Big document.docx");

for (int i = 0; i < doc.Sections.Count; i++)
{
	//将文档拆分为更小的部分，在本例中，按部分拆分。
	Section section = doc.Sections[i].Clone();

	Document newDoc = new Document();
	newDoc.Sections.Clear();

	Section newSection = (Section) newDoc.ImportNode(section, true);
	newDoc.Sections.Add(newSection);

	//将每个部分另存为单独的文档。
	newDoc.Save(dataDir + $"SplitDocument.BySections_{i}.docx");
}
```

使用此代码，您将能够使用 Aspose.Words for .NET 将 Word 文档拆分为单独的部分。

现在您可以轻松地处理特定部分。

