---
title: 获取邮件合并字段名称
linktitle: 获取邮件合并字段名称
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在您的 Word 文档中获取邮件合并字段名称。
type: docs
weight: 10
url: /zh/net/working-with-fields/get-mail-merge-field-names/
---

这是一个分步指南，用于解释下面的 C# 源代码，它使用 Aspose.Words for .NET 的“获取合并字段名称”功能。确保仔细执行每个步骤以获得所需的结果。

## 第 1 步：文档目录设置

在提供的代码中，您必须指定文档的目录。将值“YOUR DOCUMENT DIRECTORY”替换为您的文档目录的适当路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：装入文档

第一步是加载要获取合并字段名称的文档。

```csharp
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");
```

请务必将“您的文档文件”替换为您自己的文件名。

## 第 3 步：获取合并字段名称

我们使用`GetFieldNames()`方法获取包含文档中存在的合并字段名称的数组。

```csharp
string[] fieldNames = doc.MailMerge.GetFieldNames();
```

这`fieldNames`变量现在包含合并字段的名称。

### 使用 Aspose.Words for .NET 获取合并字段名称的源代码示例

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//装入文档。
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");

//获取合并字段名称。
string[] fieldNames = doc.MailMerge.GetFieldNames();

//显示合并字段的数量。
Console.WriteLine("\nDocument contains " + fieldNames.Length + " merge fields.");
```

在这个例子中，我们加载了一个文档，使用`GetFieldNames()`方法，并显示文档中存在的合并字段数。

我们关于使用 Aspose.Words for .NET 的“获取合并字段名称”功能的指南到此结束。