---
title: 不使用文档生成器插入 TOA 字段
linktitle: 不使用文档生成器插入 TOA 字段
second_title: Aspose.Words 文档处理 API
description: 了解如何在 Aspose.Words for .NET 中不使用文档生成器插入 TOA 字段。按照我们的分步指南有效地管理法律引文。
type: docs
weight: 10
url: /zh/net/working-with-fields/insert-toafield-without-document-builder/
---
## 介绍

在 Word 文档中创建引文表 (TOA) 字段就像拼凑一个复杂的拼图。然而，在 Aspose.Words for .NET 的帮助下，这个过程变得顺畅而简单。在本文中，我们将指导您完成在不使用文档生成器的情况下插入 TOA 字段的步骤，让您轻松管理 Word 文档中的引文和法律参考。

## 先决条件

在深入学习本教程之前，让我们先介绍一下您需要的基本知识：

-  Aspose.Words for .NET：确保安装了最新版本。您可以从[Aspose 网站](https://releases.aspose.com/words/net/).
- 开发环境：与 .NET 兼容的 IDE，如 Visual Studio。
- 基本 C# 知识：了解基本 C# 语法和概念将会有所帮助。
- 示例 Word 文档：创建或准备好要插入 TOA 字段的示例文档。

## 导入命名空间

首先，您需要从 Aspose.Words 库导入必要的命名空间。此设置可确保您可以访问文档操作所需的所有类和方法。

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

让我们将这个过程分解成简单易懂的步骤。我们将引导您完成每个阶段，解释每段代码的作用以及它如何有助于创建 TOA 字段。

## 步骤 1：初始化文档

首先，您需要创建一个实例`Document`类。此对象代表您正在处理的 Word 文档。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

此代码初始化一个新的 Word 文档。您可以将其视为创建一个空白画布，您可以在其中添加内容。

## 步骤2：创建并配置TA字段

接下来，我们将添加 TA（授权书目录）字段。此字段标记将出现在 TOA 中的条目。

```csharp
Paragraph para = new Paragraph(doc);

//我们希望插入如下 TA 和 TOA 字段：
// { TA \c 1 \l "值 0" }
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);
```

具体如下：
- Paragraph para = new Paragraph(doc);：在文档内创建一个新段落。
-  FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);：向段落添加 TA 字段。这`FieldType.FieldTOAEntry`指定这是一个 TOA 输入字段。
- fieldTA.EntryCategory = "1";：设置条目类别。这对于对不同类型的条目进行分类很有用。
- fieldTA.LongCitation = "Value 0";：指定长引文文本。这是将出现在 TOA 中的文本。
- doc.FirstSection.Body.AppendChild(para);：将包含TA字段的段落附加到文档正文。

## 步骤 3：添加 TOA 字段

现在，我们将把编译所有 TA 条目的实际 TOA 字段插入到表中。

```csharp
para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);
```

在此步骤中：
- FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);：向段落添加 TOA 字段。
- fieldToa.EntryCategory = "1";：过滤条目以仅包含标有类别“1”的条目。

## 步骤 4：更新 TOA 字段

插入 TOA 字段后，您需要更新它以确保它反映最新的条目。

```csharp
fieldToa.Update();
```

此命令刷新 TOA 字段，确保所有标记的条目都正确显示在表中。

## 步骤 5：保存文档

最后，使用新添加的 TOA 字段保存您的文档。

```csharp
doc.Save(dataDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

这行代码将文档保存到指定目录。请确保替换`"YOUR DOCUMENT DIRECTORY"`使用您想要保存文件的实际路径。

## 结论

就这样！您已成功将 TOA 字段添加到 Word 文档，而无需使用文档生成器。通过遵循这些步骤，您可以有效地管理引文并在法律文件中创建全面的引文表。Aspose.Words for .NET 使此过程变得顺畅而高效，为您提供了轻松处理复杂文档任务的工具。

## 常见问题解答

### 我可以添加多个不同类别的 TA 字段吗？
是的，您可以通过设置添加具有不同类别的多个 TA 字段`EntryCategory`相应的财产。

### 如何自定义 TOA 的外观？
您可以通过修改 TOA 字段的属性（例如条目格式和类别标签）来定制 TOA 的外观。

### 是否可以自动更新 TOA 字段？
虽然你可以使用`Update`方法，Aspose.Words 目前不支持文档更改的自动更新。

### 我可以以编程方式在文档的特定部分添加 TA 字段吗？
是的，您可以通过将 TA 字段插入到所需的段落或部分中来在特定位置添加 TA 字段。

### 如何处理单个文档中的多个 TOA 字段？
您可以通过分配不同的`EntryCategory`值并确保每个 TOA 字段根据其类别过滤条目。