---
title: 比较相等
linktitle: 比较相等
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 解释 Compare for Equals 功能的 C# 源代码的分步指南。
type: docs
weight: 10
url: /zh/net/compare-documents/compare-for-equal/
---

在本教程中，我们将带您了解如何使用 Aspose.Words for .NET 的比较相等功能。按照以下步骤了解源代码并应用更改。

## 第 1 步：文件比较

首先，加载两个文档进行比较。在这个例子中，我们将使用`Clone()`方法来创建原始文档的副本。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document docA = new Document(dataDir + "Document.docx");
Document docB = docA.Clone();
```

## 第二步：文件比较

我们现在将使用`Compare()`比较两个文件的方法。此方法将标记原始文档中的更改。就是这样：

```csharp
//比较文件
docA.Compare(docB, "user", DateTime.Now);

//检查文件是否相等
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are identical": "Documents are not identical");
```

### 使用 Aspose.Words for .NET 的 Compare For Equal 示例源代码

以下是 Aspose.Words for .NET 的“比较等于”功能的完整源代码：

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();
	
	// DocA 现在包含作为修订的更改。
	docA.Compare(docB, "user", DateTime.Now);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

使用此代码，您将能够使用 Aspose.Words for .NET 比较两个文档并确定它们是否相同。

