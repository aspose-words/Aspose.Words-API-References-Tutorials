---
title: 不使用文档生成器插入 TOA 字段
linktitle: 不使用文档生成器插入 TOA 字段
second_title: Aspose.Words 文档处理 API
description: 一步一步指导如何使用 Aspose.Words for .NET 无需 Document Builder 插入 TOA 字段。
type: docs
weight: 10
url: /zh/net/working-with-fields/insert-toafield-without-document-builder/
---

以下是分步指南，用于解释下面的 C# 源代码，该代码使用了 Aspose.Words for .NET 的“TOA 字段插入”功能。请仔细遵循每个步骤以获得所需的结果。

## 步骤 1：文档目录设置

在提供的代码中，您必须指定文档的目录。将值“YOUR DOCUMENT DIRECTORY”替换为您的文档目录的相应路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步骤 2：创建文档和段落

我们首先创建一个新文档并初始化一个段落。

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## 步骤 3：插入 TA 字段

我们使用 FieldTA 类将 TA 字段插入段落。

```csharp
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";
```

## 步骤 4：将段落添加到文档正文

我们将包含 TA 字段的段落添加到文档正文中。

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## 步骤 5：创建 TOA 字段的段落

我们为 TOA 字段创建一个新段落。

```csharp
para = new Paragraph(doc);
```

## 步骤 6：插入 TOA 字段

我们使用 FieldToa 类将 TOA 字段插入段落。

```csharp
FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
```

## 步骤 7：将段落添加到文档正文

我们将包含 TOA 字段的段落添加到文档正文中。

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## 步骤 8：更新 TOA 字段

最后，我们称`Update()`方法来更新TOA字段。

```csharp
fieldToa.Update();
```

### 不使用 Document Builder 和 Aspose.Words for .NET 插入 TOA 字段的源代码示例

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);

//我们希望插入如下 TA 和 TOA 字段：
// { TA \c 1 \l "值 0" }
// { 目录 \c 1 }

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

### 常见问题解答

#### 问：如何使用 Aspose.Words for .NET 自定义插入 Word 文档中的 TOA 字段的外观？

答：您可以使用`FieldTOA`对象来指定格式选项。

#### 问：我可以使用 Aspose.Words for .NET 在单个 Word 文档中添加多个 TOA 字段吗？

答：是的，您可以使用 Aspose.Words for .NET 在单个 Word 文档中添加多个 TOA 字段。只需对每个字段重复插入步骤即可。

#### 问：如何使用 Aspose.Words for .NET 检查 TOA 字段是否已成功插入到 Word 文档中？

答：要检查 TOA 字段是否成功插入，您可以浏览文档内容并搜索 TOA 字段实例。

#### 问：如果不使用 DocumentBuilder 插入 TOA 字段是否会影响使用 Aspose.Words for .NET 进行 Word 文档格式化？

答：不使用 DocumentBuilder 插入 TOA 字段不会直接影响 Word 文档的格式。但是，TOA 字段格式选项会影响文档的整体格式。