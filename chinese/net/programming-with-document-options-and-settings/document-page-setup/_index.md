---
title: 文档页面设置
linktitle: 文档页面设置
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 设置文档布局的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-document-options-and-settings/document-page-setup/
---

在本教程中，我们将引导您完成 C# 源代码，以使用 Aspose.Words for .NET 配置文档布局。此功能允许您设置布局模式、每行字符数和每页行数。

## 第 1 步：项目设置

首先，在您最喜欢的 IDE 中创建一个新的 C# 项目。确保您的项目中引用了 Aspose.Words for .NET 库。

## 第 2 步：加载文档

在此步骤中，我们将加载要配置的Word文档。使用以下代码加载文档：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

代替`"YOUR DOCUMENTS DIRECTORY"`与文档所在目录的实际路径。

## 第 3 步：设置布局

现在让我们配置文档布局。使用以下代码设置布局模式、每行字符数和每页行数：

```csharp
doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
doc.FirstSection.PageSetup.CharactersPerLine = 30;
doc.FirstSection.PageSetup.LinesPerPage = 10;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
```

此代码将布局模式设置为“Grid”，然后指定每行的字符数和每页的行数。

### 使用 Aspose.Words for .NET 进行文档页面设置的示例源代码


```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	//设置允许定义文档网格行为的部分的布局模式。
	//请注意，“文档网格”选项卡在 MS Word 的“页面设置”对话框中变得可见
	//是否将任何亚洲语言定义为编辑语言。
	doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
	doc.FirstSection.PageSetup.CharactersPerLine = 30;
	doc.FirstSection.PageSetup.LinesPerPage = 10;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
   
```

请务必在中指定正确的文档路径`dataDir`多变的。

您现在已经了解了如何使用 Aspose.Words for .NET 配置文档的布局。通过遵循本教程中提供的分步指南，您可以轻松自定义自己的文档的布局。