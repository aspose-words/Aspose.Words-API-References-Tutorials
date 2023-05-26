---
title: 插入表单域
linktitle: 插入表单域
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 将下拉表单字段插入到 Word 文档中。
type: docs
weight: 10
url: /zh/net/working-with-formfields/insert-form-fields/
---

在这个循序渐进的教程中，我们将指导您如何使用 Aspose.Words for .NET 将表单字段（特别是下拉表单字段）插入到 Word 文档中。我们将解释提供的 C# 源代码，并向您展示如何在您自己的项目中实现它。

要开始，请确保您已在开发环境中安装和设置 Aspose.Words for .NET。如果您还没有这样做，请从官方网站下载并安装该库。

## 步骤 1：初始化 Document 和 DocumentBuilder 对象

首先，初始化`Document`和`DocumentBuilder`对象：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：插入下拉表单域

接下来，指定下拉表单字段的选项并使用`InsertComboBox`的方法`DocumentBuilder`目的。在此示例中，我们插入一个名为“DropDown”的下拉表单字段，其中包含三个选项：“一”、“二”和“三”：

```csharp
string[] items = { "One", "Two", "Three" };
builder.InsertComboBox("DropDown", items, 0);
```

## 第 3 步：保存文档

最后，保存文件：

```csharp
doc.Save("OutputDocument.docx");
```

就是这样！您已经使用 Aspose.Words for .NET 成功地将下拉表单字段插入到 Word 文档中。

### 使用 Aspose.Words for .NET 插入表单字段的示例源代码

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

string[] items = { "One", "Two", "Three" };
builder.InsertComboBox("DropDown", items, 0);

doc.Save("OutputDocument.docx");
```

随意在您自己的项目中使用此代码，并根据您的特定要求对其进行修改。