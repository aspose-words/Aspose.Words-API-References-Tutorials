---
title: 在 Aspose.Words for Java 中使用清理选项
linktitle: 使用清理选项
second_title: Aspose.Words Java 文档处理 API
description: 使用 Aspose.Words for Java 清理选项增强文档清晰度。了解如何删除空段落、未使用的区域等。
type: docs
weight: 10
url: /zh/java/document-manipulation/using-cleanup-options/
---

## 在 Aspose.Words for Java 中使用清理选项的简介

在本教程中，我们将探讨如何在邮件合并过程中使用 Aspose.Words for Java 中的清理选项来操作和清理文档。清理选项允许您控制文档清理的各个方面，例如删除空段落、未使用的区域等。

## 先决条件

在开始之前，请确保您已将 Aspose.Words for Java 库集成到您的项目中。您可以从以下位置下载：[这里](https://releases.aspose.com/words/java/).

## 第 1 步：删除空段落

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//插入合并字段
FieldMergeField mergeFieldOption1 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_1");
mergeFieldOption1.setFieldName("Option_1");
builder.write(" ? ");
FieldMergeField mergeFieldOption2 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_2");
mergeFieldOption2.setFieldName("Option_2");

//设置清理选项
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS);

//启用带有标点符号的清理段落
doc.getMailMerge().setCleanupParagraphsWithPunctuationMarks(true);

//执行邮件合并
doc.getMailMerge().execute(new String[] { "Option_1", "Option_2" }, new Object[] { null, null });

//保存文档
doc.save("WorkingWithCleanupOptions.CleanupParagraphsWithPunctuationMarks.docx");
```

在此示例中，我们创建一个新文档，插入合并字段，并设置清理选项以删除空段落。此外，我们还可以删除带有标点符号的段落。执行邮件合并后，将保存文档并应用指定的清理。

## 第2步：删除未合并的区域

```java
Document doc = new Document("Your Directory Path" + "Mail merge destination - Northwind suppliers.docx");
DataSet data = new DataSet();

//设置清理选项以删除未使用的区域
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS);

//执行与区域的邮件合并
doc.getMailMerge().executeWithRegions(data);

//保存文档
doc.save("WorkingWithCleanupOptions.RemoveUnmergedRegions.docx");
```

在此示例中，我们打开一个包含合并区域的现有文档，设置清理选项以删除未使用的区域，然后使用空数据执行邮件合并。此过程会自动从文档中删除未使用的区域。

## 第 3 步：删除空字段

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

//设置清理选项以删除空字段
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_FIELDS);

//执行邮件合并
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

//保存文档
doc.save("WorkingWithCleanupOptions.RemoveEmptyFields.docx");
```

在此示例中，我们打开一个包含合并字段的文档，设置清理选项以删除空字段，然后执行与数据的邮件合并。合并后，任何空白字段都将从文档中删除。

## 第 4 步：删除未使用的字段

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

//设置清理选项以删除未使用的字段
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS);

//执行邮件合并
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

//保存文档
doc.save("WorkingWithCleanupOptions.RemoveUnusedFields.docx");
```

在此示例中，我们打开一个包含合并字段的文档，设置清理选项以删除未使用的字段，然后执行与数据的邮件合并。合并后，任何未使用的字段将从文档中删除。

## 第 5 步：删除包含字段

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

//设置清理选项以删除包含字段
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS);

//执行邮件合并
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

//保存文档
doc.save("WorkingWithCleanupOptions.RemoveContainingFields.docx");
```

在此示例中，我们打开一个包含合并字段的文档，设置清理选项以删除包含字段，然后执行与数据的邮件合并。合并后，字段本身将从文档中删除。

## 步骤 6：删除空表行

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

//设置清理选项以删除空表行
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS);

//执行邮件合并
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

//保存文档
doc.save("WorkingWithCleanupOptions.RemoveEmptyTableRows.docx");
```

在此示例中，我们打开一个包含表和合并字段的文档，设置清理选项以删除空表行，并执行与数据的邮件合并。合并后，任何空表行都将从文档中删除。

## 结论

在本教程中，您学习了如何在邮件合并过程中使用 Aspose.Words for Java 中的清理选项来操作和清理文档。这些选项提供对文档清理的细粒度控制，使您可以轻松创建精美的自定义文档。

## 常见问题解答

### Aspose.Words for Java 中的清理选项有哪些？

Aspose.Words for Java 中的清理选项允许您在邮件合并过程中控制文档清理的各个方面。它们使您能够删除不必要的元素，例如空段落、未使用的区域等，确保您的最终文档结构良好且优美。

### 如何从文档中删除空段落？

要使用 Aspose.Words for Java 从文档中删除空段落，您可以设置`MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS`选项为真。这将自动消除没有内容的段落，从而产生更干净的文档。

### 目的是什么`REMOVE_UNUSED_REGIONS` cleanup option?

这`MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS`选项用于在邮件合并过程中删除文档中没有相应数据的区域。它通过删除未使用的占位符来帮助保持文档整洁。

### 我可以使用 Aspose.Words for Java 从文档中删除空表行吗？

是的，您可以通过设置从文档中删除空表格行`MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS`清理选项设置为 true。这将自动删除任何不包含数据的表格行，确保文档中的表格结构良好。

### 当我设置时会发生什么`REMOVE_CONTAINING_FIELDS` option?

设置`MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS`该选项将在邮件合并过程中从文档中删除整个合并字段，包括其包含的段落。当您想要消除合并字段及其关联文本时，这非常有用。

### 如何从文档中删除未使用的合并字段？

要从文档中删除未使用的合并字段，您可以设置`MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS`选项为真。这将自动消除邮件合并期间未填充的合并字段，从而生成更干净的文档。

### 有什么区别`REMOVE_EMPTY_FIELDS` and `REMOVE_UNUSED_FIELDS` cleanup options?

这`REMOVE_EMPTY_FIELDS`选项会删除邮件合并过程中没有数据或为空的合并字段。另一方面，`REMOVE_UNUSED_FIELDS`选项删除合并期间未填充数据的合并字段。它们之间的选择取决于您是否要删除没有内容的字段或特定合并操作中未使用的字段。

### 如何删除带有标点符号的段落？

要启用删除带标点符号的段落，您可以设置`cleanupParagraphsWithPunctuationMarks`选项设置为 true 并指定要考虑清理的标点符号。这使您可以通过删除不必要的仅标点符号段落来创建更精致的文档。

### 我可以自定义 Aspose.Words for Java 中的清理选项吗？

是的，您可以根据您的具体需求自定义清理选项。您可以选择要应用的清理选项，并根据您的文档清理要求对其进行配置，以确保您的最终文档满足您所需的标准。