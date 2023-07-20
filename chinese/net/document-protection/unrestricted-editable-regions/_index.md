---
title: Word 文档中不受限制的可编辑区域
linktitle: Word 文档中不受限制的可编辑区域
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中创建不受限制的可编辑区域。
type: docs
weight: 10
url: /zh/net/document-protection/unrestricted-editable-regions/
---
在本教程中，我们将指导您完成使用 Aspose.Words for .NET 的无限制可编辑区域功能的步骤。此功能使您可以在 Word 文档中定义可以不受限制地编辑内容的区域，即使文档的其余部分是只读的也是如此。请按照以下步骤操作：

## 第1步：加载文档并设置保护

首先加载现有文档：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
doc.Protect(ProtectionType.ReadOnly, "MyPassword");
```

通过设置只读保护类型和密码来保护文档

## 第二步：创建可编辑区域

首先使用 EditableRangeStart 和 EditableRangeEnd 对象创建可编辑区域：

```csharp
EditableRangeStart edRangeStart = builder.StartEditableRange();
//为我们刚刚创建的 EditableRangeStart 创建一个 EditableRange 对象。
EditableRange editableRange = edRangeStart.EditableRange;

//将某些内容放入可编辑范围内。
builder.Writeln("Paragraph inside first editable range");

//如果可编辑范围有开头和结尾，则它是格式良好的。
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

```

## 步骤 3：在可编辑区域之外添加内容

您可以在可编辑区域之外添加内容，该区域将保持只读状态：

```csharp
builder.Writeln("This paragraph is outside of all editable areas and cannot be edited.");
```

## 步骤 4：保存文档

最后保存修改后的文档：

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");
```

请务必指定正确的路径和文件名以保存具有可编辑区域的文档。

### 使用 Aspose.Words for .NET 的无限制可编辑区域的示例源代码

以下是使用 Aspose.Words for .NET 的无限制可编辑区域的完整源代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//上传文档并将其设置为只读。
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

doc.Protect(ProtectionType.ReadOnly, "MyPassword");

builder.Writeln("Hello world! Since we have set the document's protection level to read-only, " + "we cannot edit this paragraph without the password.");

//开始一个可编辑范围。
EditableRangeStart edRangeStart = builder.StartEditableRange();
//为我们刚刚创建的 EditableRangeStart 创建一个 EditableRange 对象。
EditableRange editableRange = edRangeStart.EditableRange;

//将某些内容放入可编辑范围内。
builder.Writeln("Paragraph inside first editable range");

//如果可编辑范围有开头和结尾，则它是格式良好的。
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

builder.Writeln("This paragraph is outside any editable ranges, and cannot be edited.");

doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");

```
通过执行以下步骤，您可以使用 Aspose.Words for .NET 在 Word 文档中轻松创建不受限制的可编辑区域。

## 结论
在本教程中，我们学习了如何使用 Aspose.Words for .NET 在 Word 文档中创建不受限制的可编辑区域。通过执行提供的步骤，您可以定义文档中的特定区域，用户可以在其中自由编辑内容，同时保持文档的其余部分为只读。 Aspose.Words for .NET 提供强大的文档保护和自定义功能，让您可以控制 Word 文档的编辑功能。

### Word 文档中不受限制的可编辑区域的常见问题解答

#### 问：Aspose.Words for .NET 中的不受限制的可编辑区域是什么？

答：Aspose.Words for .NET 中的无限制可编辑区域是 Word 文档中可以不受任何限制地编辑内容的区域，即使文档的其余部分设置为只读也是如此。这些区域提供了一种定义文档特定部分的方法，用户可以在维护整体文档保护的同时修改这些部分。

#### 问：如何使用 Aspose.Words for .NET 创建不受限制的可编辑区域？

答：要使用 Aspose.Words for .NET 在 Word 文档中创建不受限制的可编辑区域，您可以按照以下步骤操作：
1. 使用加载现有文档`Document`班级。
2. 使用以下命令将文档保护设置为只读`Protect`的方法`Document`目的。
3. 使用`DocumentBuilder`类通过添加创建可编辑范围`EditableRangeStart`对象和一个`EditableRangeEnd`目的。
4. 使用以下命令添加可编辑范围内的内容`DocumentBuilder`.
5. 使用以下命令保存修改后的文档`Save`的方法`Document`目的。

#### 问：Word 文档中可以有多个不受限制的可编辑区域吗？

答：是的，Word 文档中可以有多个不受限制的可编辑区域。为了实现这一点，您可以创建多组`EditableRangeStart`和`EditableRangeEnd`对象使用`DocumentBuilder`班级。每组对象将定义一个单独的可编辑区域，用户可以在其中不受任何限制地修改内容。

#### 问：我可以将可编辑区域嵌套在一起吗？

答：不可以，您不能使用 Aspose.Words for .NET 将可编辑区域嵌套在一起。每个可编辑区域由`EditableRangeStart`和`EditableRangeEnd`对应该是独立的，不能重叠或嵌套在另一个可编辑区域内。不支持嵌套的可编辑区域。

#### 问：我可以取消可编辑区域内文档的只读保护吗？

答：不可以，您无法删除可编辑区域内文档的只读保护。只读保护应用于整个文档，并且不能在特定的可编辑区域内有选择地删除。可编辑区域的目的是允许修改内容，同时保持整个文档只读。