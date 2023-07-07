---
title: 不受限制的可编辑区域
linktitle: 不受限制的可编辑区域
second_title: Aspose.Words for .NET API 参考
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


