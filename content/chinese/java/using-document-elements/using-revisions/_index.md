---
title: 在 Aspose.Words for Java 中使用修订版
linktitle: 使用修订版
second_title: Aspose.Words Java 文档处理 API
description: 学习高效地使用Aspose.Words for Java 的修订版。开发人员的分步指南。优化您的文档管理。
type: docs
weight: 22
url: /zh/java/using-document-elements/using-revisions/
---

如果您是一位希望处理文档并需要实施修订控制的 Java 开发人员，Aspose.Words for Java 提供了一组强大的工具来帮助您有效地管理修订。在本教程中，我们将指导您逐步使用 Aspose.Words for Java 中的修订版本。 

## 1.Aspose.Words for Java简介

Aspose.Words for Java 是一个强大的 Java API，允许您创建、修改和操作 Word 文档，而无需 Microsoft Word。当您需要在文档中进行修订时，它特别有用。

## 2. 设置您的开发环境

在我们深入使用 Aspose.Words for Java 之前，您需要设置您的开发环境。确保您安装了必要的 Java 开发工具和 Aspose.Words for Java 库。

## 3. 创建新文档

让我们首先使用 Aspose.Words for Java 创建一个新的 Word 文档。您可以这样做：

```java
string outPath = "Your Output Directory";
Document doc = new Document();
Body body = doc.getFirstSection().getBody();
Paragraph para = body.getFirstParagraph();
```

## 4.向文档添加内容

现在您有了一个空白文档，您可以向其中添加内容。在此示例中，我们将添加三个段落：

```java
para.appendChild(new Run(doc, "Paragraph 1. "));
body.appendParagraph("Paragraph 2. ");
body.appendParagraph("Paragraph 3. ");
```

## 5. 开始修订跟踪

要跟踪文档中的修订，您可以使用以下代码：

```java
doc.startTrackRevisions("John Doe", new Date());
```

## 6. 修改

让我们修改一下，添加另一段：

```java
para = body.appendParagraph("Paragraph 4. ");
```

## 7. 接受和拒绝修改

您可以使用 Aspose.Words for Java 接受或拒绝文档中的修订。生成文档后，可以在 Microsoft Word 中轻松管理修订。

## 8. 停止修订跟踪

要停止跟踪修订，请使用以下代码：

```java
doc.stopTrackRevisions();
```

## 9. 保存文档

最后，保存您的文档：

```java
doc.save(outPath + "WorkingWithRevisions.AcceptRevisions.docx");
```

## 10. 结论

在本教程中，我们介绍了在 Aspose.Words for Java 中使用修订版的基础知识。您已了解如何创建文档、添加内容、启动和停止修订跟踪以及保存文档。

现在，您拥有了使用 Aspose.Words for Java 有效管理 Java 应用程序中的修订所需的工具。

## 完整的源代码
```java
string outPath = "Your Output Directory";
Document doc = new Document();
Body body = doc.getFirstSection().getBody();
Paragraph para = body.getFirstParagraph();
//将文本添加到第一个段落，然后再添加两个段落。
para.appendChild(new Run(doc, "Paragraph 1. "));
body.appendParagraph("Paragraph 2. ");
body.appendParagraph("Paragraph 3. ");
//我们有三个段落，其中没有一个被注册为任何类型的修订
//如果我们在跟踪修订时添加/删除文档中的任何内容，
//它们将在文档中显示并可以接受/拒绝。
doc.startTrackRevisions("John Doe", new Date());
//本段是修订版，并将设置相应的“IsInsertRevision”标志。
para = body.appendParagraph("Paragraph 4. ");
Assert.assertTrue(para.isInsertRevision());
//获取文档的段落集合并删除段落。
ParagraphCollection paragraphs = body.getParagraphs();
Assert.assertEquals(4, paragraphs.getCount());
para = paragraphs.get(2);
para.remove();
//由于我们正在跟踪修订，该段落仍然存在于文档中，将设置“IsDeleteRevision”
//并将在 Microsoft Word 中显示为修订版本，直到我们接受或拒绝所有修订版本。
Assert.assertEquals(4, paragraphs.getCount());
Assert.assertTrue(para.isDeleteRevision());
//一旦我们接受更改，已删除的修订段落就会被删除。
doc.acceptAllRevisions();
Assert.assertEquals(3, paragraphs.getCount());
Assert.assertEquals(para.getRuns().getCount(), 0); //是 Is.Empty
//停止跟踪修订会使该文本显示为普通文本。
//文档更改时不计算修订版本。
doc.stopTrackRevisions();
//保存文档。
doc.save(outPath + "WorkingWithRevisions.AcceptRevisions.docx");
  
```

## 常见问题解答

### 1. 我可以将 Aspose.Words for Java 与其他编程语言一起使用吗？

不，Aspose.Words for Java 是专为 Java 开发而设计的。

### 2. Aspose.Words for Java 是否与所有版本的 Microsoft Word 兼容？

是的，Aspose.Words for Java 旨在与各种版本的 Microsoft Word 兼容。

### 3. 我可以跟踪现有 Word 文档的修订吗？

是的，您可以使用 Aspose.Words for Java 来跟踪现有 Word 文档中的修订。

### 4. 使用 Aspose.Words for Java 有任何许可要求吗？

是的，您需要获得许可证才能在项目中使用 Aspose.Words for Java。你可以[在这里获取许可证](https://purchase.aspose.com/buy).

### 5. 在哪里可以找到 Aspose.Words for Java 的支持？

如有任何疑问或问题，您可以访问[Aspose.Words for Java 支持论坛](https://forum.aspose.com/).

立即开始使用 Aspose.Words for Java 并简化您的文档管理流程。
