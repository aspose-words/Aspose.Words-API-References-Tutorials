---
title: 添加 Css 类名称前缀
linktitle: 添加 Css 类名称前缀
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 将文档转换为 HTML 时添加 CSS 类名前缀的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---

在本教程中，我们将引导您通过 C# 源代码添加带有 Aspose.Words for .NET 的 CSS 类名前缀。此功能允许您在将文档转换为 HTML 时向生成的 CSS 类名称添加自定义前缀。

## 第 1 步：项目设置

首先，在您喜欢的 IDE 中创建一个新的 C# 项目。确保在您的项目中引用了 Aspose.Words for .NET 库。

## 第 2 步：装入文档

在此步骤中，我们将加载要转换为 HTML 的 Word 文档。使用以下代码加载文档：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

代替`"YOUR DOCUMENTS DIRECTORY"`使用文档所在目录的实际路径。

## 第 3 步：设置 HTML 保存选项

现在让我们设置 HTML 保存选项，包括 CSS 样式表类型和 CSS 类名前缀。使用以下代码：

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
     CssStyleSheetType = CssStyleSheetType.External,
     CssClassNamePrefix = "pfx_"
};
```

此代码创建一个实例`HtmlSaveOptions`并设置`CssStyleSheetType`到`CssStyleSheetType.External`生成外部 CSS 样式表，以及`CssClassNamePrefix`到`"pfx_"`前缀`"pfx_"`命名 CSS 类。

## 第 4 步：将文档转换并保存为 HTML

最后，我们将使用前面定义的 HTML 保存选项将文档转换为 HTML。使用以下代码：

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

此代码将文档转换为 HTML 并将其保存到添加了 CSS 类名前缀的文件中。

### 使用 Aspose.Words for .NET 添加 Css 类名称前缀的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External, CssClassNamePrefix = "pfx_"
	};
	
	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);

```

请务必在`dataDir`多变的。

您现在已经了解了如何在使用 Aspose.Words for .NET 将文档转换为 HTML 时添加 CSS 类名前缀。按照本教程中提供的分步指南步骤，您可以在转换后的 HTML 文档中自定义 CSS 类名称。