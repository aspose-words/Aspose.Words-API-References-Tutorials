---
title: 使用 DOM 插入合并字段
linktitle: 使用 DOM 插入合并字段
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将自定义字段合并字段插入到您的 Word 文档中。
type: docs
weight: 10
url: /zh/net/working-with-fields/insert-merge-field-using-dom/
---

这是一个逐步指南，用于解释下面的 C# 源代码，它使用 Aspose.Words for .NET 的“插入字段合并字段”功能。确保仔细执行每个步骤以获得所需的结果。

## 第 1 步：文档目录设置

在提供的代码中，您必须指定文档的目录。将值“YOUR DOCUMENT DIRECTORY”替换为您的文档目录的适当路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：创建文档和 DocumentBuilder

我们首先创建一个新文档并初始化一个 DocumentBuilder。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第三步：移动光标到段落

我们使用`MoveTo()` DocumentBuilder 的方法将光标移动到我们要插入字段合并字段的段落。

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## 第 4 步：插入字段合并字段

我们使用 DocumentBuilder 的`InsertField()`将字段合并字段插入段落的方法。

```csharp
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

然后，我们通过指定适当的选项来配置字段合并字段属性，例如字段名称、字段前后的文本以及垂直格式设置选项。

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;
```

最后，我们称`Update()`更新字段的方法。

```csharp
field. Update();
```

### 使用 Aspose.Words for .NET 插入字段合并字段的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//创建文档和 DocumentBuilder。
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//将光标移动到段落。
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);

//插入字段合并字段。
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);

field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;

//更新字段。
field. Update();

doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

在本例中，我们新建了一个文档，将光标移动到需要的段落，然后在文档中插入了一个字段合并字段。