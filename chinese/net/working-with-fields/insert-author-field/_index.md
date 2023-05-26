---
title: 插入作者字段
linktitle: 插入作者字段
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在您的 Word 文档中插入作者字段。指定作者姓名以个性化您的文档。
type: docs
weight: 10
url: /zh/net/working-with-fields/insert-author-field/
---


这是一个分步指南，用于解释下面的 C# 源代码，它使用 Aspose.Words for .NET 的“插入作者字段”功能。确保仔细执行每个步骤以获得所需的结果。

## 第 1 步：文档目录设置

在提供的代码中，您必须指定文档的目录。将值“YOUR DOCUMENT DIRECTORY”替换为您的文档目录的适当路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：创建文档和段落

我们首先创建一个新文档并获取第一段。

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## 第 3 步：插入 AUTHOR 字段

我们使用`AppendField()`在段落中插入 AUTHOR 字段的方法。

```csharp
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);
```

然后我们配置字段的`AuthorName`属性来指定作者的名字。

```csharp
field. AuthorName = "Test1";
```

最后，我们称`Update()`更新字段的方法。

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

在本例中，我们创建了一个新文档，插入了一个 AUTHOR 字段，配置了作者姓名，并以指定的文件名保存了该文档。

我们关于使用 Aspose.Words for .NET 的“插入作者字段”功能的指南到此结束。
