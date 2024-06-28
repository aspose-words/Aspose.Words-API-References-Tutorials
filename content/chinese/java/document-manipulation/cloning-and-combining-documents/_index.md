---
title: 在 Aspose.Words for Java 中克隆和合并文档
linktitle: 克隆和合并文档
second_title: Aspose.Words Java 文档处理 API
description: 了解如何在 Aspose.Words for Java 中克隆和合并文档。带有源代码示例的分步指南。
type: docs
weight: 27
url: /zh/java/document-manipulation/cloning-and-combining-documents/
---

## Aspose.Words for Java 中克隆和组合文档的简介

在本教程中，我们将探索如何使用 Aspose.Words for Java 克隆和组合文档。我们将介绍各种场景，包括克隆文档、在替换点插入文档、书签以及在邮件合并操作期间。

## 第 1 步：克隆文档

要在 Aspose.Words for Java 中克隆文档，您可以使用`deepClone()`方法。这是一个简单的例子：

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
Document clone = doc.deepClone();
clone.save("Your Directory Path" + "CloneAndCombineDocuments.CloningDocument.docx");
```

此代码将创建原始文档的深度克隆并将其另存为新文件。

## 步骤 2：在替换点插入文档

您可以在另一个文档中的特定替换点插入文档。您可以这样做：

```java
Document mainDoc = new Document("Your Directory Path" + "Document insertion 1.docx");
FindReplaceOptions options = new FindReplaceOptions();
options.setDirection(FindReplaceDirection.BACKWARD);
options.setReplacingCallback(new InsertDocumentAtReplaceHandler());
mainDoc.getRange().replace(Pattern.compile("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.save("Your Directory Path" + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

在这个例子中，我们使用一个`FindReplaceOptions`对象来指定用于替换的回调处理程序。这`InsertDocumentAtReplaceHandler`类处理插入逻辑。

## 步骤 3：在书签处插入文档

要将文档插入到另一个文档中的特定书签处，可以使用以下代码：

```java
Document mainDoc = new Document("Your Directory Path" + "Document insertion 1.docx");
Document subDoc = new Document("Your Directory Path" + "Document insertion 2.docx");
Bookmark bookmark = mainDoc.getRange().getBookmarks().get("insertionPlace");
insertDocument(bookmark.getBookmarkStart().getParentNode(), subDoc);
mainDoc.save("Your Directory Path" + "CloneAndCombineDocuments.InsertDocumentAtBookmark.docx");
```

在这里，我们按名称查找书签并使用`insertDocument`方法插入内容`subDoc`书签位置处的文档。

## 步骤 4：在邮件合并期间插入文档

您可以在 Aspose.Words for Java 中的邮件合并操作期间插入文档。就是这样：

```java
Document mainDoc = new Document("Your Directory Path" + "Document insertion 1.docx");
mainDoc.getMailMerge().setFieldMergingCallback(new InsertDocumentAtMailMergeHandler());
mainDoc.getMailMerge().execute(new String[] { "Document_1" }, new Object[] { "Your Directory Path" + "Document insertion 2.docx" });
mainDoc.save("Your Directory Path" + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

在此示例中，我们使用以下命令设置字段合并回调`InsertDocumentAtMailMergeHandler`类来处理由“Document_1”字段指定的文档的插入。

## 结论

可以使用多种技术来完成 Aspose.Words for Java 中的克隆和合并文档。无论您需要克隆文档、在替换点、书签处插入内容，还是在邮件合并过程中，Aspose.Words 都提供了强大的功能来无缝操作文档。

## 常见问题解答

### 如何在 Aspose.Words for Java 中克隆文档？

您可以使用 Aspose.Words for Java 克隆文档`deepClone()`方法。这是一个例子：

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
Document clone = doc.deepClone();
clone.save("Your Directory Path" + "ClonedDocument.docx");
```

### 如何在书签处插入文档？

要在 Aspose.Words for Java 中的书签处插入文档，您可以按名称找到书签，然后使用`insertDocument`方法来插入内容。这是一个例子：

```java
Document mainDoc = new Document("Your Directory Path" + "MainDocument.docx");
Document subDoc = new Document("Your Directory Path" + "SubDocument.docx");
Bookmark bookmark = mainDoc.getRange().getBookmarks().get("MyBookmark");
insertDocument(bookmark.getBookmarkStart().getParentNode(), subDoc);
mainDoc.save("Your Directory Path" + "CombinedDocument.docx");
```

### 如何在 Aspose.Words for Java 中的邮件合并过程中插入文档？

您可以通过设置字段合并回调并指定要插入的文档，在 Aspose.Words for Java 中的邮件合并过程中插入文档。这是一个例子：

```java
Document mainDoc = new Document("Your Directory Path" + "MainDocument.docx");
mainDoc.getMailMerge().setFieldMergingCallback(new InsertDocumentAtMailMergeHandler());
mainDoc.getMailMerge().execute(new String[] { "DocumentField" }, new Object[] { "Your Directory Path" + "DocumentToInsert.docx" });
mainDoc.save("Your Directory Path" + "MergedDocument.docx");
```

在此示例中，`InsertDocumentAtMailMergeHandler`类处理邮件合并期间“DocumentField”的插入逻辑。