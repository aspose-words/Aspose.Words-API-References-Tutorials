---
title: 重命名合并字段
linktitle: 重命名合并字段
second_title: Aspose.Words for .NET API 参考
description: 在本教程中，您将学习如何使用 Aspose.Words for .NET 重命名文档中的合并字段。
type: docs
weight: 10
url: /zh/net/working-with-fields/rename-merge-fields/
---

这是一个逐步指南，用于解释下面的 C# 源代码，它使用 Aspose.Words for .NET 的合并字段重命名功能。仔细执行每个步骤以获得所需的结果。

## 第 1 步：文档目录设置

在提供的代码中，您必须指定文档的目录。将值“YOUR DOCUMENT DIRECTORY”替换为您的文档目录的适当路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：创建文档并插入合并域

我们首先创建一个新文档并使用`DocumentBuilder`插入合并字段。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");
```

## 第 3 步：重命名合并字段

我们遍历文档范围内的每个字段，如果它是一个合并字段，我们通过添加“_重命名”后缀。

```csharp
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}
```

## 第 4 步：保存文档

最后，我们称`Save()`保存修改文档的方法。

```csharp
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

### 使用 Aspose.Words for .NET 重命名合并字段的源代码示例

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//创建文档并插入合并域。
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");

//重命名合并字段。
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}

//保存文档。
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

按照以下步骤使用 Aspose.Words for .NET 重命名文档中的合并字段。