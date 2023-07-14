---
title: 重新启动列表编号
linktitle: 重新启动列表编号
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 重置 Word 文档中的列表编号。
type: docs
weight: 10
url: /zh/net/working-with-list/restart-list-number/
---
在本分步教程中，我们将向您展示如何使用 Aspose.Words for .NET 重置 Word 文档中的列表编号。我们将解释提供的 C# 源代码并向您展示如何在您自己的项目中实现它。

首先，请确保您已在开发环境中安装并配置了 Aspose.Words for .NET。如果您还没有安装该库，请从官方网站下载并安装该库。

## 第 1 步：创建文档和文档生成器

首先，创建一个新文档和关联的文档生成器：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：创建并自定义第一个列表

接下来，根据现有模板创建一个列表，然后自定义其级别：

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

## 步骤 3：将项目添加到第一个列表

使用文档生成器将项目添加到第一个列表并删除列表编号：

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## 第 4 步：创建并自定义第二个列表

要通过重置编号来重用第一个列表，请创建原始列表布局的副本：

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

如果需要，您还可以对第二个列表进行其他更改。

## 步骤 5：将项目添加到第二个列表

再次使用文档生成器将项目添加到第二个列表并删除列表编号：

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## 第六步：保存修改后的文档

最后保存修改后的文档：

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

所以 ！您已使用 Aspose.Words for .NET 成功重置了 Word 文档中的列表编号。

### 列表编号重置的示例源代码

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//根据模板创建列表。
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

### 常见问题解答

#### 问：如何在 Aspose.Words 中重新启动列表的编号？

答：要在 Aspose.Words 中重新启动列表编号，您可以使用`ListRestartAtNumber`的方法`List`班级。此方法允许您设置一个新的拨号值，列表应从该值重新启动。例如，您可以使用`list.ListRestartAtNumber(1)`从 1 重新开始编号。

#### 问：是否可以在Aspose.Words中自定义重新启动的列表编号的前缀和后缀？

答：是的，您可以在 Aspose.Words 中自定义重新启动列表编号的前缀和后缀。这`ListLevel`类提供诸如`ListLevel.NumberPrefix`和`ListLevel.NumberSuffix`它允许您指定列表中每个级别的前缀和后缀。您可以使用这些属性根据需要自定义前缀和后缀。

#### 问：如何指定列表应重新启动的特定编号值？

答：要指定列表应重新启动的特定数值，您可以使用`ListRestartAtNumber`方法将所需值作为参数传递。例如，要从 5 重新开始编号，您可以使用`list.ListRestartAtNumber(5)`.

#### 问：是否可以在 Aspose.Words 中重新启动多级列表编号？

答：是的，Aspose.Words 支持多个列表级别的重新编号。您可以应用`ListRestartAtNumber`方法在每个列表级别单独重新开始编号。例如，您可以使用`list.Levels[0].ListRestartAtNumber(1)`从 1 重新开始第一个列表级别，并且`list.Levels[1].ListRestartAtNumber(1)`从1开始重新启动二级列表，依此类推。



