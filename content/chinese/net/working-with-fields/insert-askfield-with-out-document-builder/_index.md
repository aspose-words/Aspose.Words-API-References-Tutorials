---
title: 不使用文档生成器插入 ASKField
linktitle: 不使用文档生成器插入 ASKField
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中插入 ASK 字段。
type: docs
weight: 10
url: /zh/net/working-with-fields/insert-askfield-with-out-document-builder/
---

以下是分步指南，用于解释下面的 C# 源代码，该代码使用了 Aspose.Words for .NET 的“插入不带 DocumentBuilder 的 ASK 字段”功能。请务必仔细遵循每个步骤以获得所需的结果。

## 步骤 1：文档目录设置

在提供的代码中，您必须指定文档的目录。将值“YOUR DOCUMENT DIRECTORY”替换为您的文档目录的相应路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步骤 2：创建文档和段落

我们首先创建一个新文档并获取第一段。

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## 步骤 3：插入 ASK 字段

我们使用`AppendField()`方法将 ASK 字段插入段落。

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

然后，我们通过指定所需的值来配置 ASK 字段的各种属性。

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

最后，我们称`Update()`方法来更新字段。

```csharp
field. Update();
```

### 使用 Aspose.Words for .NET 插入 ASK 字段（无需 DocumentBuilder）的源代码示例

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//文档创建。
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

//插入 ASK 字段。
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

在这个例子中，我们创建了一个新文档，插入了一个 ASK 字段（没有使用 DocumentBuilder），配置了该字段的各种属性，并使用指定的文件名保存了该文档。

这就是我们关于使用 Aspose.Words for .NET 的“不使用 DocumentBuilder 插入 ASK 字段”功能的指南。

### 常见问题解答

#### 问：Aspose.Words 中的 ASK 字段是什么？

答：Aspose.Words 中的 ASK 字段用于在打开文档时向用户询问问题。它通常用于请求特定信息或反馈，具体信息或反馈可能因用户而异。

#### 问：如何在不使用 Aspose.Words 中的文档生成器的情况下在 Word 文档中插入 ASK 字段？

答：要在 Word 文档中插入 ASK 字段而不使用 Aspose.Words 中的 Document Builder，您可以按照以下步骤操作：

1. 从 Aspose.Words.Fields 命名空间导入 Document 和 Field 类。
2. 通过加载现有文档来创建 Document 的实例。
3. 使用 InsertField 方法通过指定问题名称插入 ASK 字段。
4. 保存文档。

#### 问：如何获取 Word 文档中 ASK 字段的用户响应？

答：要获取用户对 Word 文档中 ASK 字段的响应，您可以使用 Document 类中提供的 GetFieldNames 方法。此方法返回文档中存在的字段名称列表。然后，您可以检查列表中是否存在 ASK 字段名称并检索相关响应。

#### 问：ASK 字段可以用来向用户请求更多信息吗？

答：是的，ASK 字段可用于向用户请求多条信息。您可以在文档中插入多个 ASK 字段，每个字段包含不同的问题。打开文档时，系统会提示用户输入相应的答案。