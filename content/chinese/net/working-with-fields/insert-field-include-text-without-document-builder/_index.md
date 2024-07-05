---
title: 插入字段包含文本（无需文档生成器）
linktitle: 不使用文档生成器插入 FieldIncludeText
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中插入 FieldIncludeText 字段。
type: docs
weight: 10
url: /zh/net/working-with-fields/insert-field-include-text-without-document-builder/
---

以下是分步指南，用于解释下面的 C# 源代码，该代码使用了 Aspose.Words for .NET 的“插入 FieldIncludeText 字段”功能。请务必仔细遵循每个步骤以获得所需的结果。

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

## 步骤 3：插入 FieldIncludeText 字段

我们使用`AppendField()`方法将 FieldIncludeText 字段插入到段落中。

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

然后我们通过指定书签的名称和源文件的名称来配置 FieldIncludeText 字段的属性。

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

接下来，我们将该段落添加到文档正文中。

```csharp
doc.FirstSection.Body.AppendChild(para);
```

最后，我们称`Update()`方法来更新字段。

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

在这个例子中，我们创建了一个新文档，初始化了一个段落，插入了一个指定书签名称和源文件名的FieldIncludeTexten，并以指定的文件名保存了该文档。

这就是我们关于使用 Aspose.Words for .NET 的“插入 FieldIncludeText”功能的指南。

### 常见问题解答

#### 问：如何在 Aspose.Words for .NET 中指定文本包含字段的源文件？

答：要在 Aspose.Words for .NET 中指定文本包含字段的源文件，您可以使用`FieldIncludeText.SourceFullName`属性来设置源文件的完整路径。确保源文件可访问且包含您想要包含在文本包含字段中的内容。

#### 问：我可以使用 Aspose.Words for .NET 在文本包含字段中包含来自宏的文本吗？

答：是的，您可以使用 Aspose.Words for .NET 在文本包含字段中包含来自宏的文本。您可以使用`FieldIncludeText.IncludeText`属性来指定应包含在字段中的宏的名称。

#### 问：在没有文档生成器的情况下插入文本包含字段是否会影响使用 Aspose.Words for .NET 的 Word 文档结构？

答：不使用文档生成器插入文本包含字段不会直接影响 Word 文档的结构。但是，它会向文档内容添加新的字段元素。您可以根据需要通过添加、删除或修改现有元素来操纵文档结构。

#### 问：我可以使用 Aspose.Words for .NET 自定义 Word 文档中文本包含字段的外观吗？

答：文本包含字段不会直接自定义其在 Word 文档中的外观。但是，您可以使用 Aspose.Words for .NET 中提供的段落属性、字体属性和其他格式化对象来格式化包含的文本。