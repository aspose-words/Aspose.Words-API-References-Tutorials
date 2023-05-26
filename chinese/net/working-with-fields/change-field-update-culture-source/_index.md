---
title: 更改字段更新文化来源
linktitle: 更改字段更新文化来源
second_title: Aspose.Words for .NET API 参考
description: Change Field Update Culture Source，在 Aspose.Words for .NET 中修改文化源的分步指南。
type: docs
weight: 10
url: /zh/net/working-with-fields/change-field-update-culture-source/
---

在本教程中，我们将指导您完成使用 Aspose.Words for .NET 更改 Word 文档中的字段更新文化源的过程。通过修改文化源，您可以在字段更新和邮件合并操作期间控制日期格式。我们将为您提供实现此目的所需的 C# 源代码和分步说明。

## 先决条件
在我们开始之前，请确保您具备以下先决条件：
- Aspose.Words for .NET 库安装在您的系统上。

## 第 1 步：创建文档和 DocumentBuilder
首先，创建一个 Document 类的实例和一个 DocumentBuilder 对象：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：插入具有特定语言环境的内容
接下来，将语言环境设置为德语并插入具有日期格式的字段：

```csharp
builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

在上面的代码中，我们将字体区域设置为德语（区域设置 ID 1031）并插入两个具有特定日期格式的字段。

## 第 3 步：更改字段更新文化来源
要更改字段更新文化源，请使用 FieldOptions 类：

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

在此示例中，我们将字段更新期间使用的文化设置为从该字段使用的文化中选择。

## 步骤 4：执行邮件合并
执行邮件合并操作并为“Date2”字段指定日期值：

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

在此代码片段中，我们执行邮件合并操作并为“Date2”字段提供 DateTime 值。

## 第 5 步：保存文档
使用 Document 类的 Save 方法将修改后的文档保存到文件中：

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

### 使用 Aspose.Words for .NET 更改字段更新文化源的示例源代码
以下是使用 Aspose.Words for .NET 更改 Word 文档中字段更新文化源的完整源代码：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");

doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;

doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });

doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## 结论
恭喜！您已经成功学习了如何使用 Aspose.Words for .NET 更改 Word 文档中的字段更新文化源。通过遵循分步指南并利用提供的源代码，您现在可以控制在字段更新和邮件合并操作期间用于日期格式化的区域性。根据您的要求定制培养源，以确保准确和一致的日期。