---
title: 删除字段
linktitle: 删除字段
second_title: Aspose.Words for .NET API 参考
description: 在本指南中，您将学习如何使用 Aspose.Words for .NET 删除文档中的特定字段。
type: docs
weight: 10
url: /zh/net/working-with-fields/remove-field/
---
这是一个分步指南，用于解释下面的 C# 源代码，它使用 Aspose.Words for .NET 的“字段删除”功能。仔细执行每个步骤以获得所需的结果。

## 第 1 步：文档目录设置

在提供的代码中，您必须指定文档的目录。将值“YOUR DOCUMENT DIRECTORY”替换为您的文档目录的适当路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：装入文档

我们首先从指定文件加载现有文档。

```csharp
Document doc = new Document(dataDir + "Various fields.docx");
```

## 第 3 步：删除字段

我们选择文档范围中的第一个字段并使用`Remove()`方法来删除它。

```csharp
Field field = doc.Range.Fields[0];
field. Remove();
```

## 第 4 步：保存文档

最后，我们称`Save()`保存修改文档的方法。

```csharp
doc.Save(dataDir + "WorkingWithFields.RemoveField.docx");
```

### 使用 Aspose.Words for .NET 删除字段的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//装入文档。
Document doc = new Document(dataDir + "Various fields.docx");

//选择要删除的字段。
Field field = doc.Range.Fields[0];
field. Remove();

//保存文档。
doc.Save(dataDir + "WorkingWithFields.RemoveField.docx");
```

按照以下步骤使用 Aspose.Words for .NET 删除文档中的特定字段。
