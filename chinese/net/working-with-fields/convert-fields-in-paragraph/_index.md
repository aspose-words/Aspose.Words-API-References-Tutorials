---
title: 转换段落中的字段
linktitle: 转换段落中的字段
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 将 IF 字段转换为段落中的纯文本。
type: docs
weight: 10
url: /zh/net/working-with-fields/convert-fields-in-paragraph/
---

这是一个教程，演示了如何将字段转换为段落功能与 Aspose.Words for .NET 一起使用。此代码将文档最后一段中遇到的所有 IF 类型字段转换为纯文本。请按照以下步骤理解并运行此代码。

在开始之前，确保您已经安装了 Aspose.Words for .NET 并设置了您的开发环境。

## 第 1 步：导入引用

要在您的项目中使用 Aspose.Words，您需要添加必要的引用。确保您已在项目中添加对 Aspose.Words 库的引用。

## 第 2 步：装入文档

在您可以转换字段之前，您必须加载包含要转换的字段的文档。请务必指定包含文档的目录的正确路径。上传文档的方法如下：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//装入文档。
Document doc = new Document(dataDir + "Linked fields.docx");
```

将“您的文档目录”替换为文档目录的实际路径。

## 第 3 步：将字段转换为文本

现在文档已加载，我们可以继续将类型字段转换为纯文本。在此示例中，我们仅针对文档最后一段中出现的字段。下面是执行此转换的代码：

```csharp
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());
```

此代码使用 LINQ 方法的组合来过滤掉文档最后一段中的字段，然后通过调用将其转换为纯文本`Unlink()`方法。

## 第 4 步：保存修改后的文档

转换字段后，您可以保存修改后的文档。使用`Save()`为此的方法。这是一个例子：

```csharp
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

请务必为备份指定正确的路径和文件名。

### 使用 Aspose.Words for .NET 转换段落中的字段的源代码示例

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//装入文档。
Document doc = new Document(dataDir + "Linked fields.docx");

//在文档的最后一段中将 IF 字段转换为纯文本。
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());

//保存修改后的文档。
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```
