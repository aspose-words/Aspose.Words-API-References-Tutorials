---
title: 查看选项
linktitle: 查看选项
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 配置文档显示选项的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-document-options-and-settings/view-options/
---

在本教程中，我们将引导您通过 C# 源代码使用 Aspose.Words for .NET 配置显示选项。此功能允许您自定义文档中的查看模式和缩放级别。

## 第 1 步：项目设置

首先，在您喜欢的 IDE 中创建一个新的 C# 项目。确保在您的项目中引用了 Aspose.Words for .NET 库。

## 第 2 步：装入文档

在此步骤中，我们将加载要为其配置显示选项的 Word 文档。使用以下代码加载文档：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

代替`"YOUR DOCUMENTS DIRECTORY"`使用文档所在目录的实际路径。

## 第 3 步：配置显示选项

现在我们将配置文档显示选项。使用以下代码设置显示模式和缩放级别：

```csharp
doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
```

此代码将视图模式设置为“PageLayout”并将缩放级别设置为 50%。

### 使用 Aspose.Words for .NET 的视图选项示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	doc.ViewOptions.ViewType = ViewType.PageLayout;
	doc.ViewOptions.ZoomPercent = 50;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
    
```

请务必在`dataDir`多变的。

您现在已经学习了如何使用 Aspose.Words for .NET 配置文档显示选项。按照本教程中提供的分步指南，您可以轻松自定义自己文档的显示。