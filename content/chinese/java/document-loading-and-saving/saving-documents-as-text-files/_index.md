---
title: 在 Aspose.Words for Java 中将文档保存为文本文件
linktitle: 将文档另存为文本文件
second_title: Aspose.Words Java 文档处理 API
description: 了解如何在 Aspose.Words for Java 中将文档另存为文本文件。请按照我们的 Java 代码示例分步指南进行操作。
type: docs
weight: 24
url: /zh/java/document-loading-and-saving/saving-documents-as-text-files/
---

## 在 Aspose.Words for Java 中将文档保存为文本文件简介

在本教程中，我们将探讨如何使用 Aspose.Words for Java 库将文档另存为文本文件。 Aspose.Words 是一个功能强大的 Java API，用于处理 Word 文档，它提供了多种选项来保存不同格式的文档，包括纯文本。我们将介绍实现这一目标的步骤并提供示例 Java 代码。

## 先决条件

在我们开始之前，请确保您具备以下先决条件：

- 您的系统上安装了 Java 开发工具包 (JDK)。
-  Aspose.Words for Java 库集成到您的项目中。您可以从以下位置下载：[这里](https://releases.aspose.com/words/java/).
- Java 编程的基础知识。

## 第 1 步：创建文档

要将文档另存为文本文件，我们首先需要使用 Aspose.Words 创建一个文档。下面是一个简单的 Java 代码片段，用于创建包含某些内容的文档：

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.writeln("Hello world!");
builder.getParagraphFormat().setBidi(true);
builder.writeln("שלום עולם!");
builder.writeln("مرحبا بالعالم!");
```

在此代码中，我们创建一个新文档并向其中添加一些文本，包括不同语言的文本。

## 第 2 步：定义文本保存选项

接下来，我们需要定义文本保存选项，指定如何将文档保存为文本文件。我们可以配置各种设置，例如添加双向标记、列表缩进等等。让我们看两个例子：

### 示例 1：添加 Bidi 标记

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
doc.save("output.txt", saveOptions);
```

在这个例子中，我们创建一个`TxtSaveOptions`对象并设置`AddBidiMarks`财产给`true`在文本输出中包含 bidi 标记。

### 示例 2：使用制表符进行列表缩进

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
doc.save("output.txt", saveOptions);
```

在这里，我们配置保存选项以使用制表符进行列表缩进，计数为 1。

## 步骤 3：将文档另存为文本

现在我们已经定义了文本保存选项，我们可以将文档保存为文本文件。以下代码演示了如何执行此操作：

```java
doc.save("output.txt", saveOptions);
```

代替`"output.txt"`以及要保存文本文件的所需文件路径。

## 在 Aspose.Words for Java 中将文档保存为文本文件的完整源代码

```java
    public void addBidiMarks() throws Exception
    {        
		Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.writeln("Hello world!");
        builder.getParagraphFormat().setBidi(true);
        builder.writeln("שלום עולם!");
        builder.writeln("مرحبا بالعالم!");
        TxtSaveOptions saveOptions = new TxtSaveOptions(); { saveOptions.setAddBidiMarks(true); }
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
    }
    @Test
    public void useTabCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        //创建一个具有三级缩进的列表。
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(1);
        saveOptions.getListIndentation().setCharacter('\t');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);
    }
    @Test
    public void useSpaceCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        //创建一个具有三级缩进的列表。
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(3);
        saveOptions.getListIndentation().setCharacter(' ');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
	}
```

## 结论

在本教程中，我们学习了如何在 Aspose.Words for Java 中将文档另存为文本文件。我们介绍了创建文档、定义文本保存选项以及以文本格式保存文档的步骤。 Aspose.Words 在保存文档方面提供了广泛的灵活性，允许您根据您的特定要求定制输出。

## 常见问题解答

### 如何将 Bidi 标记添加到文本输出？

要将 Bidi 标记添加到文本输出，请设置`AddBidiMarks`的财产`TxtSaveOptions`到`true`。例如：

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
```

### 我可以自定义列表缩进字符吗？

是的，您可以通过配置来自定义列表缩进字符`ListIndentation`的财产`TxtSaveOptions`。例如，要使用制表符进行列表缩进，您可以执行以下操作：

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
```

### Aspose.Words for Java 适合处理多语言文本吗？

是的，Aspose.Words for Java 适合处理多语言文本。它支持各种语言和字符编码，使其成为处理不同语言文档的多功能选择。

### 如何访问 Aspose.Words for Java 的更多文档和资源？

您可以在 Aspose 文档网站上找到 Aspose.Words for Java 的全面文档和资源：[Aspose.Words for Java 文档](https://reference.aspose.com/words/java/).

### 在哪里可以下载 Aspose.Words for Java？

您可以从 Aspose 网站下载 Aspose.Words for Java 库：[下载 Java 版 Aspose.Words](https://releases.aspose.com/words/java/).