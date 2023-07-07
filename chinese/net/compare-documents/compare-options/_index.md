---
title: 比较选项
linktitle: 比较选项
second_title: Aspose.Words for .NET API 参考
description: 分步指南解释 Aspose.Words for .NET 的比较选项功能的 C# 源代码。
type: docs
weight: 10
url: /zh/net/compare-documents/compare-options/
---

在本教程中，我们将解释如何将“比较选项”功能与 Aspose.Words for .NET 结合使用。请按照以下步骤了解源代码并应用更改。

## 第 1 步：将文档与自定义选项进行比较

首先，加载两个文档进行比较。在此示例中，我们将使用`Clone()`方法创建原始文档的副本。就是这样：

```csharp
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();
```

## 第 2 步：配置比较选项

我们现在将通过创建一个来配置比较选项`CompareOptions`对象并根据需要设置各种属性。就是这样：

```csharp
CompareOptions options = new CompareOptions
{
IgnoreFormatting = true,
IgnoreHeadersAndFooters = true,
IgnoreCaseChanges = true,
IgnoreTables = true,
IgnoreFields = true,
IgnoreComments = true,
IgnoreTextboxes=true,
IgnoreFootnotes=true
};
```

## 第 3 步：将文档与自定义选项进行比较

我们现在将使用`Compare()`方法传递自定义选项来比较两个文档。该方法将标记原始文档中的更改。就是这样：

```csharp
//将文档与自定义选项进行比较
docA.Compare(docB, "user", DateTime.Now, options);

//检查文件是否相同
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal": "Documents are not equal");
```

### 使用 Aspose.Words for .NET 的比较选项的示例源代码

以下是 Aspose.Words for .NET 的比较选项功能的完整源代码：

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();

	CompareOptions options = new CompareOptions
	{
		IgnoreFormatting = true,
		IgnoreHeadersAndFooters = true,
		IgnoreCaseChanges = true,
		IgnoreTables = true,
		IgnoreFields = true,
		IgnoreComments = true,
		IgnoreTextboxes = true,
		IgnoreFootnotes = true
	};

	docA.Compare(docB, "user", DateTime.Now, options);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

通过此代码，您可以使用自定义选项来比较两个文档，以在与 Aspose.Words for .NET 进行比较时忽略特定元素。

