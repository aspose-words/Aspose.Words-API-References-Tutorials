---
title: 插入嵌套字段
linktitle: 插入嵌套字段
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 轻松地将嵌套字段插入到您的 Word 文档中。
type: docs
weight: 10
url: /zh/net/working-with-fields/insert-nested-fields/
---

这是一个分步指南，用于解释下面的 C# 源代码，它使用 Aspose.Words for .NET 的“插入嵌套字段”功能。确保仔细执行每个步骤以获得所需的结果。

## 第 1 步：文档目录设置

在提供的代码中，您必须指定文档的目录。将值“YOUR DOCUMENT DIRECTORY”替换为您的文档目录的适当路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：创建文档和 DocumentBuilder

我们首先创建一个新文档并初始化一个 DocumentBuilder。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 3 步：插入分页符

我们使用循环在文档中插入多个分页符。

```csharp
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);
```

## 第 4 步：移至页脚

我们使用`MoveToHeaderFooter()`DocumentBuilder 的方法将光标移动到主页脚。

```csharp
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

## 第 5 步：插入嵌套字段

我们使用 DocumentBuilder 的`InsertField()`将嵌套字段插入页脚的方法。

```csharp
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");
```

最后，我们称`Update()`更新字段的方法。

```csharp
field. Update();
```

### 使用 Aspose.Words for .NET 插入嵌套字段的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//创建文档和 DocumentBuilder。
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//插入分页符。
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);

//移动到页脚。
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

//插入嵌套字段。
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");

//更新字段。
field. Update();

doc.Save(dataDir + "InsertNestedFields.docx");
```

在此示例中，我们创建了一个新文档，插入了分页符，将光标移动到页脚，然后在页脚中插入了一个嵌套字段。