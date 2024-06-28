---
title: 插入字段包括文本而不使用文档生成器
linktitle: 在没有文档生成器的情况下插入 FieldIncludeText
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中插入 FieldIncludeText 字段。
type: docs
weight: 10
url: /zh/net/working-with-fields/insert-field-include-text-without-document-builder/
---

以下是解释下面 C# 源代码的分步指南，该源代码使用 Aspose.Words for .NET 的“插入 FieldIncludeText 字段”功能。确保仔细执行每个步骤以获得所需的结果。

## 第 1 步：文档目录设置

在提供的代码中，您必须指定文档的目录。将值“YOUR DOCUMENT DIRECTORY”替换为文档目录的相应路径。

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

接下来，我们将该段落添加到文档正文中。

```csharp
doc.FirstSection.Body.AppendChild(para);
```

最后，我们调用`Update()`更新字段的方法。

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

在此示例中，我们创建了一个新文档，初始化了一个段落，插入了一个指定书签名称和源文件名的 FieldIncludeTexten，并使用指定的文件名保存了文档。

我们关于使用 Aspose.Words for .NET 的“插入 FieldIncludeText”功能的指南到此结束。

### 常见问题解答

#### 问：如何在 Aspose.Words for .NET 中指定文本包含字段的源文件？

答：要指定 Aspose.Words for .NET 中文本包含字段的源文件，您可以使用`FieldIncludeText.SourceFullName`属性设置源文件的完整路径。确保源文件可访问并且包含要包含在文本包含字段中的内容。

#### 问：我可以使用 Aspose.Words for .NET 在文本包含字段中包含宏中的文本吗？

答：是的，您可以使用 Aspose.Words for .NET 将宏中的文本包含在文本包含字段中。您可以使用`FieldIncludeText.IncludeText`属性来指定其内容应包含在字段中的宏的名称。

#### 问：在没有文档生成器的情况下插入文本包含字段是否会影响 Aspose.Words for .NET 的 Word 文档结构？

答：在没有文档生成器的情况下插入文本包含字段不会直接影响 Word 文档的结构。但是，它向文档内容添加了一个新的字段元素。您可以根据需要通过添加、删除或修改现有元素来操作文档结构。

#### 问：我可以使用 Aspose.Words for .NET 自定义 Word 文档中文本包含字段的外观吗？

答：文本字段包含不会直接自定义其在 Word 文档中的外观。但是，您可以使用段落属性、字体属性和 Aspose.Words for .NET 中提供的其他格式对象来格式化包含的文本。