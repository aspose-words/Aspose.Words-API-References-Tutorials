---
title: 显示语法和拼写错误
linktitle: 显示语法和拼写错误
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 在文档中显示语法和拼写错误的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-document-options-and-settings/show-grammatical-and-spelling-errors/
---

在本教程中，我们将引导您了解 C# 源代码，以便使用 Aspose.Words for .NET 显示语法和拼写错误。此功能允许您查看文档中的语法和拼写错误。

## 步骤 1：项目设置

首先，在您最喜欢的 IDE 中创建一个新的 C# 项目。确保您的项目中引用了 Aspose.Words for .NET 库。

## 步骤 2：加载文档

在此步骤中，我们将加载要显示语法和拼写错误的 Word 文档。使用以下代码加载文档：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

代替`"YOUR DOCUMENTS DIRECTORY"`与文档所在目录的实际路径一致。

## 步骤 3：启用错误显示

现在我们将启用文档中语法和拼写错误的显示。使用以下代码启用错误显示：

```csharp
doc. ShowGrammaticalErrors = true;
doc. ShowSpellingErrors = true;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");
```

此代码可以显示语法错误（`ShowGrammaticalErrors`）和拼写错误（`ShowSpellingErrors`) 在文档中。

### 使用 Aspose.Words for .NET 显示语法和拼写错误的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.ShowGrammaticalErrors = true;
	doc.ShowSpellingErrors = true;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");

```

确保在`dataDir`多变的。

现在，您已经了解了如何使用 Aspose.Words for .NET 在文档中显示语法和拼写错误。按照本教程中提供的分步指南，您可以轻松地在自己的文档中启用此功能。