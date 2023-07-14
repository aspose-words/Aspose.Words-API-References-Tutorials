---
title: 插入作者字段
linktitle: 插入作者字段
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中插入作者字段。指定作者姓名以个性化您的文档。
type: docs
weight: 10
url: /zh/net/working-with-fields/insert-author-field/
---


以下是解释下面 C# 源代码的分步指南，该源代码使用 Aspose.Words for .NET 的“插入作者字段”功能。确保仔细执行每个步骤以获得所需的结果。

## 第 1 步：文档目录设置

在提供的代码中，您必须指定文档的目录。将值“YOUR DOCUMENT DIRECTORY”替换为文档目录的相应路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：创建文档和段落

我们首先创建一个新文档并获取第一段。

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## 第 3 步：插入作者字段

我们使用`AppendField()`方法将 AUTHOR 字段插入到段落中。

```csharp
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);
```

然后我们配置该字段的`AuthorName`属性来指定作者姓名。

```csharp
field. AuthorName = "Test1";
```

最后，我们调用`Update()`更新字段的方法。

```csharp
field. Update();
```

### 使用 Aspose.Words for .NET 插入 AUTHOR 字段的源代码示例

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//文档创建。
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

//插入作者字段。
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);

field. AuthorName = "Test1";

field. Update();

doc.Save(dataDir + "InsertionAuthorField.docx");
```

在此示例中，我们创建了一个新文档，插入了 AUTHOR 字段，配置了作者姓名，并使用指定的文件名保存了文档。

我们关于使用 Aspose.Words for .NET 的“插入作者字段”功能的指南到此结束。

### 常见问题解答

#### 问：Aspose.Words 中的作者字段是什么？

答：Aspose.Words 中的作者字段是一个特殊字段，可自动在 Word 文档中插入和更新作者姓名。它通常用于指示谁创建或修改了文档。

#### 问：如何使用 Aspose.Words 更新 Word 文档中的作者字段？

答：Word 文档中的作者字段可以更新以反映当前作者的姓名。为此，您可以使用 Document 类中提供的 UpdateFields 方法。此方法将更新文档中的所有字段，包括作者字段。

#### 问：Word文档中作者字段的格式可以自定义吗？

答：是的，可以自定义Word文档中作者字段的格式。默认情况下，作者字段仅显示作者姓名。但是，您可以使用 Aspose.Words 中提供的格式选项添加其他信息，例如修改日期和时间。

#### 问：作者字段对作者姓名的后续更改是否敏感？

答：是的，作者字段对作者姓名的后续更改很敏感。如果您更改文档属性中的作者姓名，则在更新文档字段时，作者字段将自动更新为新名称。