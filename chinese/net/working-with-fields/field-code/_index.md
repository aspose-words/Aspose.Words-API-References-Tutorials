---
title: 字段代码
linktitle: 字段代码
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 获取 Word 文档中的字段代码和字段结果的分步指南。
type: docs
weight: 10
url: /zh/net/working-with-fields/field-code/
---

这是一个分步指南，用于解释下面的 C# 源代码，它使用 Aspose.Words for .NET 的“获取字段代码”功能。确保仔细执行每个步骤以获得所需的结果。

## 第 1 步：文档目录设置

在提供的代码中，您必须指定文档的目录。将值“YOUR DOCUMENT DIRECTORY”替换为您的文档目录的适当路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：装入文档

第一步是将文档上传到您想要获取域代码的位置。

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

请务必将“Hyperlinks.docx”替换为您自己的文件名。

## 第 3 步：浏览文档字段

我们使用一个`foreach`循环遍历文档中存在的所有字段。

```csharp
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;
}
```

在循环的每次迭代中，我们使用`GetFieldCode()`方法。我们还将字段的结果存储在一个变量中。

### 使用 Aspose.Words for .NET 获取字段代码的源代码示例

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//装入文档。
Document doc = new Document(dataDir + "Hyperlinks.docx");

//遍历文档字段。
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;

     //对字段的代码和结果做一些事情。
}
```

在此示例中，我们加载了一个文档，然后循环遍历文档中存在的所有字段。在每次迭代中，我们都得到了字段的代码和结果。您可以根据需要添加自己的逻辑来处理代码和结果字段。

我们关于使用 Aspose.Words for .NET 的“获取字段代码”功能的指南到此结束。