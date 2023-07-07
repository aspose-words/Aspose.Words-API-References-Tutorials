---
title: 比较是否相等
linktitle: 比较是否相等
second_title: Aspose.Words for .NET API 参考
description: 分步指南解释 Aspose.Words for .NET 的 Compare for Equals 功能的 C# 源代码。
type: docs
weight: 10
url: /zh/net/compare-documents/compare-for-equal/
---

在本教程中，我们将引导您了解如何将“比较等于”功能与 Aspose.Words for .NET 结合使用。请按照以下步骤了解源代码并应用更改。

## 第1步：文档比较

首先，加载两个文档进行比较。在此示例中，我们将使用`Clone()`方法创建原始文档的副本。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document docA = new Document(dataDir + "Document.docx");
Document docB = docA.Clone();
```

## 第2步：文档比较

我们现在将使用`Compare()`比较两个文档的方法。该方法将标记原始文档中的更改。就是这样：

```csharp
//比较文档
docA.Compare(docB, "user", DateTime.Now);

//检查文件是否相同
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are identical": "Documents are not identical");
```

### 使用 Aspose.Words for .NET 进行比较相等的示例源代码

以下是 Aspose.Words for .NET 的比较等于功能的完整源代码：

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();
	
	// DocA 现在包含作为修订版的更改。
	docA.Compare(docB, "user", DateTime.Now);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

通过此代码，您将能够使用 Aspose.Words for .NET 比较两个文档并确定它们是否相同。

