---
title: 转换文档中的字段
linktitle: 转换文档中的字段
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 将文档字段转换为文本的分步指南。
type: docs
weight: 10
url: /zh/net/working-with-fields/convert-fields-in-document/
---

在本教程中，我们将逐步指导您使用 Aspose.Words for .NET 软件的 ConvertFieldsInDocument 功能。我们将详细解释此功能所需的 C# 源代码，并提供示例降价输出格式。

## 第 1 步：先决条件
在开始之前，请确保您具备以下条件：

- Aspose.Words for .NET 安装在你的开发机器上。
- 包含要转换为文本的链接字段的 Word 文档。
- 一个文档目录，您可以在其中保存转换后的文档。

## 第 2 步：设置环境
确保您已正确配置开发环境以使用 Aspose.Words for .NET。导入必要的命名空间并设置文档目录的路径。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 3 步：装入文档
使用`Document`Aspose.Words 类加载包含要转换的链接字段的 Word 文档。

```csharp
Document doc = new Document(MyDir + "Linked fields.docx");
```

## 第 4 步：将绑定字段转换为文本
使用`Unlink()`将文档中遇到的所有“IF”类型字段转换为文本的方法。此方法用于将链接字段转换为其文本内容。

```csharp
doc.Range.Fields.Where(f => f.Type == FieldType.FieldIf).ToList().ForEach(f => f.Unlink());
```

## 第 5 步：保存转换后的文档
使用`Save()`方法将字段转换为文本的文档保存在指定的文档目录中。

```csharp
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInDocument.docx");
```

## 使用 Aspose.Words for .NET 的 ConvertFieldsInDocument 示例源代码

以下是 ConvertFieldsInDocument 函数的完整源代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(MyDir + "Linked fields.docx");

//传递适当的参数以将文档中遇到的所有 IF 字段（包括页眉和页脚）转换为文本。
doc.Range.Fields.Where(f => f.Type == FieldType.FieldIf).ToList().ForEach(f => f.Unlink());

//将包含已转换字段的文档保存到磁盘
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInDocument.docx");
```

## 结论
Aspose.Words for .NET 的 ConvertFieldsInDocument 函数是将 Word 文档中的链接字段转换为文本的强大工具。 