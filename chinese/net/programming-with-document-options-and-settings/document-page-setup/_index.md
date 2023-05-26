---
title: 文档页面设置
linktitle: 文档页面设置
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 设置文档布局的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-document-options-and-settings/document-page-setup/
---

在本教程中，我们将引导您通过 C# 源代码使用 Aspose.Words for .NET 配置文档布局。此功能允许您设置布局模式、每行字符数和每页行数。

## 第 1 步：项目设置

首先，在您喜欢的 IDE 中创建一个新的 C# 项目。确保在您的项目中引用了 Aspose.Words for .NET 库。

## 第 2 步：装入文档

在此步骤中，我们将加载要配置的 Word 文档。使用以下代码加载文档：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

代替`"YOUR DOCUMENTS DIRECTORY"`使用文档所在目录的实际路径。

## 第 3 步：设置布局

现在让我们配置文档布局。使用以下代码设置布局方式、每行字符数和每页行数：

```csharp
doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
doc.FirstSection.PageSetup.CharactersPerLine = 30;
doc.FirstSection.PageSetup.LinesPerPage = 10;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
```

此代码将布局模式设置为“网格”，然后指定每行字符数和每页行数。

### 使用 Aspose.Words for .NET 的文档页面设置示例源代码


```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	//为允许定义文档网格行为的部分设置布局模式。
	//请注意，文档网格选项卡在 MS Word 的页面设置对话框中可见
	//如果任何亚洲语言被定义为编辑语言。
	doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
	doc.FirstSection.PageSetup.CharactersPerLine = 30;
	doc.FirstSection.PageSetup.LinesPerPage = 10;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
   
```

请务必在`dataDir`多变的。

您现在已经了解了如何使用 Aspose.Words for .NET 配置文档的布局。按照本教程中提供的分步指南，您可以轻松自定义自己文档的布局。