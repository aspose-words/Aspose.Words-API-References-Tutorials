---
title: 删除个人信息
linktitle: 删除个人信息
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 从文档中删除个人信息的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-document-properties/remove-personal-information/
---

在本教程中，我们将引导您通过 C# 源代码使用 Aspose.Words for .NET 从文档中删除个人信息。此功能允许您从文档中删除敏感的个人信息，例如作者身份数据。

## 第 1 步：项目设置

首先，在您喜欢的 IDE 中创建一个新的 C# 项目。确保在您的项目中引用了 Aspose.Words for .NET 库。

## 第 2 步：装入文档

在此步骤中，我们将上传要从中删除个人信息的 Word 文档。使用以下代码加载文档：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };
```

代替`"YOUR DOCUMENTS DIRECTORY"`使用文档所在目录的实际路径。

## 第三步：删除个人信息

现在我们将通过设置`RemovePersonalInformation`财产给`true`.使用以下代码：

```csharp
doc.RemovePersonalInformation = true;
```

此代码激活删除文档中的个人信息。

## 第 4 步：保存文档

最后，我们将保存已删除个人信息的文档。使用以下代码：

```csharp
doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
```

此代码将删除了个人信息的文档保存到新文件中。

### 使用 Aspose.Words for .NET 删除个人信息的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };

	doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
	
```

请务必在`dataDir`多变的。

您现在已经了解了如何使用 Aspose.Words for .NET 从文档中删除个人信息。按照本教程中提供的分步指南，您可以轻松地从自己的文档中删除敏感信息。