---
title: 在每个部分重新启动列表
linktitle: 在每个部分重新启动列表
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 为 Word 文档中的每个部分重置编号列表。
type: docs
weight: 10
url: /zh/net/working-with-list/restart-list-at-each-section/
---

在这个循序渐进的教程中，我们将向您展示如何使用 Aspose.Words for .NET 为 Word 文档中的每个部分重置编号列表。我们将解释提供的 C# 源代码，并向您展示如何在您自己的项目中实施它。

要开始，请确保您已在开发环境中安装并配置了 Aspose.Words for .NET。如果您还没有，请从官方网站下载并安装该库。

## 第 1 步：创建文档和列表

首先，创建一个新文档并添加一个默认编号列表：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;
```

## 第 2 步：将项目添加到列表

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

在此示例中，我们在第 15 个列表项之后插入一个分节符以说明重新编号。

## 第 3 步：保存修改后的文档

最后，保存修改后的文件：

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);
```

所以 ！您已经使用 Aspose.Words for .NET 成功地将编号列表重置为 Word 文档中的每个部分。

### 在每个部分重置列表的示例源代码

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

随意在您自己的项目中使用此代码并修改它以满足您的特定需求。
