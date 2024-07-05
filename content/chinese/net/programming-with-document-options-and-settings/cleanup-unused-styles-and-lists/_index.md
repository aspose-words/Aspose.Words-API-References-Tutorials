---
title: 清理未使用的样式和列表
linktitle: 清理未使用的样式和列表
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 清理文档中未使用的样式和列表的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-document-options-and-settings/cleanup-unused-styles-and-lists/
---

在本教程中，我们将引导您完成 C# 源代码，以使用 Aspose.Words for .NET 清理未使用的样式和列表。此功能允许您删除文档中未使用的样式和列表。

## 步骤 1：项目设置

首先，在您最喜欢的 IDE 中创建一个新的 C# 项目。确保您的项目中引用了 Aspose.Words for .NET 库。

## 步骤 2：加载文档

在此步骤中，我们将加载包含要清理的未使用样式和列表的 Word 文档。使用以下代码加载文档：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Unused styles.docx");
```

代替`"YOUR DOCUMENTS DIRECTORY"`与文档所在目录的实际路径一致。

## 步骤 3：清洁前清点款式和清单

在清理之前，我们将计算文档中存在的样式和列表的数量。使用以下代码显示计数器：

```csharp
Console.WriteLine($"Number of styles before cleaning: {doc.Styles.Count}\n" +
$"Number of lists before cleaning: {doc.Lists.Count}");
```

这些说明显示了清理之前文档中存在的样式和列表的数量。

## 步骤 4：清理未使用的样式和列表

现在让我们从文档中清理未使用的样式和列表。使用以下代码执行清理：

```csharp
CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
doc. Cleanup(cleanupOptions);
```

此代码使用指定的选项从文档中清除未使用的样式和列表。在此示例中，我们启用了`UnusedStyles`删除未使用的样式并禁用`UnusedLists`即使不使用列表也可以选择保留它们。

## 步骤 5：清点清洁后的款式和清单

完成清理后，我们将再次计数样式和列表以检查它们是否已折叠。使用以下代码显示新的计数器：

```csharp
Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
				  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
```

这些说明显示了清洁后剩余的样式和列表的数量。

### 使用 Aspose.Words for .NET 清理未使用的样式和列表的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Unused styles.docx");

	//结合内置样式，该文档现在有八种样式。
	//当文档中有任何文本时，自定义样式将被标记为“已使用”
	//格式化为该样式。这意味着我们添加的 4 种样式目前未使用。
	Console.WriteLine($"Count of styles before Cleanup: {doc.Styles.Count}\n" +
					  $"Count of lists before Cleanup: {doc.Lists.Count}");

	//根据给定的 CleanupOptions 清除文档中未使用的样式和列表。
	CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
	doc.Cleanup(cleanupOptions);

	Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
					  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
    
```

确保在`dataDir`多变的。

现在，您已经了解了如何使用 Aspose.Words for .NET 从文档中清除未使用的样式和列表。通过遵循本教程中提供的分步指南，您可以轻松地将此功能应用于您自己的文档。

