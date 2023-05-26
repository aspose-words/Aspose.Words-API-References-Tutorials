---
title: 在没有文档生成器的情况下插入 FieldIncludeText
linktitle: 在没有文档生成器的情况下插入 FieldIncludeText
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在您的 Word 文档中插入 FieldIncludeText 字段。
type: docs
weight: 10
url: /zh/net/working-with-fields/insert-field-include-text-without-document-builder/
---

这是一个分步指南，用于解释下面的 C# 源代码，它使用 Aspose.Words for .NET 的“插入 FieldIncludeText 字段”功能。确保仔细执行每个步骤以获得所需的结果。

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

## 第 3 步：插入 FieldIncludeText 字段

我们使用`AppendField()`方法将 FieldIncludeText 字段插入到段落中。

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

然后，我们通过指定书签的名称和源文件的名称来配置 FieldIncludeText 字段的属性。

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

接下来，我们将段落添加到文档的正文中。

```csharp
doc.FirstSection.Body.AppendChild(para);
```

最后，我们称`Update()`更新字段的方法。

```csharp
fieldIncludeText.Update();
```

### 使用 Aspose.Words for .NET 插入 FieldIncludeText 字段的源代码示例

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//创建文档和段落。
Document doc = new Document();
Paragraph para = new Paragraph(doc);

//插入 FieldIncludeText 字段。
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);

fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";

doc.FirstSection.Body.AppendChild(para);

fieldIncludeText.Update();

doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

在此示例中，我们创建了一个新文档，初始化了一个段落，插入了一个指定书签名称和源文件名的 FieldIncludeTexten，并以指定的文件名保存了文档。

我们关于使用 Aspose.Words for .NET 的“插入 FieldIncludeText”功能的指南到此结束。