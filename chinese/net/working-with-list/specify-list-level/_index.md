---
title: 指定列表级别
linktitle: 指定列表级别
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中指定列表级别。
type: docs
weight: 10
url: /zh/net/working-with-list/specify-list-level/
---

在这个循序渐进的教程中，我们将向您展示如何使用 Aspose.Words for .NET 在 Word 文档中指定列表级别。我们将解释提供的 C# 源代码，并向您展示如何在您自己的项目中实施它。

要开始，请确保您已在开发环境中安装并配置了 Aspose.Words for .NET。如果您还没有，请从官方网站下载并安装该库。

## 第 1 步：创建文档和文档生成器

首先，创建一个新文档和一个关联的文档生成器：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：创建和应用编号列表

接下来，根据 Microsoft Word 的列表模板之一创建一个编号列表，并将其应用于文档生成器中的当前段落：

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);
```

## 第 3 步：列表级别规范

使用文档生成器的`ListLevelNumber`属性指定列表级别并向段落添加文本：

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

重复这些步骤以指定列表级别并在每个级别添加文本。

## 第 4 步：创建和应用项目符号列表

您还可以使用 Microsoft Word 的列表模板之一创建和应用项目符号列表：

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);
```

## 第 5 步：将文本添加到项目符号列表级别

使用`ListLevelNumber`属性再次指定项目符号列表级别并添加文本：

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

## 第 6 步：停止格式化列表

要停止列表格式化，请设置`null`到`List`文档生成器的属性：

```csharp
builder. ListFormat. List = null;
```

## 第七步：保存修改后的文档

保存修改后的文档：

```csharp
builder.Document.Save(dataDir + "SpecifyListLevel.docx");
```

所以 ！您已经成功地使用 Aspose.Words for .NET 在 Word 文档中指定了列表级别。

### 用于指定列表级别的示例源代码

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//根据 Microsoft Word 列表模板之一创建编号列表
//并将其应用于文档生成器的当前段落。
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);

//此列表中有九个级别，让我们尝试所有级别。
for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

//基于 Microsoft Word 列表模板之一创建项目符号列表
//并将其应用于文档生成器的当前段落。
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



