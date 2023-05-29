---
title: Form Fields 获取表单字段集合
linktitle: Form Fields 获取表单字段集合
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 检索和操作 Word 文档中的表单字段集合。
type: docs
weight: 10
url: /zh/net/working-with-formfields/form-fields-get-form-fields-collection/
---

在这个循序渐进的教程中，我们将指导您如何使用 Aspose.Words for .NET 从 Word 文档中检索表单字段集合。我们将解释提供的 C# 源代码，并向您展示如何在您自己的项目中实现它。

要开始，请确保您已在开发环境中安装和设置 Aspose.Words for .NET。如果您还没有这样做，请从官方网站下载并安装该库。

## 第 1 步：初始化文档对象

首先，初始化`Document`通过提供包含表单字段的源文档的路径来对象：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Form fields.docx");
```

## 第 2 步：检索表单字段集合

接下来，访问`FormFields`的财产`Range`文档中的对象以检索表单字段的集合：

```csharp
FormFieldCollection formFields = doc.Range.FormFields;
```

现在，您将 Word 文档中的表单域集合存储在`formFields`多变的。

## 第 3 步：访问和操作表单字段

您可以遍历表单域集合并对每个表单域执行各种操作，例如获取或设置值、修改格式或提取信息。

```csharp
foreach (FormField formField in formFields)
{
    //访问和操作每个表单字段
    //...
}
```

## 第 4 步：保存文档

最后，如有必要，保存修改后的文档：

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

就是这样！您已经使用 Aspose.Words for .NET 成功地从 Word 文档中检索了表单域集合。

### 表单字段的示例源代码使用 Aspose.Words for .NET 获取表单字段集合

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Form fields.docx");

FormFieldCollection formFields = doc.Range.FormFields;

//根据需要访问和操作表单域
//...

doc.Save(dataDir + "ModifiedFormFields.docx");
```

随意在您自己的项目中使用此代码，并根据您的特定要求对其进行修改。