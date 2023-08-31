---
title: 导出 Mhtml 资源的 Cid URL
linktitle: 导出 Mhtml 资源的 Cid URL
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 保存文档时导出 MHTML 资源的 CID URL 的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-htmlsaveoptions/export-cid-urls-for-mhtml-resources/
---

在本教程中，我们将引导您完成 C# 源代码，以使用 Aspose.Words for .NET 导出 MHTML 资源的 CID URL。此功能允许您在以 MHTML 格式保存文档时导出 MHTML 资源的 CID URL。

## 第 1 步：项目设置

首先，在您最喜欢的 IDE 中创建一个新的 C# 项目。确保您的项目中引用了 Aspose.Words for .NET 库。

## 第 2 步：加载文档

在此步骤中，我们将加载要导出的文档。使用以下代码从指定目录加载文档：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Content-ID.docx");
```

这段代码创建了一个实例`Document`通过从指定目录加载文档。

## 步骤 3：配置 HTML 备份选项

现在我们将配置 HTML 保存选项以导出 MHTML 资源的 CID URL。使用以下代码：

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
{
PrettyFormat = true,
ExportCidUrlsForMhtmlResources = true
};
```

这段代码创建了一个实例`HtmlSaveOptions`保存格式设置为 MHTML。它还可以通过设置导出 MHTML 资源的 CID URL`ExportCidUrlsForMhtmlResources`到`true`.

## 步骤 4：将文档转换并保存为 MHTML

最后，我们将使用之前配置的 HTML 保存选项将文档转换为 MHTML。使用以下代码：

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);
```

此代码将文档转换为 MHTML 并将其保存到具有导出的 MHTML 资源的 CID URL 的文件中。

### 使用 Aspose.Words for .NET 导出 Mhtml 资源的 Cid URL 的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Content-ID.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
	{
		PrettyFormat = true, ExportCidUrlsForMhtmlResources = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);

```

请务必在文件目录中指定正确的路径`dataDir`多变的。

您现在已经了解了如何使用 Aspose.Words for .NET 以 MHTML 格式保存文档时导出 MHTML 资源的 CID URL。通过遵循本教程中提供的分步指南，您可以轻松管理导出的 MHTML 文档中的 CID URL。

