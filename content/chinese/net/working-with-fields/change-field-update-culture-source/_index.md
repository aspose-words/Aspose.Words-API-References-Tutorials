---
title: 更改字段更新文化源
linktitle: 更改字段更新文化源
second_title: Aspose.Words 文档处理 API
description: 更改字段更新文化源，在 Aspose.Words for .NET 中修改文化源的分步指南。
type: docs
weight: 10
url: /zh/net/working-with-fields/change-field-update-culture-source/
---

在本教程中，我们将指导您完成使用 Aspose.Words for .NET 更改 Word 文档中的字段更新区域性源的过程。通过修改区域性源，您可以在字段更新和邮件合并操作期间控制日期格式。我们将为您提供实现这一目标所需的 C# 源代码和分步说明。

## 先决条件
在我们开始之前，请确保您满足以下先决条件：
- Aspose.Words for .NET 库安装在您的系统上。

## 第 1 步：创建文档和 DocumentBuilder
首先，创建 Document 类的实例和 DocumentBuilder 对象：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：插入具有特定区域设置的内容
接下来，将区域设置设置为德语并插入具有日期格式的字段：

```csharp
builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

在上面的代码中，我们将字体区域设置设置为德语（区域设置 ID 1031），并插入两个具有特定日期格式的字段。

## 第3步：更改字段更新文化源
要更改字段更新区域性源，请使用 FieldOptions 类：

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

在此示例中，我们将字段更新期间使用的区域性设置为从字段使用的区域性中选择。

## 步骤 4：执行邮件合并
执行邮件合并操作并指定“Date2”字段的日期值：

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

在此代码片段中，我们执行邮件合并操作并为“Date2”字段提供日期时间值。

## 第 5 步：保存文档
使用 Document 类的 Save 方法将修改后的文档保存到文件中：

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

### 使用 Aspose.Words for .NET 更改字段更新文化源的示例源代码
以下是使用 Aspose.Words for .NET 更改 Word 文档中的字段更新区域性源的完整源代码：

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
恭喜！您已成功学习如何使用 Aspose.Words for .NET 更改 Word 文档中的字段更新区域性源。通过遵循分步指南并利用提供的源代码，您现在可以控制字段更新和邮件合并操作期间用于日期格式的区域性。根据您的要求定制培养源，以确保数据准确一致。

### 常见问题解答

#### 问：如何更改 Aspose.Words for .NET 中的字段更新区域性源？

答：要更改 Aspose.Words for .NET 中的字段更新区域性源，您可以使用`Document.FieldOptions.CultureSource`属性并将其值设置为`FieldCultureSource.FieldCode`或者`FieldCultureSource.CurrentThread`。例如，您可以使用`document.FieldOptions.CultureSource = FieldCultureSource.FieldCode`使用字段代码中定义的区域性。

#### 问：如何指定特定区域性来更新 Aspose.Words for .NET 中的字段？

答：要指定用于更新 Aspose.Words for .NET 中字段的特定区域性，您可以使用`Document.FieldOptions.FieldUpdateCultureInfo`属性并设置`CultureInfo`与所需文化相对应的对象。例如，您可以使用`document.FieldOptions.FieldUpdateCultureInfo = new CultureInfo("fr-FR")`指定法国（法国）文化。

#### 问：是否可以在 Aspose.Words for .NET 中禁用自动字段更新？

答：是的，可以在 Aspose.Words for .NET 中禁用自动字段更新。您可以使用`Document.FieldOptions.UpdateFields`属性并将其设置为`false`以防止字段自动更新。这允许您根据需要手动控制字段的更新。

#### 问：如何手动更新 Aspose.Words for .NET 中的文档字段？

答：要在 Aspose.Words for .NET 中手动更新文档中的字段，您可以使用`Field.Update`分别针对每个字段的方法。例如，您可以使用`field.Update()`更新特定字段。