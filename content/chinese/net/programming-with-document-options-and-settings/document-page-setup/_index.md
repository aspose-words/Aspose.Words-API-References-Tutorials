---
title: 文档页面设置
linktitle: 文档页面设置
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 设置文档布局的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-document-options-and-settings/document-page-setup/
---

在本教程中，我们将引导您完成使用 Aspose.Words for .NET 配置文档布局的 C# 源代码。此功能允许您设置布局模式、每行的字符数和每页的行数。

## 步骤 1：项目设置

首先，在您最喜欢的 IDE 中创建一个新的 C# 项目。确保您的项目中引用了 Aspose.Words for .NET 库。

## 步骤 2：加载文档

在此步骤中，我们将加载要配置的Word文档。使用以下代码加载文档：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

代替`"YOUR DOCUMENTS DIRECTORY"`与文档所在目录的实际路径一致。

## 步骤 3：设置布局

现在我们来配置文档布局。使用以下代码设置布局模式、每行字符数和每页行数：

```csharp
doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
doc.FirstSection.PageSetup.CharactersPerLine = 30;
doc.FirstSection.PageSetup.LinesPerPage = 10;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
```

此代码将布局模式设置为“网格”，然后指定每行的字符数和每页的行数。

### 使用 Aspose.Words for .NET 进行文档页面设置的示例源代码


```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	//设置某个部分的布局模式以允许定义文档网格行为。
	//请注意，文档网格选项卡在 MS Word 的“页面设置”对话框中可见
	//如果任何亚洲语言被定义为编辑语言。
	doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
	doc.FirstSection.PageSetup.CharactersPerLine = 30;
	doc.FirstSection.PageSetup.LinesPerPage = 10;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
   
```

确保在`dataDir`多变的。

现在您已经了解了如何使用 Aspose.Words for .NET 配置文档的布局。通过遵循本教程中提供的分步指南，您可以轻松自定义您自己的文档的布局。