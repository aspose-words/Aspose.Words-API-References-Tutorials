---
title: 出口资源
linktitle: 出口资源
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 将文档资源另存为 HTML 时导出文档资源的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-htmlsaveoptions/export-resources/
---

在本教程中，我们将引导您完成 C# 源代码，以使用 Aspose.Words for .NET 导出文档资源。此功能允许您在以 HTML 格式保存文档时将资源（例如字体）导出为外部文件。

## 第 1 步：项目设置

首先，在您最喜欢的 IDE 中创建一个新的 C# 项目。确保您的项目中引用了 Aspose.Words for .NET 库。

## 第 2 步：加载文档

在此步骤中，我们将加载要导出的文档。使用以下代码从指定目录加载文档：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

这段代码创建了一个实例`Document`通过从指定目录加载文档。

## 步骤 3：配置 HTML 备份选项

现在我们将配置 HTML 保存选项来导出文档资源。使用以下代码：

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
CssStyleSheetType = CssStyleSheetType.External,
ExportFontResources=true,
ResourceFolder = ArtifactsDir + "Resources",
ResourceFolderAlias = "http://example.com/resources”
};
```

这段代码创建了一个实例`HtmlSaveOptions`并设置以下选项：

- `CssStyleSheetType`被设定为`CssStyleSheetType.External`将 CSS 样式表导出到外部文件。
- `ExportFontResources`被设定为`true`导出字体资源。
- `ResourceFolder`指定保存资源的目标目录。
- `ResourceFolderAlias`指定将用于访问资源的 URL 别名。

## 步骤 4：将文档转换并保存为 HTML

最后，我们将使用之前配置的 HTML 保存选项将文档转换为 HTML。使用以下代码：

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

此代码将文档转换为 HTML 并使用指定的 URL 别名将资源保存到指定目录。

### 使用 Aspose.Words for .NET 导出资源的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External,
		ExportFontResources = true,
		ResourceFolder = ArtifactsDir + "Resources",
		ResourceFolderAlias = "http://example.com/resources”
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
  
```

请务必在文件目录中指定正确的路径`dataDir`多变的。