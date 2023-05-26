---
title: 不要压缩小图元文件
linktitle: 不要压缩小图元文件
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在保存文档时启用“不压缩小图元文件”功能。
type: docs
weight: 10
url: /zh/net/programming-with-docsaveoptions/do-not-compress-small-metafiles/
---

在 C# 应用程序中处理文件时，压缩文档中的元数据是一项常见功能。但是，可能有必要不压缩小文件的元数据以保持其质量。在本分步指南中，我们将向您展示如何使用 Aspose.Words for .NET 的 C# 源代码在文档保存选项中启用“不压缩小图元文件”功能。

## 理解 Aspose.Words 库

在深入研究代码之前，了解 .NET 的 Aspose.Words 库很重要。 Aspose.Words 是一个强大的库，可以在包括.NET 在内的不同平台上创建、编辑、转换和保护 Word 文档。它提供了许多用于操作文档的功能，例如插入文本、更改格式、添加部分等等。

## 第一步：设置文档目录

第一步是定义要保存文档的目录。您必须指定完整的目录路径。例如 ：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

请务必将“您的文档目录”替换为您的文档目录的实际路径。

## 第 2 步：插入部分和文本

然后您可以将部分和文本插入到您的文档中。使用 Aspose.Words 提供的 DocumentBuilder 类来构建文档的内容。这是一个简单的例子：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

在此示例中，我们创建一个新的空白文档，然后使用 DocumentBuilder 添加一行文本。

## 第 3 步：设置选项

'登记

现在让我们为文档配置保存选项。使用 DocSaveOptions 类指定保存设置。例如 ：

```csharp
DocSaveOptions saveOptions = new DocSaveOptions();
```

在此示例中，我们正在创建一个新的 DocSaveOptions 对象来设置保存选项。

## 第 4 步：启用“不压缩小图元文件”功能

要启用“不压缩小图元文件”功能，您必须设置`Compliance`DocSaveOptions 对象的属性值`PdfCompliance.PdfA1a`.就是这样：

```csharp
saveOptions.Compliance = PdfCompliance.PdfA1a;
```

此配置可确保在保存文档时不压缩小文件元数据。

## 第 5 步：保存文档

最后，您可以使用`Save`文档类的方法。指定文件的完整路径和所需的文件名。例如 ：

```csharp
doc.Save(dataDir + "DocumentWithDoNotCompressMetafiles.pdf", saveOptions);
```

请务必将“dataDir”替换为您的文档目录的路径。

### 使用 Aspose.Words for .NET 的 DocSaveOptions 示例源代码，不压缩小图元文件功能

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//插入带有一些文本的两个部分。
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

//使用“不压缩小图元文件”功能配置保存选项
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.Compliance = PdfCompliance.PdfA1a;

//使用指定选项保存文档
doc.Save(dataDir + "DocumentWithDoNotCompressMetafiles.pdf", saveOptions);
```

## 结论

在本指南中，我们解释了如何使用 Aspose.Words .NET 库在保存文档时启用“不压缩小图元文件”功能。按照提供的步骤并使用提供的 C# 源代码，您可以轻松地将此功能应用到您的 C# 应用程序中。保留未压缩的小文件元数据对于维护文档质量和完整性非常重要。