---
title: 将文本输入表单字段导出为文本
linktitle: 将文本输入表单字段导出为文本
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 将文本输入表单字段导出为纯文本的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---

在本教程中，我们将引导您完成 C# 源代码，以使用 Aspose.Words for .NET 将文本输入表单字段导出为纯文本。此功能允许您将文本输入表单字段导出为可读文本，而不是将其导出为 HTML 输入元素。

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

现在我们将配置 HTML 保存选项以将文本输入表单字段导出为纯文本。使用以下代码：

```csharp
string imagesDir = Path. Combine(ArtifactsDir, "Images");

//指定的文件夹必须存在且为空。
if (Directory.Exists(imagesDir))
Directory. Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
ExportTextInputFormFieldAsText = true,
ImagesFolder = imagesDir
};
```

这段代码创建了一个实例`HtmlSaveOptions`并设置`ExportTextInputFormFieldAsText`选项`true`将文本输入表单字段导出为纯文本。此外，它还指定保存提取的图像的文件夹。

## 步骤 4：将文档转换并保存为 HTML

最后，我们将使用之前配置的 HTML 保存选项将文档转换为 HTML。使用以下代码：

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);
```

此代码通过将文本输入表单字段导出为纯文本来将文档转换为 HTML，并将导出的 HTML 文件保存到指定目录。

### 使用 Aspose.Words for .NET 将文本输入表单字段导出为文本的示例源代码


```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	string imagesDir = Path.Combine(ArtifactsDir, "Images");

	//指定的文件夹需要存在并且应该为空。
	if (Directory.Exists(imagesDir))
		Directory.Delete(imagesDir, true);

	Directory.CreateDirectory(imagesDir);

	//设置选项以将表单字段导出为纯文本，而不是 HTML 输入元素。
	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		ExportTextInputFormFieldAsText = true, ImagesFolder = imagesDir
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);

```

请务必在文件目录中指定正确的路径`dataDir`多变的。