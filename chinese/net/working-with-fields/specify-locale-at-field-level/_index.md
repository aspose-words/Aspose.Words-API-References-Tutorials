---
title: 在字段级别指定语言环境
linktitle: 在字段级别指定语言环境
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中指定字段级本地化。
type: docs
weight: 10
url: /zh/net/working-with-fields/specify-locale-at-field-level/
---

这是一个分步指南，用于解释以下 C# 源代码，该代码允许使用 Aspose.Words for .NET 功能在字段级别指定本地化。在使用此代码之前，请确保您已将 Aspose.Words 库包含在您的项目中。

## 第一步：设置文档目录路径

```csharp
//文档目录的路径。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

请务必指定保存已编辑文档的文档目录的正确路径。

## 第 2 步：创建文档生成器

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

在这里，我们正在创建一个实例`DocumentBuilder`允许我们向文档添加字段的类。

## 第 3 步：插入具有特定位置的日期字段

```csharp
Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;
```

我们使用文档生成器插入一个类型的字段`FieldType.FieldDate`到文档中。通过设置`LocaleId`财产给`1049`我们为此字段指定俄语本地化。

## 第 4 步：保存修改后的文档

```csharp
builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

最后我们将修改后的文档保存到指定位置的指定文件中。

### 使用 Aspose.Words for .NET 指定字段级本地化的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

DocumentBuilder builder = new DocumentBuilder();

Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;

builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

这是使用 Aspose.Words for .NET 在文档中的字段级别指定本地化的示例源代码。您可以使用此代码在 Word 文档中插入具有特定位置的日期字段。
