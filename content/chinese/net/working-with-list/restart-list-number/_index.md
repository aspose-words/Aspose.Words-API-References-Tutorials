---
title: 重启列表号码
linktitle: 重启列表号码
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 重置 Word 文档中列表的编号。
type: docs
weight: 10
url: /zh/net/working-with-list/restart-list-number/
---
在本分步教程中，我们将向您展示如何使用 Aspose.Words for .NET 重置 Word 文档中列表的编号。我们将解释提供的 C# 源代码并向您展示如何在您自己的项目中实现它。

首先，请确保已在开发环境中安装并配置了 Aspose.Words for .NET。如果尚未安装，请从以下位置下载并安装该库[Aspose.发布]https://releases.aspose.com/words/net/。

## 步骤 1：创建文档和文档生成器

首先，创建一个新文档和一个相关的文档生成器：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步骤 2：创建和自定义第一个列表

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

## 步骤4：创建和自定义第二个列表

要通过重置数字重新使用第一个列表，请创建原始列表布局的副本：

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

## 步骤6：保存修改后的文档

最后保存修改后的文档：

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

所以！您已成功使用 Aspose.Words for .NET 重置了 Word 文档中列表的编号。

### 列表编号重置示例源代码

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

//要重复使用第一个列表，我们需要通过创建原始列表格式的副本来重新开始编号。
List list2 = doc.Lists.AddCopy(list1);

//我们可以以任意方式修改新列表，包括设置新的起始号码。
list2.ListLevels[0].StartAt = 10;

builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
            
```

### 常见问题解答

#### 问：如何在 Aspose.Words 中重新开始列表编号？

答：要在 Aspose.Words 中重新开始列表的编号，您可以使用`ListRestartAtNumber`方法`List`类。此方法允许您设置一个新的拨号值，列表应从该值重新启动。例如，您可以使用`list.ListRestartAtNumber(1)`从 1 重新开始编号。

#### 问：是否可以在 Aspose.Words 中自定义重新启动列表编号的前缀和后缀？

答：是的，您可以在 Aspose.Words 中自定义重新启动列表编号的前缀和后缀。`ListLevel`该类提供以下属性`ListLevel.NumberPrefix`和`ListLevel.NumberSuffix`允许您为列表中的每个级别指定前缀和后缀。您可以使用这些属性根据需要自定义前缀和后缀。

#### 问：如何指定应重新开始列表的特定编号值？

答：要指定列表应从其重新开始的特定数值，您可以使用`ListRestartAtNumber`方法将所需值作为参数传递。例如，要从 5 重新开始编号，您可以使用`list.ListRestartAtNumber(5)`.

#### 问：是否可以在 Aspose.Words 中重新启动多级列表编号？

答：是的，Aspose.Words 支持多个列表级别的重新编号。您可以应用`ListRestartAtNumber`方法可以单独重新开始编号。例如，您可以使用`list.Levels[0].ListRestartAtNumber(1)`从 1 重新开始第一级列表，然后`list.Levels[1].ListRestartAtNumber(1)`从 1 开始重新开始第二级列表，依此类推。



