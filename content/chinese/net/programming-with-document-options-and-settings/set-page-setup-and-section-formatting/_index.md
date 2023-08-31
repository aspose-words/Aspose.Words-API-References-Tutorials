---
title: 设置页面设置和部分格式
linktitle: 设置页面设置和部分格式
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 设置文档布局和部分格式的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-document-options-and-settings/set-page-setup-and-section-formatting/
---

在本教程中，我们将引导您完成 C# 源代码，以使用 Aspose.Words for .NET 设置布局和部分格式。此功能允许您设置页面方向、边距和纸张尺寸。

## 第 1 步：项目设置

首先，在您最喜欢的 IDE 中创建一个新的 C# 项目。确保您的项目中引用了 Aspose.Words for .NET 库。

## 第 2 步：创建文档

在此步骤中，我们将创建一个新文档。使用以下代码创建文档并初始化构造函数：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

代替`"YOUR DOCUMENTS DIRECTORY"`与要保存文档的目录的实际路径。

## 步骤 3：设置布局并保存文档

现在让我们配置文档布局。使用以下代码设置方向、边距和纸张尺寸：

```csharp
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.LeftMargin = 50;
builder.PageSetup.PaperSize = PaperSize.Paper10x14;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
```

此代码将页面方向设置为横向，左边距设置为 50，纸张尺寸设置为 10x14。

### 使用 Aspose.Words for .NET 设置页面设置和节格式的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.PageSetup.Orientation = Orientation.Landscape;
	builder.PageSetup.LeftMargin = 50;
	builder.PageSetup.PaperSize = PaperSize.Paper10x14;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
  
```

请务必指定要在其中保存文档的目录的正确路径`dataDir`多变的。

您现在已经了解了如何使用 Aspose.Words for .NET 配置文档的布局和部分格式。通过遵循本教程中提供的分步指南，您可以轻松自定义自己文档的布局和格式。