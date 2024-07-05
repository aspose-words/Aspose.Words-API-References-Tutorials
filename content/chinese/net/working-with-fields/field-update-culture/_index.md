---
title: 现场更新文化
linktitle: 现场更新文化
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 更新 Word 文档中的字段文化。
type: docs
weight: 10
url: /zh/net/working-with-fields/field-update-culture/
---

以下是分步指南，用于解释下面的 C# 源代码，该代码使用了 Aspose.Words for .NET 的“字段文化更新”功能。请务必仔细遵循每个步骤以获得所需的结果。

## 步骤 1：文档目录设置

在提供的代码中，您必须指定文档的目录。将值“YOUR DOCUMENT DIRECTORY”替换为您的文档目录的相应路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：创建文档和文档生成器

我们首先创建一个新文档和一个文档生成器。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步骤 3：插入时间字段

我们使用`InsertField()`方法将时间字段插入到文档中。

```csharp
builder. InsertField(FieldType.FieldTime, true);
```

这将在文档中插入时间字段。

## 步骤4：配置字段更新文化

我们配置字段选项来指定字段更新文化应该基于字段代码。

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();
```

这些选项决定了更新字段所使用的文化。

### 使用 Aspose.Words for .NET 更新字段文化的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//创建文档和文档生成器。
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//插入时间字段。
builder. InsertField(FieldType.FieldTime, true);

//配置字段更新文化。
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();

//保存文档。
doc.Save(dataDir + "UpdateCultureChamps.pdf");
```

在这个例子中，我们创建了一个新文档，插入了一个时间字段，并配置了字段更新文化。然后我们使用指定的文件名保存了该文档。

这就是我们关于使用 Aspose.Words for .NET 的“更新字段文化”功能的指南。

### 常见问题解答

#### 问：Aspose.Words 中的字段更新文化是什么？

答：Aspose.Words 中的字段更新文化是指用于格式化和更新 Word 文档中的字段值的文化。文化决定了更新字段时数字、日期和其他数据的显示方式。

#### 问：如何使用 Aspose.Words 设置 Word 文档中字段的更新文化？

答：要使用 Aspose.Words 设置 Word 文档中字段的更新文化，您可以按照以下步骤操作：

1. 从 Aspose.Words 命名空间导入 Document 类。
2. 通过加载现有文档来创建 Document 的实例。
3. 使用 Document.UpdateFieldsCultureInfo 属性设置字段的更新文化。

#### 问：Aspose.Words 中更新字段支持哪些文化？

答：Aspose.Words 支持使用不同的文化来更新字段。您可以指定操作系统支持的任何文化。例如，“en-US” 表示美式英语，“fr-FR” 表示法语，“de-DE” 表示德语等。

#### 问：是否可以为单个字段而不是整个文档设置特定的文化？

答：是的，可以为单个字段设置特定的文化，而不是为整个文档设置特定的文化。在 Aspose.Words 中，每个字段都有一个 Format 属性，可用于设置特定于该字段的格式文化。这让您可以控制此字段的显示和更新方式，而不受文档中其他字段的影响。

#### 问：如何检查 Word 文档中当前定义的字段更新文化？

答：要检查 Word 文档中当前定义的字段更新文化，可以使用 Document.UpdateFieldsCultureInfo 属性。此属性返回代表当前用于设置字段更新的文化的 CultureInfo 对象。