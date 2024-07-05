---
title: 删除自定义文档属性
linktitle: 删除自定义文档属性
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 从文档中删除自定义属性的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-document-properties/remove-custom-document-properties/
---

在本教程中，我们将引导您完成使用 Aspose.Words for .NET 从文档中删除自定义属性的 C# 源代码。此功能允许您从文档中删除特定的自定义属性。

## 步骤 1：项目设置

首先，在您最喜欢的 IDE 中创建一个新的 C# 项目。确保您的项目中引用了 Aspose.Words for .NET 库。

## 步骤 2：加载文档

在此步骤中，我们将加载要从中删除自定义属性的 Word 文档。使用以下代码加载文档：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

代替`"YOUR DOCUMENTS DIRECTORY"`与文档所在目录的实际路径一致。

## 步骤 3：删除自定义属性

现在让我们从文档中删除特定的自定义属性。使用以下代码：

```csharp
doc.CustomDocumentProperties.Remove("Authorized Date");
```

此代码从文档中删除“授权日期”自定义属性。您可以将“授权日期”替换为要删除的自定义属性的名称。

### 使用 Aspose.Words for .NET 删除自定义文档属性的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	doc.CustomDocumentProperties.Remove("Authorized Date");
	
```

确保在`dataDir`多变的。

现在您已经了解了如何使用 Aspose.Words for .NET 从文档中删除自定义属性。按照本教程中提供的分步指南，您可以轻松地从自己的文档中删除自定义属性。