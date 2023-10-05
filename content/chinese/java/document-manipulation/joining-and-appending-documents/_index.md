---
title: 在 Aspose.Words for Java 中连接和附加文档
linktitle: 加入和附加文档
second_title: Aspose.Words Java 文档处理 API
description: 了解如何使用 Aspose.Words for Java 轻松加入和附加文档。保留格式、管理页眉页脚等。
type: docs
weight: 30
url: /zh/java/document-manipulation/joining-and-appending-documents/
---

## Aspose.Words for Java 中连接和附加文档简介

在本教程中，我们将探索如何使用 Aspose.Words for Java 库加入和附加文档。您将学习如何无缝合并多个文档，同时保留格式和结构。

## 先决条件

在开始之前，请确保您的 Java 项目中已设置 Aspose.Words for Java API。

## 文档连接选项

### 简单追加

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### 添加导入格式选项

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

### 附加到空白文档

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document();
dstDoc.removeAllChildren();
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### 附加页码转换

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
convertNumPageFieldsToPageRef(dstDoc); //转换 NUMPAGES 字段
dstDoc.updatePageLayout(); //更新页面布局以获得正确的编号
```

## 处理不同的页面设置

附加具有不同页面设置的文档时：

```java
srcDoc.getFirstSection().getPageSetup().setSectionStart(SectionStart.CONTINUOUS);
srcDoc.getFirstSection().getPageSetup().setRestartPageNumbering(true);
//确保页面设置设置与目标文档匹配
```

## 连接不同样式的文档

```java
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES);
```

## 聪明的风格行为

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setSmartStyleBehavior(true);
builder.insertDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

## 使用 DocumentBuilder 插入文档

```java
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.insertDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## 保留源编号

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## 处理文本框

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setIgnoreTextBoxes(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## 管理页眉和页脚

### 链接页眉和页脚

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### 取消页眉和页脚的链接

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## 结论

Aspose.Words for Java 提供了灵活而强大的工具来连接和附加文档，无论您需要维护格式、处理不同的页面设置还是管理页眉和页脚。尝试使用这些技术来满足您的特定文档处理需求。

## 常见问题解答

### 如何无缝拼接不同样式的文档？

要加入不同样式的文档，请使用`ImportFormatMode.USE_DESTINATION_STYLES`追加时。

### 附加文档时可以保留页码吗？

是的，您可以使用以下命令保留页码`convertNumPageFieldsToPageRef`方法并更新页面布局。

### 什么是聪明风格行为？

智能样式行为有助于在附加文档时保持一致的样式。与它一起使用`ImportFormatOptions`为了更好的结果。

### 附加文档时如何处理文本框？

放`importFormatOptions.setIgnoreTextBoxes(false)`在附加过程中包含文本框。

### 如果我想在文档之间链接/取消链接页眉和页脚怎么办？

您可以将页眉和页脚链接到`linkToPrevious(true)`或取消它们的链接`linkToPrevious(false)`如所须。