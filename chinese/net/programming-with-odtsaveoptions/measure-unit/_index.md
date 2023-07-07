---
title: 测量单位
linktitle: 测量单位
second_title: Aspose.Words for .NET API 参考
description: 了解如何在使用 Aspose.Words for .NET 将 Word 文档转换为 ODT 时指定度量单位。
type: docs
weight: 10
url: /zh/net/programming-with-odtsaveoptions/measure-unit/
---

在 C# 应用程序中将 Word 文档转换为 OpenDocument Text (ODT) 格式时，您可能需要指定用于可测量格式和内容属性的测量单位。借助适用于 .NET 的 Aspose.Words 库，您可以使用 OdtSaveOptions 保存选项轻松指定此功能。在本分步指南中，我们将引导您了解如何使用 Aspose.Words for .NET C# 源代码通过使用 OdtSaveOptions 指定度量单位将 Word 文档转换为 ODT。

## 了解 Aspose.Words 库

在深入研究代码之前，了解 .NET 的 Aspose.Words 库非常重要。 Aspose.Words 是一个功能强大的库，可在包括.NET 在内的不同平台上创建、编辑、转换和保护 Word 文档。它提供了许多用于操作文档的功能，例如插入文本、更改格式、添加部分等等。

## 加载Word文档

第一步是加载要转换为 ODT 的 Word 文档。使用 Document 类从源文件加载文档。这是一个例子：

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

在此示例中，我们加载位于文档目录中的文档“Document.docx”。

## 配置备份选项

下一步是配置转换为 ODT 的备份选项。使用 OdtSaveOptions 类并将 MeasureUnit 属性设置为所需的值。例如，如果要使用英寸作为测量单位，请将 MeasureUnit 设置为 OdtSaveMeasureUnit.Inches。操作方法如下：

```csharp
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

我们创建一个新的 OdtSaveOptions 对象并将 MeasureUnit 属性设置为所需的值，在我们的示例中，OdtSaveMeasureUnit.Inches 使用英寸作为测量单位。

## 将文档转换为 ODT

现在我们已经配置了保存选项，我们可以继续将文档转换为 ODT。使用 Document 类的 Save 方法通过指定保存选项以 ODT 格式保存转换后的文档。这是一个例子：

```csharp
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

在此示例中，我们使用指定的保存选项将转换后的文档另存为“WorkingWithOdtSaveOptions.MeasureUnit.odt”。

### 使用 Aspose.Words for .NET 的具有“测量单位”功能的 OdtSaveOptions 示例源代码



```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载Word文档
Document doc = new Document(dataDir + "Document.docx");

//使用“测量单位”功能配置备份选项
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };

//将文档转换为 ODT
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

## 结论

在本指南中，我们解释了如何通过使用适用于 .NET 的 Aspose.Words 库的 OdtSaveOptions 保存选项指定测量单位，将 Word 文档转换为 ODT。通过遵循提供的步骤并使用提供的 C# 源代码，您可以轻松地在 C# 应用程序中应用此功能。转换为 ODT 时指定测量单位可让您根据具体需要控制结果文档的格式和尺寸。