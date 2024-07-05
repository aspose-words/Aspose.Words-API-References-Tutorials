---
title: 将字体导出为 Base 64
linktitle: 将字体导出为 Base 64
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 保存文档时导出 base 64 字体的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---

在本教程中，我们将引导您完成使用 Aspose.Words for .NET 导出 base 64 字体的 C# 源代码。此功能允许您在以 HTML 格式保存文档时将字体导出为 base 64 数据。

## 步骤 1：项目设置

首先，在您最喜欢的 IDE 中创建一个新的 C# 项目。确保您的项目中引用了 Aspose.Words for .NET 库。

## 步骤 2：加载文档

在此步骤中，我们将加载要导出的文档。使用以下代码从指定目录加载文档：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

此代码创建`Document`通过从指定目录加载文档。

## 步骤 3：配置 HTML 备份选项

现在我们将配置 HTML 保存选项以导出 base 64 字体。使用以下代码：

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

此代码创建`HtmlSaveOptions`并设置`ExportFontsAsBase64`到`true`指定在保存为 HTML 时应将字体导出为 base 64 数据。

## 步骤 4：将文档转换并保存为 HTML

最后，我们将使用之前配置的 HTML 保存选项将文档转换为 HTML。使用以下代码：

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

此代码将文档转换为 HTML，并将其保存到文件中，并将字体导出为 base 64 数据。

### 使用 Aspose.Words for .NET 将字体导出为 Base 64 的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);

```

确保在`dataDir`多变的。

现在，您已经了解了如何使用 Aspose.Words for .NET 将文档保存为 HTML 时导出 base 64 字体。按照本教程中提供的分步指南，您可以轻松地安全地导出字体并将其嵌入到 HTML 文档中。