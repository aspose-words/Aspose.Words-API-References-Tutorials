---
title: 在每个部分重新启动列表
linktitle: 在每个部分重新启动列表
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 重置 Word 文档中每个部分的编号列表。
type: docs
weight: 10
url: /zh/net/working-with-list/restart-list-at-each-section/
---

在本分步教程中，我们将向您展示如何使用 Aspose.Words for .NET 重置 Word 文档中每个部分的编号列表。我们将解释提供的 C# 源代码并向您展示如何在您自己的项目中实现它。

首先，请确保您已在开发环境中安装并配置了 Aspose.Words for .NET。如果您还没有安装该库，请从以下位置下载并安装该库：[Aspose.Releases]https://releases.aspose.com/words/net/。

## 第 1 步：创建文档和列表

首先，创建一个新文档并添加默认编号列表：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;
```

## 第 2 步：将项目添加到列表中

然后使用一个`DocumentBuilder`将项目添加到列表中。您可以使用循环将多个项目添加到列表中：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
     builder.Writeln($"List item {i}");

     if (i == 15)
         builder.InsertBreak(BreakType.SectionBreakNewPage);
}
```

在此示例中，我们在第 15 个列表项之后插入分节符以说明重新编号。

## 第三步：保存修改后的文档

最后保存修改后的文档：

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);
```

所以 ！您已使用 Aspose.Words for .NET 成功重置了 Word 文档中每个部分的编号列表。

### 用于重置每个部分的列表的示例源代码

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
	 builder.Writeln($"List item {i}");

	 if (i == 15)
		 builder.InsertBreak(BreakType.SectionBreakNewPage);
}

OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);

```

请随意在您自己的项目中使用此代码并对其进行修改以满足您的特定需求。

### 常见问题解答

#### 问：如何在 Aspose.Words 的每个部分重新启动列表？

答：要在 Aspose.Words 中的每个部分重新启动列表，您需要创建一个实例`List`类并为其分配一个编号列表。然后您可以使用`List.IsRestartAtEachSection`属性来指定应在每个部分重新开始编号。您可以将此列表与文档的一个或多个部分相关联，以便在每个部分正确地重新开始编号。

#### 问：我可以在 Aspose.Words 中自定义列表的编号格式吗？

答：是的，您可以在 Aspose.Words 中自定义列表的编号格式。这`List`类为此提供了几个属性，例如`List.ListFormat.ListType`, `List.ListLevels`, `ListLevel.NumberFormat`等。您可以使用这些属性来设置列表类型（编号、项目符号等）、编号格式（阿拉伯数字、罗马数字、字母等）以及其他编号格式选项。

#### 问：是否可以向 Aspose.Words 中的编号列表添加其他级别？

答：是的，可以向 Aspose.Words 中的编号列表添加其他级别。这`ListLevel`类允许您为列表的每个级别设置格式属性。您可以设置前缀、后缀、对齐、缩进等选项。这允许您创建具有多个层次结构的列表。