---
title: 不保存图片项目符号
linktitle: 不保存图片项目符号
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中禁用保存图像项目符号。
type: docs
weight: 10
url: /zh/net/programming-with-docsaveoptions/do-not-save-picture-bullet/
---

图片项目符号是Word文档中常用的功能，用于添加自定义项目符号。但是，在某些情况下，使用 Aspose.Words Library for .NET 操作文档时可能需要禁用图像项目符号注册。在本分步指南中，我们将解释如何使用 Aspose.Words C# .NET 源代码通过 DocSaveOptions 保存选项禁用图像项目符号保存。

## 了解 Aspose.Words 库

在深入研究代码之前，了解 .NET 的 Aspose.Words 库非常重要。 Aspose.Words 是一个功能强大的库，可在包括.NET 在内的不同平台上创建、编辑、转换和保护 Word 文档。它提供了许多用于操作文档的功能，例如插入文本、更改格式、添加部分等等。

## 第1步：设置文档目录

第一步是定义文档所在的目录。您必须指定完整的目录路径。例如 ：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

请务必将“您的文档目录”替换为文档目录的实际路径。

## 步骤 2：加载带有图像项目符号的文档

接下来，您需要加载带有图像项目符号的文档。使用 Document 类从文件加载文档。例如 ：

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

在此示例中，我们从文件“ImageBulletpoints.docx”加载文档

  位于文档目录中。

## 步骤 3：配置录制选项

现在让我们配置文档的保存选项。使用 DocSaveOptions 类指定保存设置。例如 ：

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };
```

在此示例中，我们创建一个新的 DocSaveOptions 对象并将 SavePictureBullet 属性设置为 false 以禁用保存图片项目符号。

## 步骤4：启用“不保存图片项目符号”功能

为了启用“不保存图片项目符号”功能，我们已经配置了保存选项，并将 SavePictureBullet 设置为 false。这可确保图像项目符号不会保存在最终文档中。

## 第 5 步：保存文档

最后，您可以使用 Document 类的 Save 方法保存文档。指定文件的完整路径和所需的文件名。例如 ：

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

请务必将“dataDir”替换为文档的目录路径。

## 使用 Aspose.Words for .NET 的 DocSaveOptions 保存选项以及“不保存图片项目符号”功能的示例源代码

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载带有图像项目符号的文档
Document doc = new Document(dataDir + "Image bullet points.docx");

//使用“不保存图片项目符号”功能配置保存选项
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };

//使用指定选项保存文档
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

## 结论

在本指南中，我们介绍了如何使用 .NET 的 Aspose.Words 库禁用在文档中保存图像项目符号。通过遵循提供的步骤并使用提供的 C# 源代码，您可以轻松地在 C# 应用程序中应用此功能。在某些情况下，禁用图片项目符号保存可能很有用，可以保留文档结构和格式而不保存图片项目符号。