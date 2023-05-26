---
title: 清理重复样式
linktitle: 清理重复样式
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 清理文档中重复样式的分步指南。包括完整的源代码。
type: docs
weight: 10
url: /zh/net/programming-with-document-options-and-settings/cleanup-duplicate-style/
---

在本教程中，我们将逐步引导您通过 C# 源代码使用 Aspose.Words for .NET 清理重复样式。此功能有助于从文档中删除重复的样式。

## 第 1 步：项目设置

首先，在您喜欢的 IDE 中创建一个新的 C# 项目。确保在您的项目中引用了 Aspose.Words for .NET 库。

## 第 2 步：装入文档

在此步骤中，我们将加载要清理的 Word 文档。使用以下代码加载文档：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

代替`"YOUR DOCUMENTS DIRECTORY"`使用文档所在目录的实际路径。

## 第 3 步：清洁前清点样式

在继续清理之前，我们将计算文档中存在的样式数。使用以下代码显示样式计数：

```csharp
Console.WriteLine(doc.Styles.Count);
```

此语句显示文档中存在的样式数。

## 第 4 步：清理重复样式

现在让我们从文档中清除重复的样式。使用以下代码执行清理：

```csharp
CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
doc. Cleanup(options);
```

此代码使用指定的选项从文档中清除重复的样式。在这个例子中，我们启用了`DuplicateStyle`清理重复样式的选项。

## 第 5 步：清点后清点样式

清理完毕后，我们会再次统计款式数量，看看是否有所减少。使用以下代码显示新样式计数：

```csharp
Console.WriteLine(doc.Styles.Count);
doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");
```

此语句显示清理后剩余的样式数。

### 使用 Aspose.Words for .NET 清理重复样式的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	//清理前的样式计数。
	Console.WriteLine(doc.Styles.Count);

	//清除文档中的重复样式。
	CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
	doc.Cleanup(options);

	//清理后的样式数减少了。
	Console.WriteLine(doc.Styles.Count);

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");

```