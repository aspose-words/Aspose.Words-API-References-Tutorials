---
title: 在 Aspose.Words for Java 中使用文档属性
linktitle: 使用文档属性
second_title: Aspose.Words Java 文档处理 API
description: 使用 Aspose.Words for Java 优化文档管理。在这个综合教程中学习如何使用文档属性、添加自定义元数据等。
type: docs
weight: 32
url: /zh/java/document-manipulation/using-document-properties/
---

## 文档属性简介

文档属性是任何文档的重要组成部分。它们提供有关文档本身的附加信息，例如标题、作者、主题、关键字等。在 Aspose.Words for Java 中，您可以操作内置和自定义文档属性。

## 枚举文档属性

### 内置属性

要检索和使用内置文档属性，您可以使用以下代码片段：

```java
@Test
public void enumerateProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    System.out.println(MessageFormat.format("1. Document name: {0}", doc.getOriginalFileName()));
    System.out.println("2. Built-in Properties");
    for (DocumentProperty prop : doc.getBuiltInDocumentProperties())
        System.out.println(MessageFormat.format("{0} : {1}", prop.getName(), prop.getValue()));
}
```

此代码将显示文档的名称和内置属性，包括“标题”、“作者”和“关键字”等属性。

### 自定义属性

要使用自定义文档属性，您可以使用以下代码片段：

```java
@Test
public void addCustomDocumentProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    CustomDocumentProperties customDocumentProperties = doc.getCustomDocumentProperties();

    if (customDocumentProperties.get("Authorized") != null) return;

    customDocumentProperties.add("Authorized", true);
    customDocumentProperties.add("Authorized By", "John Smith");
    customDocumentProperties.add("Authorized Date", new Date());
    customDocumentProperties.add("Authorized Revision", doc.getBuiltInDocumentProperties().getRevisionNumber());
    customDocumentProperties.add("Authorized Amount", 123.45);
}
```

此代码片段演示了如何添加自定义文档属性，包括布尔值、字符串、日期、修订号和数值。

## 删除文档属性

要删除特定文档属性，可以使用以下代码：

```java
@Test
public void removeCustomDocumentProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    doc.getCustomDocumentProperties().remove("Authorized Date");
}
```

此代码从文档中删除自定义属性“授权日期”。

## 配置内容链接

在某些情况下，您可能希望在文档中创建链接。您可以这样做：

```java
@Test
public void configuringLinkToContent() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.startBookmark("MyBookmark");
    builder.writeln("Text inside a bookmark.");
    builder.endBookmark("MyBookmark");

    CustomDocumentProperties customProperties = doc.getCustomDocumentProperties();

    //添加链接到内容属性。
    DocumentProperty customProperty = customProperties.addLinkToContent("Bookmark", "MyBookmark");
    customProperty = customProperties.get("Bookmark");
    boolean isLinkedToContent = customProperty.isLinkToContent();
    String linkSource = customProperty.getLinkSource();
    String customPropertyValue = customProperty.getValue().toString();
}
```

此代码段演示了如何在文档中创建书签并添加链接到该书签的自定义文档属性。

## 测量单位之间的转换

在Aspose.Words for Java中，您可以轻松转换测量单位。以下是如何执行此操作的示例：

```java
@Test
public void convertBetweenMeasurementUnits() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    PageSetup pageSetup = builder.getPageSetup();

    //设置页边距（以英寸为单位）。
    pageSetup.setTopMargin(ConvertUtil.inchToPoint(1.0));
    pageSetup.setBottomMargin(ConvertUtil.inchToPoint(1.0));
    pageSetup.setLeftMargin(ConvertUtil.inchToPoint(1.5));
    pageSetup.setRightMargin(ConvertUtil.inchToPoint(1.5));
    pageSetup.setHeaderDistance(ConvertUtil.inchToPoint(0.2));
    pageSetup.setFooterDistance(ConvertUtil.inchToPoint(0.2));
}
```

此代码片段通过将各种边距和距离（以英寸为单位）转换为点来设置它们。

## 使用控制字符

处理文本时控制字符很有用。以下是替换文本中控制字符的方法：

```java
@Test
public void useControlCharacters()
{
    final String TEXT = "test\r";

    //将“\r”控制字符替换为“\r\n”。
    String replace = TEXT.replace(ControlChar.CR, ControlChar.CR_LF);
}
```

在此示例中，我们替换回车符 (`\r`），回车后跟换行符（`\r\n`）。

## 结论

文档属性在 Aspose.Words for Java 中有效管理和组织文档方面发挥着重要作用。无论是使用内置属性、自定义属性还是使用控制字符，您都可以使用一系列工具来增强文档管理功能。

## 常见问题解答

### 如何访问内置文档属性？

要访问 Aspose.Words for Java 中的内置文档属性，您可以使用`getBuiltInDocumentProperties`方法上的`Document`目的。此方法返回您可以迭代的内置属性的集合。

### 我可以向文档添加自定义文档属性吗？

是的，您可以使用以下命令将自定义文档属性添加到文档中：`CustomDocumentProperties`收藏。您可以使用各种数据类型定义自定义属性，包括字符串、布尔值、日期和数值。

### 如何删除特定的自定义文档属性？

要删除特定的自定义文档属性，您可以使用`remove`方法上的`CustomDocumentProperties`集合，将要删除的属性的名称作为参数传递。

### 链接到文档内容的目的是什么？

链接到文档中的内容允许您创建对文档特定部分的动态引用。这对于创建交互式文档或各部分之间的交叉引用非常有用。

### 如何在 Aspose.Words for Java 中的不同测量单位之间进行转换？

您可以使用 Aspose.Words for Java 在不同的测量单位之间进行转换`ConvertUtil`班级。它提供了将英寸转换为点、点转换为厘米等单位的方法。