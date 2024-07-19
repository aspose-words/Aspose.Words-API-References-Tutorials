---
title: 指定列表级别
linktitle: 指定列表级别
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中指定列表级别。
type: docs
weight: 10
url: /zh/net/working-with-list/specify-list-level/
---

在本分步教程中，我们将向您展示如何使用 Aspose.Words for .NET 在 Word 文档中指定列表级别。我们将解释提供的 C# 源代码并向您展示如何在您自己的项目中实现它。

首先，请确保已在开发环境中安装并配置了 Aspose.Words for .NET。如果尚未安装，请从以下位置下载并安装该库[Aspose.发布]https://releases.aspose.com/words/net/。

## 步骤 1：创建文档和文档生成器

首先，创建一个新文档和一个相关的文档生成器：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步骤 2：创建并应用编号列表

接下来，根据 Microsoft Word 的列表模板之一创建一个编号列表，并将其应用于文档构建器中的当前段落：

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);
```

## 步骤 3：列表级别规范

使用文档生成器的`ListLevelNumber`属性来指定列表级别并向段落添加文本：

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

重复这些步骤以指定列表级别并在每个级别添加文本。

## 步骤 4：创建并应用项目符号列表

您还可以使用 Microsoft Word 的列表模板之一创建和应用项目符号列表：

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);
```

## 步骤 5：向项目符号列表级别添加文本

使用`ListLevelNumber`属性来指定项目符号列表级别并添加文本：

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

## 步骤 6：停止格式化列表

要停止列表格式化，请设置`null`到`List`文档生成器的属性：

```csharp
builder. ListFormat. List = null;
```

## 步骤 7：保存修改后的文档

保存修改后的文档：

```csharp
builder.Document.Save(dataDir + "SpecifyListLevel.docx");
```

所以！您已成功使用 Aspose.Words for .NET 在 Word 文档中指定列表级别。

### 指定列表级别的示例源代码

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//根据 Microsoft Word 列表模板之一创建编号列表
//并将其应用于文档构建器的当前段落。
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);

//此列表中共有九个级别，让我们全部尝试一下。
for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

//根据 Microsoft Word 列表模板之一创建项目符号列表
//并将其应用于文档构建器的当前段落。
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);

for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

//这是一种停止列表格式化的方法。
builder.ListFormat.List = null;

builder.Document.Save(dataDir + "WorkingWithList.SpecifyListLevel.docx");
            
```

### 常见问题解答

#### 问：如何在 Aspose.Words 中指定列表级别？

答：要在 Aspose.Words 中指定列表级别，您需要创建一个实例`List`类并为其添加编号列表。然后您可以使用`Paragraph.ListFormat.ListLevelNumber`属性来指定每个列表项的级别。您可以将此列表与文档的某个部分关联起来，以便列表项具有所需的级别。

#### 问：是否可以更改 Aspose.Words 中列表项的编号格式？

答：是的，您可以更改 Aspose.Words 中列表项的编号格式。`ListLevel`该类提供了几个属性，例如`ListLevel.NumberFormat`, `ListLevel.NumberStyle`, `ListLevel.NumberPosition`等。您可以使用这些属性来设置列表项的编号格式，例如阿拉伯数字、罗马数字、字母等。

#### 问：我可以在 Aspose.Words 中的编号列表中添加其他级别吗？

答：是的，可以在 Aspose.Words 中的编号列表中添加其他级别。`ListLevel`类允许您为列表的每个级别设置格式属性。您可以设置前缀、后缀、对齐、缩进等选项。这允许您创建具有多个层次结构的列表。


