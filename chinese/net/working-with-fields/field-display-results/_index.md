---
title: 现场显示结果
linktitle: 现场显示结果
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 在 Word 文档中显示字段结果的分步指南。
type: docs
weight: 10
url: /zh/net/working-with-fields/field-display-results/
---

这是一个分步指南，用于解释下面的 C# 源代码，它使用 Aspose.Words for .NET 的“显示字段结果”功能。确保仔细执行每个步骤以获得所需的结果。

## 第 1 步：文档目录设置

在提供的代码中，您必须指定文档的目录。将值“YOUR DOCUMENT DIRECTORY”替换为您的文档目录的适当路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：装入文档

第一步是加载要在其中显示字段结果的文档。

```csharp
Document document = new Document(dataDir + "Miscellaneous fields.docx");
```

请务必将“Miscellaneous Fields.docx”替换为您自己的文件名。

## 第 3 步：更新字段

我们使用`UpdateFields()`更新文档中所有字段的方法。

```csharp
document. UpdateFields();
```

此步骤很重要，因为它可确保正确显示字段结果。

## 第 4 步：显示字段结果

我们使用一个`foreach`loop 循环遍历文档中的所有字段并显示它们的结果。

```csharp
foreach(Field field in document.Range.Fields)
     Console.WriteLine(field.DisplayResult);
```

在循环的每次迭代中，我们访问`DisplayResult`字段的属性以获取显示的结果。

### 使用 Aspose.Words for .NET 显示字段结果的源代码示例

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//装入文档。
Document document = new Document(dataDir + "Miscellaneous fields.docx");

//更新字段。
document. UpdateFields();

//显示现场结果。
foreach(Field field in document.Range.Fields)
     Console.WriteLine(field.DisplayResult);
```

在此示例中，我们上传了一个文档，更新了所有字段，然后循环显示这些字段以显示它们的结果。您可以使用自己的逻辑来自定义此步骤以处理字段结果。

我们的关于使用 Aspose.Words for .NET 的“显示字段结果”功能的指南到此结束。