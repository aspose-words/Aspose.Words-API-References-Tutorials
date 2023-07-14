---
title: 导出往返信息
linktitle: 导出往返信息
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 将文档另存为 HTML 时导出往返信息的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-htmlsaveoptions/export-roundtrip-information/
---

在本教程中，我们将引导您完成 C# 源代码，以使用 Aspose.Words for .NET 从文档中导出往返信息。此功能允许您在导出的 HTML 文件中包含往返信息，从而更轻松地检索对原始文档所做的更改。

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

现在我们将配置 HTML 保存选项以导出文档的往返信息。使用以下代码：

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };
```

这段代码创建了一个实例`HtmlSaveOptions`并设置`ExportRoundtripInformation`选项`true`导出时包含往返信息。

## 步骤 4：将文档转换并保存为 HTML

最后，我们将使用之前配置的 HTML 保存选项将文档转换为 HTML。使用以下代码：

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
```

此代码将文档转换为包含往返信息的 HTML，并将导出的 HTML 文件保存到指定目录。

### 使用 Aspose.Words for .NET 导出往返信息的示例源代码


```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);

```

请务必在文件目录中指定正确的路径`dataDir`多变的。