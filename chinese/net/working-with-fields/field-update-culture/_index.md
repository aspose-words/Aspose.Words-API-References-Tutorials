---
title: 现场更新文化
linktitle: 现场更新文化
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 更新 Word 文档中的字段文化。
type: docs
weight: 10
url: /zh/net/working-with-fields/field-update-culture/
---

下面是解释 C# 源代码的分步指南，该源代码使用 Aspose.Words for .NET 的“Field Culture Update”功能。确保仔细执行每个步骤以获得所需的结果。

## 第 1 步：文档目录设置

在提供的代码中，您必须指定文档的目录。将值“YOUR DOCUMENT DIRECTORY”替换为文档目录的相应路径。

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

这将在文档中插入一个时间字段。

## 步骤 4：配置字段更新文化

我们配置字段选项以指定字段更新区域性应基于字段代码。

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();
```

这些选项确定用于更新字段的区域性。

### 使用 Aspose.Words for .NET 更新现场文化的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//创建文档和文档生成器。
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//插入时间字段。
builder. InsertField(FieldType.FieldTime, true);

//配置字段更新区域性。
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();

//保存文档。
doc.Save(dataDir + "UpdateCultureChamps.pdf");
```

在此示例中，我们创建了一个新文档，插入了一个时间字段，并配置了字段更新区域性。然后我们用指定的文件名保存文档。

我们关于使用 Aspose.Words for .NET 的“更新字段文化”功能的指南到此结束。

### 常见问题解答

#### 问：Aspose.Words 中的字段更新文化是什么？

答：Aspose.Words 中的字段更新区域性是指用于格式化和更新 Word 文档中字段值的区域性。区域性决定数字、日期和其他数据更新时在字段中的显示方式。

#### 问：如何使用 Aspose.Words 设置 Word 文档中字段的更新区域性？

答：要使用 Aspose.Words 设置 Word 文档中字段的更新区域性，您可以按照以下步骤操作：

1. 从 Aspose.Words 命名空间导入 Document 类。
2. 通过加载现有文档来创建 Document 实例。
3. 使用 Document.UpdateFieldsCultureInfo 属性设置字段的更新区域性。

#### 问：Aspose.Words 中更新字段支持哪些区域性？

答：Aspose.Words 支持不同文化的字段更新。您可以指定操作系统支持的任何区域性。例如，“en-US”表示美式英语，“fr-FR”表示法语，“de-DE”表示德语等。

#### 问：是否可以为单个字段而不是整个文档设置特定的文化？

答：是的，可以为单个字段而不是整个文档设置特定的文化。在Aspose.Words中，每个字段都有一个Format属性，可用于设置特定于该字段的格式区域性。这使您可以控制该字段的显示和更新方式，独立于文档中的其他字段。

#### 问：如何检查 Word 文档中当前定义的字段更新区域性？

答：要检查 Word 文档中当前定义的字段更新区域性，可以使用 Document.UpdateFieldsCultureInfo 属性。此属性返回表示当前用于设置字段更新的区域性的 CultureInfo 对象。