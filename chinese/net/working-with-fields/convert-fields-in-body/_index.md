---
title: 转换正文中的字段
linktitle: 转换正文中的字段
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将页面字段转换为 Word 文档正文中的文本。
type: docs
weight: 10
url: /zh/net/working-with-fields/convert-fields-in-body/
---

在这个循序渐进的教程中，我们将带您了解如何使用提供的 C# 源代码使用 Aspose.Words for .NET 的 ConvertFieldsInBody 功能。此功能允许您将文档正文中的特定字段转换为纯文本，使您的文档更易于处理。请按照以下步骤有效地使用此功能。

## 第 1 步：先决条件

在开始之前，请确保您已经安装了 Aspose.Words for .NET 并准备好处理文档。还要确保您有文档的目录路径。

## 第 2 步：装入文档

首先为文档目录的路径声明一个变量，然后使用该变量从指定的文档中初始化一个 Document 对象。在我们的示例中，该文档称为“Linked fields.docx”。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//装入文档
Document doc = new Document(dataDir + "Linked fields.docx");
```

## 第 3 步：将页面字段转换为纯文本

现在文档已加载，我们可以继续进行转换步骤。要将页面字段转换为第一部分正文中的纯文本，您可以使用`Range.Fields`方法获取指定范围内的所有字段，然后过滤掉类型的字段`FieldType.FieldPage`.然后你可以使用`ForEach`循环遍历每个字段并调用`Unlink()`方法将其转换为纯文本。

```csharp
//传递适当的参数以将页面字段转换为第一部分正文中的纯文本。
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.Unlink());
```

## 第 4 步：保存修改后的文档

将页面字段转换为纯文本后，您可以使用`Save()`方法并指定输出文件的路径和名称。在我们的示例中，我们将其保存为“WorkingWithFields.ConvertFieldsInBody.docx”。

```csharp
//保存修改后的文件
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### 使用 Aspose.Words for .NET 转换正文字段的示例源代码

以下是使用 Aspose.Words for .NET 将字段转换为正文的完整源代码示例：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//装入文档
Document doc = new Document(dataDir + "Linked fields.docx");

//传递适当的参数以将页面字段转换为第一部分正文中的纯文本。
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.A
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```