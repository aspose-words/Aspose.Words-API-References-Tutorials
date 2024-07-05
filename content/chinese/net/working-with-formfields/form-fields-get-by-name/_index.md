---
title: 按名称获取表单字段
linktitle: 按名称获取表单字段
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中按名称检索和修改表单字段。
type: docs
weight: 10
url: /zh/net/working-with-formfields/form-fields-get-by-name/
---

在本分步教程中，我们将指导您如何使用 Aspose.Words for .NET 从 Word 文档中按名称检索表单字段。我们将解释提供的 C# 源代码并向您展示如何在您自己的项目中实现它。

首先，请确保您已在开发环境中安装并设置了 Aspose.Words for .NET。如果您尚未这样做，请从下载并安装该库[Aspose.发布]https://releases.aspose.com/words/net/。

## 步骤 1：初始化文档对象

首先，初始化`Document`通过提供包含表单字段的源文档的路径来获取对象：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");
```

## 步骤 2：检索表单字段

接下来，访问`FormFields`的财产`Range`文档中的对象来检索所有表单字段：

```csharp
FormFieldCollection documentFormFields = doc.Range.FormFields;
```

您可以通过索引或名称检索表单字段。在此示例中，我们使用两种方法检索表单字段：

```csharp
FormField formField1 = documentFormFields[3]; //通过索引检索
FormField formField2 = documentFormFields["Text2"]; //按名称检索
```

## 步骤 3：修改表单字段属性

检索表单字段后，您可以根据需要修改其属性。在此示例中，我们更改了`formField1`至 20，字体颜色为`formField2`变为红色：

```csharp
formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;
```

## 步骤4：保存文档

最后保存修改后的文档：

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

就是这样！您已成功按名称检索表单字段并使用 Aspose.Words for .NET 在 Word 文档中修改了它们的属性。

### 使用 Aspose.Words for .NET 按名称获取表单字段的示例源代码

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

请随意在您自己的项目中使用此代码，并根据您的特定要求进行修改。

### 常见问题解答

#### 问：如何在 Aspose.Words 中通过名称获取表单字段？

答：要在 Aspose.Words 中按名称获取表单字段，您可以使用`Document.Range.FormFields[name]`方法。该方法返回指定名称对应的表单字段。

#### 问：如果文档中不存在指定名称的表单字段怎么办？

答：如果文档中不存在指定名称的表单字段，则`Document.Range.FormFields[name]`方法将返回`null`。您可以检查此结果来处理未找到表单字段的情况。

#### 问：如何修改找到的表单字段的属性？

答：通过名称获取表单字段后，您可以访问其各个属性来编辑它们。例如，您可以更改字段的值、启用或禁用其可见性，或者根据需要修改其他属性。

#### 问：我可以在一份文档中获取多个同名的表单字段吗？

答：是的，一个文档中可以有多个同名的表单字段。在这种情况下，`Document.Range.FormFields[name]`方法将返回找到的第一个具有指定名称的表单字段。如果您有多个同名的表单字段，则在操作字段时需要考虑到这一点。

#### 问：如何遍历文档中的所有表单字段？

答：要迭代文档中的所有表单字段，您可以使用`foreach`循环播放`Document.Range.FormFields`集合。这将允许您单独访问每个表单字段并对每个字段执行操作。