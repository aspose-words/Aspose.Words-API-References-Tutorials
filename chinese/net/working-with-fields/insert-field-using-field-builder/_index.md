---
title: 使用字段生成器插入字段
linktitle: 使用字段生成器插入字段
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将自定义字段插入到您的 Word 文档中。
type: docs
weight: 10
url: /zh/net/working-with-fields/insert-field-using-field-builder/
---

这是一个分步指南，用于解释下面的 C# 源代码，它使用 Aspose.Words for .NET 的“使用 FieldBuilder 插入字段”功能。确保仔细执行每个步骤以获得所需的结果。

## 第 1 步：文档目录设置

在提供的代码中，您必须指定文档的目录。将值“YOUR DOCUMENT DIRECTORY”替换为您的文档目录的适当路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：创建文档

我们首先创建一个新文档。

```csharp
Document doc = new Document();
```

## 第 3 步：使用 FieldBuilder 构建 IF 字段

我们使用 FieldBuilder 类来构造一个具有两个嵌套 MERGEFIELD 字段的 IF 字段。在此示例中，IF 字段根据条件显示名字和姓氏。

```csharp
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));
```

## 第 4 步：将 IF 域插入文档

我们使用`BuildAndInsert()`在文档中的特定位置构建和插入 IF 字段的方法。

```csharp
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();
```

### 使用 FieldBuilder 和 Aspose.Words for .NET 插入字段的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//文档创建。
Document doc = new Document();

//使用 FieldBuilder 构建 IF 字段。
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));

//将 IF 域插入到文档中。
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();

doc.Save(dataDir + "InsertFieldWithFieldBuilder.docx");
```

在此示例中，我们创建了一个新文档，构造了一个带有嵌套 MERGEFIELD 字段的 IF 字段，然后将该字段插入到文档的指定位置。然后以特定文件名保存该文档。
