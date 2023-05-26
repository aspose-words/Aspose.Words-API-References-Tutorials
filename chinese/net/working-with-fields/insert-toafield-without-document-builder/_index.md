---
title: 在没有文档生成器的情况下插入 TOA 字段
linktitle: 在没有文档生成器的情况下插入 TOA 字段
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 的分步指南，无需文档生成器即可插入 TOA 字段。
type: docs
weight: 10
url: /zh/net/working-with-fields/insert-toafield-without-document-builder/
---

这是一个分步指南，用于解释下面的 C# 源代码，它使用 Aspose.Words for .NET 的“TOA 字段插入”功能。仔细执行每个步骤以获得所需的结果。

## 第 1 步：文档目录设置

在提供的代码中，您必须指定文档的目录。将值“YOUR DOCUMENT DIRECTORY”替换为您的文档目录的适当路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：创建文档和段落

我们首先创建一个新文档并初始化一个段落。

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## 第 3 步：插入 TA 字段

我们使用 FieldTA 类在段落中插入一个 TA 字段。

```csharp
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";
```

## 第 4 步：将段落添加到文档正文

我们将包含 TA 字段的段落添加到文档的正文中。

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## 第 5 步：为 TOA 字段创建段落

我们为 TOA 字段创建一个新段落。

```csharp
para = new Paragraph(doc);
```

## 第 6 步：插入 TOA 字段

我们使用 FieldToa 类将 TOA 字段插入到段落中。

```csharp
FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
```

## 第 7 步：将段落添加到文档正文

我们将包含 TOA 字段的段落添加到文档的正文中。

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## 步骤 8：更新 TOA 字段

最后，我们称`Update()`更新 TOA 字段的方法。

```csharp
fieldToa.Update();
```

### 使用 Aspose.Words for .NET 的不带文档生成器的 TOA 字段插入的源代码示例

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);

//我们想像这样插入 TA 和 TOA 字段：
// { TA \c 1 \l "值 0" }
// { TOA \c 1 }

FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);

para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);

fieldToa.Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```
