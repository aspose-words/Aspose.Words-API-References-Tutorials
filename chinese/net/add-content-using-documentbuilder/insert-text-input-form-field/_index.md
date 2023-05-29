---
title: 插入文本输入表单域
linktitle: 插入文本输入表单域
second_title: Aspose.Words for .NET API 参考
description: 通过此分步指南了解如何使用 Aspose.Words for .NET 将文本输入表单域插入 Word 文档。
type: docs
weight: 10
url: /zh/net/add-content-using-documentbuilder/insert-text-input-form-field/
---

在本分步指南中，我们将探讨如何使用 Aspose.Words for .NET 中的插入文本输入表单域功能，使用 C# 源代码在 Word 文档中添加和操作文本输入表单域。文本输入表单域允许用户在文档中输入自定义文本，使其成为创建交互式表单和问卷的理想选择。按照以下说明，您将能够毫不费力地在文档中插入和自定义文本输入表单域。让我们开始吧！

## Aspose.Words for .NET 插入文本输入表单字段功能介绍

Aspose.Words for .NET 中的插入文本输入表单域功能允许您以编程方式将文本输入表单域添加到您的 Word 文档中。这些表单域提供了一个交互元素，用户可以在其中输入自定义文本或数据。

## 了解使用该功能的要求

在继续实施之前，请确保您满足以下要求：

1. Aspose.Words for .NET 库安装在您的项目中。
2. C# 编程语言的基础知识。
3. 在现有 Word 文档或新文档中插入文本输入表单域。

确保具备这些先决条件才能顺利进行。

## 使用 C# 源代码实现插入文本输入表单域的分步指南

按照以下步骤使用提供的 C# 源代码实现插入文本输入表单字段功能：

### 第 1 步：初始化文档和文档生成器

首先，初始化文档和文档生成器。文档生成器是 Aspose.Words for .NET 提供的一个强大的工具，它允许我们以编程方式构建和操作 Word 文档。使用以下代码片段：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

### 第 2 步：插入文本输入表单域

接下来，我们将使用`InsertTextInput`方法。该方法接受各种参数，包括表单域的名称、表单域的类型（在本例中，`TextFormFieldType.Regular`)、默认值和最大长度。这是一个例子：

```csharp
builder.InsertTextInput("TextInput", TextFormFieldType.Regular, "", "Hello", 0);
```

上面的代码将插入一个文本输入表单域，名称为“TextInput”，默认值为“Hello”，没有最大长度限制。

### 第 3 步：保存文档

插入文本输入表单域后，使用`Save`方法。确保提供适当的文件路径：

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTextInputFormField.docx");
```

此代码将在指定位置保存带有插入的文本输入表单域的文档。

### 使用 Aspose.Words for .NET 插入文本输入表单字段的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertTextInput("TextInput", TextFormFieldType.Regular, "", "Hello", 0);

doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTextInputFormField.docx");
```
