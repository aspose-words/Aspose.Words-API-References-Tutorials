---
title: 设置图像文件夹
linktitle: 设置图像文件夹
second_title: Aspose.Words 文档处理 API
description: 了解使用 Aspose.Words for .NET 导出到 Markdown 时如何设置图像文件夹。自定义图像的位置以更好地组织和集成。
type: docs
weight: 10
url: /zh/net/programming-with-markdownsaveoptions/set-images-folder/
---

以下是逐步指南，解释以下 C# 源代码，该代码有助于使用 .NET 的 Aspose.Words 库为 Markdown 导出选项设置图像文件夹。在使用此代码之前，请确保您已在项目中包含 Aspose.Words 库。

## 第1步：设置文档目录路径

```csharp
//文档目录的路径。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

请务必指定包含图像的文档所在文档目录的正确路径。

## 步骤 2：加载包含图像的文档

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

我们加载包含要使用 Markdown 选项导出的图像的指定文档。

## 第 3 步：为 Markdown 导出选项设置图像文件夹

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };
```

我们创建一个实例`MarkdownSaveOptions`并使用以下命令设置图像文件夹的路径`ImagesFolder`财产。确保指定要保存导出图像的文件夹的正确路径。

## 步骤 4：使用 Markdown 导出选项保存文档

```csharp
using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

我们使用指定的 Markdown 导出选项将文档保存到内存流。然后，您可以使用该流程执行其他操作，例如将 Markdown 内容保存到文件中。

### 使用 Aspose.Words for .NET 为 MarkdownSaveOptions 设置图像文件夹的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Image bullet points.docx");

MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };

using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

此源代码演示了如何加载包含图像的文档，然后为 Markdown 导出选项设置图像文件夹。然后使用指定的选项将文档保存到内存流中。这允许您在导出 Markdown 内容时自定义图像文件夹的位置。