---
title: 表单字段按名称获取
linktitle: 表单字段按名称获取
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 按名称检索和修改 Word 文档中的表单域。
type: docs
weight: 10
url: /zh/net/working-with-formfields/form-fields-get-by-name/
---

在这个循序渐进的教程中，我们将指导您如何使用 Aspose.Words for .NET 从 Word 文档中按名称检索表单字段。我们将解释提供的 C# 源代码，并向您展示如何在您自己的项目中实现它。

开始之前，请确保您已经在开发环境中安装并设置了 Aspose.Words for .NET。如果您还没有这样做，请从官方网站下载并安装该库。

## 第 1 步：初始化文档对象

首先，初始化`Document`通过提供包含表单字段的源文档的路径来对象：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");
```

## 第 2 步：检索表单域

接下来，访问`FormFields`的财产`Range`文档中的对象以检索所有表单字段：

```csharp
FormFieldCollection documentFormFields = doc.Range.FormFields;
```

您可以通过索引或名称检索表单字段。在此示例中，我们使用两种方法检索表单字段：

```csharp
FormField formField1 = documentFormFields[3]; //按索引检索
FormField formField2 = documentFormFields["Text2"]; //按名称检索
```

## 第 3 步：修改表单字段属性

检索到表单域后，您可以根据需要修改它们的属性。在这个例子中，我们改变字体大小`formField1`到 20 和字体颜色`formField2`变红：

```csharp
formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;
```

## 第 4 步：保存文档

最后，保存修改后的文件：

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

就是这样！您已使用 Aspose.Words for .NET 成功地按名称检索表单字段并在 Word 文档中修改了它们的属性。

### 使用 Aspose.Words for .NET 的按名称获取表单字段的示例源代码

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");

FormFieldCollection documentFormFields = doc.Range.FormFields;

FormField formField1 = documentFormFields[3];
FormField formField2 = documentFormFields["Text2"];

formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;

doc.Save(dataDir + "ModifiedFormFields.docx");
```

随意在您自己的项目中使用此代码，并根据您的特定要求对其进行修改。
