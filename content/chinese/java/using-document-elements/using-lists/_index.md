---
title: 在 Aspose.Words for Java 中使用列表
linktitle: 使用列表
second_title: Aspose.Words Java 文档处理 API
description: 通过此分步教程，学习如何在 Aspose.Words for Java 中使用列表。有效地组织和格式化您的文档。
type: docs
weight: 18
url: /zh/java/using-document-elements/using-lists/
---

在这个综合教程中，我们将探讨如何有效地使用 Aspose.Words for Java 中的列表，这是一个强大的 API，用于以编程方式处理 Microsoft Word 文档。列表对于构建和组织文档中的内容至关重要。我们将介绍使用列表的两个关键方面：在每个部分重新启动列表和指定列表级别。让我们深入了解吧！

## Aspose.Words for Java 简介

在开始使用列表之前，让我们先熟悉一下 Aspose.Words for Java。该 API 为开发人员提供了在 Java 环境中创建、修改和操作 Word 文档的工具。它是一种多功能解决方案，适用于从简单的文档生成到复杂的格式设置和内容管理等任务。

### 设置您的环境

首先，请确保您已在开发环境中安装并设置了 Aspose.Words for Java。你可以下载它[这里](https://releases.aspose.com/words/java/). 

## 在每个部分重新启动列表

在许多情况下，您可能需要在文档的每个部分重新启动列表。这对于创建具有多个部分的结构化文档（例如报告、手册或学术论文）非常有用。

以下是有关如何使用 Aspose.Words for Java 实现此目的的分步指南：

### 初始化您的文档： 
首先创建一个新的文档对象。

```java
Document doc = new Document();
```

### 添加编号列表： 
将编号列表添加到您的文档中。我们将使用默认的编号样式。

```java
doc.getLists().add(ListTemplate.NUMBER_DEFAULT);
```

### 配置列表设置： 
\启用列表在每个部分重新启动。

```java
List list = doc.getLists().get(0);
list.isRestartAtEachSection(true);
```

### 文档生成器设置： 
创建一个 DocumentBuilder 以将内容添加到文档中。

```java
DocumentBuilder builder = new DocumentBuilder(doc);
builder.getListFormat().setList(list);
```

### 添加列表项： 
使用循环将列表项添加到文档中。我们将在第 15 项之后插入分节符。

```java
for (int i = 1; i < 45; i++) {
    builder.writeln(MessageFormat.format("List Item {0}", i));
    if (i == 15)
        builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
}
```

### 保存您的文档： 
使用所需选项保存文档。

```java
OoxmlSaveOptions options = new OoxmlSaveOptions();
options.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL);
doc.save(outPath + "RestartListAtEachSection.docx", options);
```

通过执行这些步骤，您可以创建包含在每个部分重新开始的列表的文档，从而保持清晰且有组织的内容结构。

## 指定列表级别

Aspose.Words for Java 允许您指定列表级别，当您在文档中需要不同的列表格式时，这特别有用。让我们探讨一下如何做到这一点：

### 初始化您的文档： 
创建一个新的文档对象。

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

### 创建编号列表： 
应用 Microsoft Word 中的编号列表模板。

```java
builder.getListFormat().setList(doc.getLists().add(ListTemplate.NUMBER_ARABIC_DOT));
```

### 指定列表级别： 
迭代不同的列表级别并添加内容。

```java
for (int i = 0; i < 9; i++) {
    builder.getListFormat().setListLevelNumber(i);
    builder.writeln("Level " + i);
}
```

### 创建项目符号列表： 
现在，让我们创建一个项目符号列表。

```java
builder.getListFormat().setList(doc.getLists().add(ListTemplate.BULLET_DIAMONDS));
```

### 指定项目符号列表级别： 
与编号列表类似，指定级别并添加内容。

```java
for (int i = 0; i < 9; i++) {
    builder.getListFormat().setListLevelNumber(i);
    builder.writeln("Level " + i);
}
```

### 停止列表格式： 
要停止列表格式化，请将列表设置为空。

```java
builder.getListFormat().setList(null);
```

### 保存您的文档： 
保存文档。

```java
builder.getDocument().save(outPath + "SpecifyListLevel.docx");
```

通过执行这些步骤，您可以创建具有自定义列表级别的文档，从而允许您控制文档中列表的格式。

## 完整的源代码
```java
	string outPath = "Your Output Directory";
 public void restartListAtEachSection() throws Exception
    {
        Document doc = new Document();
        doc.getLists().add(ListTemplate.NUMBER_DEFAULT);
        List list = doc.getLists().get(0);
        list.isRestartAtEachSection(true);
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.getListFormat().setList(list);
        for (int i = 1; i < 45; i++)
        {
            builder.writeln(MessageFormat.format("List Item {0}", i));
            if (i == 15)
                builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
        }
        //仅当合规性高于 OoxmlComplianceCore.Ecma376 时才会写入 IsRestartAtEachSection。
        OoxmlSaveOptions options = new OoxmlSaveOptions(); { options.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL); }
        doc.save(outPath + "WorkingWithList.RestartListAtEachSection.docx", options);
    }
    @Test
    public void specifyListLevel() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        //根据 Microsoft Word 列表模板之一创建编号列表
        //并将其应用于文档生成器的当前段落。
        builder.getListFormat().setList(doc.getLists().add(ListTemplate.NUMBER_ARABIC_DOT));
        //此列表中有九个级别，让我们全部尝试一下。
        for (int i = 0; i < 9; i++)
        {
            builder.getListFormat().setListLevelNumber(i);
            builder.writeln("Level " + i);
        }
        //基于 Microsoft Word 列表模板之一创建项目符号列表
        //并将其应用于文档生成器的当前段落。
        builder.getListFormat().setList(doc.getLists().add(ListTemplate.BULLET_DIAMONDS));
        for (int i = 0; i < 9; i++)
        {
            builder.getListFormat().setListLevelNumber(i);
            builder.writeln("Level " + i);
        }
        //这是停止列表格式化的一种方法。
        builder.getListFormat().setList(null);
        builder.getDocument().save(outPath + "WorkingWithList.SpecifyListLevel.docx");
    }
    @Test
    public void restartListNumber() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        //根据模板创建列表。
        List list1 = doc.getLists().add(ListTemplate.NUMBER_ARABIC_PARENTHESIS);
        list1.getListLevels().get(0).getFont().setColor(Color.RED);
        list1.getListLevels().get(0).setAlignment(ListLevelAlignment.RIGHT);
        builder.writeln("List 1 starts below:");
        builder.getListFormat().setList(list1);
        builder.writeln("Item 1");
        builder.writeln("Item 2");
        builder.getListFormat().removeNumbers();
        //要重用第一个列表，我们需要通过创建原始列表格式的副本来重新开始编号。
        List list2 = doc.getLists().addCopy(list1);
        //我们可以以任何方式修改新列表，包括设置新的起始编号。
        list2.getListLevels().get(0).setStartAt(10);
        builder.writeln("List 2 starts below:");
        builder.getListFormat().setList(list2);
        builder.writeln("Item 1");
        builder.writeln("Item 2");
        builder.getListFormat().removeNumbers();
        builder.getDocument().save(outPath + "WorkingWithList.RestartListNumber.docx");
	}
```

## 结论

恭喜！您已经了解了如何在 Aspose.Words for Java 中有效地使用列表。列表对于组织和呈现文档中的内容至关重要。无论您需要在每个部分重新启动列表还是指定列表级别，Aspose.Words for Java 都能提供您创建具有专业外观的文档所需的工具。

现在，您可以自信地使用这些功能来增强文档生成和格式化任务。如果您有任何疑问或需要进一步帮助，请随时联系[Aspose 社区论坛](https://forum.aspose.com/)为了支持。

## 常见问题解答

### 如何安装 Aspose.Words for Java？
您可以从以下位置下载 Aspose.Words for Java：[这里](https://releases.aspose.com/words/java/)并按照文档中的安装说明进行操作。

### 我可以自定义列表的编号格式吗？
是的，Aspose.Words for Java 提供了广泛的选项来自定义列表编号格式。具体可以参考API文档。

### Aspose.Words for Java 是否与最新的 Word 文档标准兼容？
是的，您可以配置 Aspose.Words for Java 以符合各种 Word 文档标准，包括 ISO 29500。

### 我可以使用 Aspose.Words for Java 生成包含表格和图像的复杂文档吗？
绝对地！ Aspose.Words for Java 支持高级文档格式，包括表格、图像等。检查文档中的示例。

### 在哪里可以获得 Aspose.Words for Java 的临时许可证？
您可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).
