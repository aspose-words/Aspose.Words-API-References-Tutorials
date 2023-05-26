---
title: 优化 Ms Word
linktitle: 优化 Ms Word
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 优化 MS Word 文档的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-document-options-and-settings/optimize-for-ms-word/
---

在本教程中，我们将引导您通过 C# 源代码使用 Aspose.Words for .NET 优化 MS Word 文档。此功能允许您针对特定版本的 MS Word 优化文档。

## 第 1 步：项目设置

首先，在您喜欢的 IDE 中创建一个新的 C# 项目。确保在您的项目中引用了 Aspose.Words for .NET 库。

## 第 2 步：装入文档

在此步骤中，我们将加载要优化的 Word 文档。使用以下代码加载文档：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

代替`"YOUR DOCUMENTS DIRECTORY"`使用文档所在目录的实际路径。

## 第 3 步：MS Word 优化

现在让我们针对特定版本的 MS Word 优化文档。使用以下代码执行优化：

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2016);
doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.OptimizeForMsWord.docx");
```

此代码告诉 Aspose.Words 为 MS Word 2016 优化文档。您可以替换`MsWordVersion.Word2016`使用要优化的特定版本的 MS Word。

### 使用 Aspose.Words for .NET 优化 Ms Word 的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2016);

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.OptimizeForMsWord.docx");
   
```

请务必在`dataDir`多变的。

您现在已经了解了如何使用 Aspose.Words for .NET 为特定版本的 MS Word 优化文档。按照本教程中提供的分步指南，您可以轻松地针对不同版本的 MS Word 优化您自己的文档。