---
title: 比较 Word 文档中的选项
linktitle: 比较 Word 文档中的选项
second_title: Aspose.Words 文档处理 API
description: 分步指南解释使用 Aspose.Words for .NET 在 Word 文档功能中比较选项的 C# 源代码。
type: docs
weight: 10
url: /zh/net/compare-documents/compare-options/
---
在本教程中，我们将解释如何通过 Aspose.Words for .NET 使用 Word 文档中的比较选项功能。请按照以下步骤了解源代码并应用更改。

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

## 结论

在本教程中，我们学习了如何在比较两个文档时使用 Aspose.Words for .NET 中的比较选项来自定义比较过程。通过指定不同的选项，您可以忽略特定元素并使比较过程更加灵活。此功能使您可以更好地控制比较过程，并根据您的具体要求进行定制。 Aspose.Words for .NET 提供强大的文档比较功能，可以轻松识别文档之间的差异，同时根据需要忽略某些元素。

### 常见问题解答

#### 问：在 Aspose.Words for .NET 中使用比较选项的目的是什么？

答：Aspose.Words for .NET 中的比较选项允许您在比较两个文档时自定义比较过程。使用这些选项，您可以指定在比较过程中忽略哪些元素，例如格式更改、页眉和页脚、表格、字段、注释、文本框和脚注。

#### 问：如何在 Aspose.Words for .NET 中使用比较选项？

答：要在 Aspose.Words for .NET 中使用比较选项，请按照下列步骤操作：
1. 将要比较的两个文档加载到单独的 Document 对象中。
2. 使用`Clone()`方法创建原始文档的副本。
3. 创建一个`CompareOptions`对象并设置其属性来自定义比较过程。您可以指定在比较过程中忽略哪些元素。
4. 使用`Compare()`方法在其中一个文档上并传递另一个文档和`CompareOptions`对象作为参数。该方法将根据指定的选项对文档进行比较，并标记原始文档中的更改。
5. 检查`Revisions`原始文档的属性。如果计数为零，则意味着考虑到指定的选项，文档是相同的。

#### 问：CompareOptions 中有哪些常用选项？

答：CompareOptions 中可用的常见选项包括：
- `IgnoreFormatting`：忽略格式更改。
- `IgnoreHeadersAndFooters`：忽略页眉和页脚的更改。
- `IgnoreCaseChanges`：忽略大小写更改（大写/小写）。
- `IgnoreTables`：忽略表中的更改。
- `IgnoreFields`：忽略字段的变化。
- `IgnoreComments`：忽略注释中的更改。
- `IgnoreTextboxes`：忽略文本框中的更改。
- `IgnoreFootnotes`：忽略脚注的更改。

#### 问：在文档比较过程中，我可以对特定元素使用自定义选项吗？

答：是的，您可以在文档比较过程中对特定元素使用自定义选项。通过设置属性`CompareOptions`相应地，您可以选择在比较过程中忽略哪些元素以及考虑哪些元素。