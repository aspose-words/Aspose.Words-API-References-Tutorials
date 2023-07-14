---
title: 添加自定义文档属性
linktitle: 添加自定义文档属性
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 将自定义属性添加到文档的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-document-properties/add-custom-document-properties/
---

在本教程中，我们将引导您完成 C# 源代码，以使用 Aspose.Words for .NET 将自定义属性添加到文档中。此功能允许您向文档添加自定义信息。

## 第 1 步：项目设置

首先，在您最喜欢的 IDE 中创建一个新的 C# 项目。确保您的项目中引用了 Aspose.Words for .NET 库。

## 第 2 步：加载文档

在此步骤中，我们将加载要添加自定义属性的 Word 文档。使用以下代码加载文档：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

代替`"YOUR DOCUMENTS DIRECTORY"`与文档所在目录的实际路径。

## 第 3 步：添加自定义属性

现在让我们向文档添加自定义属性。使用以下代码添加属性：

```csharp
CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;

if (customDocumentProperties["Authorized"] != null) return;

customDocumentProperties.Add("Authorized", true);
customDocumentProperties.Add("Authorized By", "John Smith");
customDocumentProperties.Add("Authorized Date", DateTime.Today);
customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
customDocumentProperties.Add("Authorized Amount", 123.45);
```

此代码首先检查自定义属性中是否已存在“Authorized”属性。如果存在，则进程被中断。否则，自定义属性将添加到文档中。

### 使用 Aspose.Words for .NET 添加自定义文档属性的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");

	CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;
	
	if (customDocumentProperties["Authorized"] != null) return;
	
	customDocumentProperties.Add("Authorized", true);
	customDocumentProperties.Add("Authorized By", "John Smith");
	customDocumentProperties.Add("Authorized Date", DateTime.Today);
	customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
	customDocumentProperties.Add("Authorized Amount", 123.45);

```

请务必在中指定正确的文档路径`dataDir`多变的。

您现在已经了解了如何使用 Aspose.Words for .NET 将自定义属性添加到文档中。通过遵循本教程中提供的分步指南，您可以轻松地将自己的自定义属性添加到文档中。