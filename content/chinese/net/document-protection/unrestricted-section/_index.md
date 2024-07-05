---
title: Word 文档中不受限制的部分
linktitle: Word 文档中不受限制的部分
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中定义不受限制的部分。
type: docs
weight: 10
url: /zh/net/document-protection/unrestricted-section/
---
在本教程中，我们将指导您完成使用 Aspose.Words for .NET 的不受限制部分功能的步骤。此功能允许您定义 Word 文档中不受保护的特定部分，即使文档的其余部分受到保护。请按照以下步骤操作：

## 步骤 1：创建文档和章节

首先创建 Document 类和 DocumentBuilder 对象的实例：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步骤 2：向文档添加内容
使用 DocumentBuilder 对象向文档添加内容并插入分节符：

```csharp
builder.Writeln("Section 1. Unprotected.");
builder. InsertBreak(BreakType. SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");
```

## 步骤 3：保护文档和章节

仅当启用文档保护且仅允许在表单字段中编辑时，部分保护才有效。您可以使用 Document 对象的 Protect() 方法来保护文档：

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

确保指定正确的保护类型并设置所需的密码。

## 步骤 4：禁用特定部分的保护

默认情况下，所有部分都受到保护，但您可以使用 Section 对象的 ProtectedForForms 属性有选择地禁用特定部分的保护：

```csharp
doc.Sections[0].ProtectedForForms = false;
```

在此示例中，第一部分的保护被禁用。

## 步骤 5：保存文档

最后保存修改后的文档：

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");
```

确保指定正确的路径和文件名以保存包含不受限制部分的文档。

### 使用 Aspose.Words for .NET 的“不受限制部分”的示例源代码

以下是使用 Aspose.Words for .NET 的不受限制部分的完整源代码：


```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//插入两个包含一些文本的部分。
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1. Unprotected.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");

//仅当文档保护开启时，部分保护才有效，并且只允许在表单字段中进行编辑。
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

//默认情况下，所有部分都受到保护，但我们可以有选择地关闭保护。
doc.Sections[0].ProtectedForForms = false;
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");

doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");

```

通过遵循这些步骤，您将能够使用 Aspose.Words for .NET 轻松地在 Word 文档中定义不受限制的部分。

## 结论

在本教程中，我们探索了 Aspose.Words for .NET 的不受限制部分功能，该功能允许 Word 文档中的特定部分保持不受保护，而文档的其余部分受到保护。按照提供的步骤，您可以轻松定义文档中的部分，用户可以自由编辑内容，同时保持对其他部分的保护。Aspose.Words for .NET 提供了强大的文档保护和自定义功能，让您可以控制 Word 文档中的编辑权限。

### Word 文档中不受限制部分的常见问题解答

#### 问：Aspose.Words for .NET 中不受限制的部分是什么？

答：Aspose.Words for .NET 中的不受限制部分是 Word 文档中不受保护的特定部分，即使文档的其余部分受到保护。这些部分允许用户修改其中的内容，同时保持对文档其余部分的保护。

#### 问：如何使用 Aspose.Words for .NET 创建不受限制的部分？

答：要使用 Aspose.Words for .NET 在 Word 文档中创建不受限制的部分，您可以按照以下步骤操作：
1. 创建一个实例`Document`类和一个`DocumentBuilder`目的。
2. 使用`DocumentBuilder`向文档添加内容并插入分节符。
3. 使用保护文档`Protect`方法`Document`对象，指定所需的保护类型和密码。
4. 通过设置禁用特定部分的保护`ProtectedForForms`相应财产`Section`反对`false`.
5. 保存修改后的文档。

#### 问：一个 Word 文档中可以有多个不受限制的部分吗？

答：是的，Word 文档中可以有多个不受限制的部分。通过选择性地禁用特定部分的保护，使用`ProtectedForForms`的财产`Section`对象，您可以定义多个部分，用户可以自由修改内容，同时保护其他部分。

#### Q4. 我可以取消对最初受保护部分的保护吗？
是的，您可以通过设置`ProtectedForForms`相应财产`Section`反对`false`。这允许用户不受任何限制地编辑该特定部分内的内容。

#### 问：Word 文档可以应用哪些保护类型？

答：Aspose.Words for .NET 提供了多种可应用于 Word 文档的保护类型，包括：
- NoProtection：不应用任何保护。
- AllowOnlyRevisions：用户只能对文档进行修改。
- AllowOnlyComments：用户只能向文档添加评论。
- AllowOnlyFormFields：用户只能编辑文档中的表单字段。
- ReadOnly：该文档是只读的，不允许编辑。


