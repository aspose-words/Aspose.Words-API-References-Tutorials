---
title: 重启列表编号
linktitle: 重启列表编号
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 重置 Word 文档中的列表编号。
type: docs
weight: 10
url: /zh/net/working-with-list/restart-list-number/
---
在本分步教程中，我们将向您展示如何使用 Aspose.Words for .NET 重置 Word 文档中列表的编号。我们将解释提供的 C# 源代码，并向您展示如何在您自己的项目中实施它。

要开始，请确保您已在开发环境中安装并配置了 Aspose.Words for .NET。如果您还没有，请从官方网站下载并安装该库。

## 第 1 步：创建文档和文档生成器

首先，创建一个新文档和一个关联的文档生成器：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：创建和自定义第一个列表

接下来，基于现有模板创建列表，然后自定义其级别：

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

## 第 3 步：将项目添加到第一个列表

使用文档生成器将项目添加到第一个列表并删除列表编号：

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## 第 4 步：创建和自定义第二个列表

要通过重置数字重用第一个列表，请创建原始列表布局的副本：

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

如果需要，您还可以对第二个列表进行其他更改。

## 第 5 步：将项目添加到第二个列表

再次使用文档生成器将项目添加到第二个列表并删除列表编号：

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## 第 6 步：保存修改后的文件

最后，保存修改后的文件：

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

所以 ！您已经使用 Aspose.Words for .NET 成功重置了 Word 文档中的列表编号。

### 列表编号重置的示例源代码

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//基于模板创建列表。
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;

builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

//要重用第一个列表，我们需要通过创建原始列表格式的副本来重新开始编号。
List list2 = doc.Lists.AddCopy(list1);

//我们可以以任何方式修改新列表，包括设置新的起始编号。
list2.ListLevels[0].StartAt = 10;

builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
            
```




