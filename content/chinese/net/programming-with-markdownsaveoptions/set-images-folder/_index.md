---
title: 设置图像文件夹
linktitle: 设置图像文件夹
second_title: Aspose.Words 文档处理 API
description: 了解如何在使用 Aspose.Words for .NET 导出到 Markdown 时设置图像文件夹。自定义图像的位置以实现更好的组织和集成。
type: docs
weight: 10
url: /zh/net/programming-with-markdownsaveoptions/set-images-folder/
---

以下是分步指南，用于解释以下 C# 源代码，该代码有助于使用 .NET 的 Aspose.Words 库为 Markdown 导出选项设置图像文件夹。在使用此代码之前，请确保已在项目中包含 Aspose.Words 库。

## 步骤 1：设置文档目录路径

```csharp
//文档目录的路径。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

确保指定包含图像的文档所在文档目录的正确路径。

## 第 2 步：加载包含图像的文档

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

我们加载包含要使用 Markdown 选项导出的图像的指定文档。

## 步骤 3：设置 Markdown 导出选项的图像文件夹

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };
```

我们创建一个实例`MarkdownSaveOptions`并使用设置图像文件夹的路径`ImagesFolder`属性。请确保指定要保存导出图像的文件夹的正确路径。

## 步骤 4：使用 Markdown 导出选项保存文档

```csharp
using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

我们使用指定的 Markdown 导出选项将文档保存到内存流。然后，您可以使用该流执行其他操作，例如将 Markdown 内容保存到文件。

### 使用 Aspose.Words for .NET 设置 MarkdownSaveOptions 图像文件夹的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Image bullet points.docx");

MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };

using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

此源代码演示了如何加载包含图像的文档，然后为 Markdown 导出选项设置图像文件夹。使用指定的选项，文档随后将保存到内存流。这允许您在导出 Markdown 内容时自定义图像文件夹的位置。