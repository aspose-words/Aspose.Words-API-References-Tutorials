---
title: 转换正文中的字段
linktitle: 转换正文中的字段
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 将页面字段转换为 Word 文档正文中的文本。
type: docs
weight: 10
url: /zh/net/working-with-fields/convert-fields-in-body/
---

在本分步教程中，我们将引导您了解如何使用提供的 C# 源代码使用 Aspose.Words for .NET 的 ConvertFieldsInBody 功能。此功能允许您将文档正文中的特定字段转换为纯文本，使您的文档更易于处理。请按照以下步骤有效地使用此功能。

## 第 1 步：先决条件

在开始之前，请确保您已安装 Aspose.Words for .NET 并准备好可以处理的文档。另请确保您拥有文档的目录路径。

## 第 2 步：加载文档

首先为文档目录的路径声明一个变量，然后使用该变量从指定文档初始化 Document 对象。在我们的示例中，该文档称为“Linked fields.docx”。

```csharp
//您的文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载文档
Document doc = new Document(dataDir + "Linked fields.docx");
```

## 步骤 3：将页面字段转换为纯文本

现在文档已加载，我们可以继续进行转换步骤。要将第一部分正文中的页面字段转换为纯文本，您可以使用`Range.Fields`方法获取指定范围内的所有字段，然后过滤掉type的字段`FieldType.FieldPage`。然后您可以使用`ForEach`方法循环遍历每个字段并调用`Unlink()`方法将其转换为纯文本。

```csharp
//传递适当的参数以将第一部分正文中的页面字段转换为纯文本。
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.Unlink());
```

## 第四步：保存修改后的文档

将页面字段转换为纯文本后，您可以使用以下命令保存修改后的文档：`Save()`方法并指定输出文件的路径和名称。在我们的示例中，我们将其保存为“WorkingWithFields.ConvertFieldsInBody.docx”。

```csharp
//保存修改后的文档
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### 使用 Aspose.Words for .NET 转换正文中字段的示例源代码

以下是使用 Aspose.Words for .NET 将字段转换为正文的完整源代码示例：

```csharp
//您的文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载文档
Document doc = new Document(dataDir + "Linked fields.docx");

//传递适当的参数以将第一部分正文中的页面字段转换为纯文本。
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.A
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### 常见问题解答

#### 问：Aspose.Words 是否与不同版本的 Microsoft Word 兼容？

答：是的，Aspose.Words 与 Microsoft Word 的各个版本兼容，包括 Word 2003、Word 2007、Word 2010、Word 2013、Word 2016 和 Word 2019。

#### 问：Aspose.Words 可以处理复杂的字段结构吗？

答：当然！ Aspose.Words 为复杂的字段结构提供广泛的支持，包括嵌套字段、计算和条件表达式。您可以利用强大的 API 来处理任何类型的字段结构。

#### 问：Aspose.Words 支持字段更新操作吗？

答：是的，Aspose.Words 允许您以编程方式更新字段。您可以使用 API 轻松更新字段值、刷新计算以及执行其他与字段相关的操作。

#### 问：我可以使用 Aspose.Words 将字段转换为纯文本吗？

答：当然可以！ Aspose.Words 提供了将字段转换为纯文本的方法。当您需要提取没有任何字段相关格式或功能的内容时，这非常有用。

#### 问：是否可以使用 Aspose.Words 生成带有动态字段的 Word 文档？

答：当然！ Aspose.Words 提供了强大的功能来生成带有动态字段的 Word 文档。您可以使用预定义字段创建模板并动态填充数据，从而提供灵活高效的文档生成解决方案。