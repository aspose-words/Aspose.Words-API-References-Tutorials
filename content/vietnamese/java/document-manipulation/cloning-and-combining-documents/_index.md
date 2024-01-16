---
title: Nhân bản và kết hợp các tài liệu trong Aspose.Words cho Java
linktitle: Nhân bản và kết hợp tài liệu
second_title: API xử lý tài liệu Java Aspose.Words
description: Tìm hiểu cách sao chép và kết hợp các tài liệu trong Aspose.Words cho Java. Hướng dẫn từng bước với các ví dụ về mã nguồn.
type: docs
weight: 27
url: /vi/java/document-manipulation/cloning-and-combining-documents/
---

## Giới thiệu về Nhân bản và Kết hợp Tài liệu trong Aspose.Words cho Java

Trong hướng dẫn này, chúng ta sẽ khám phá cách sao chép và kết hợp các tài liệu bằng Aspose.Words cho Java. Chúng tôi sẽ đề cập đến nhiều tình huống khác nhau, bao gồm sao chép tài liệu, chèn tài liệu vào các điểm thay thế, dấu trang và trong các hoạt động trộn thư.

## Bước 1: Sao chép tài liệu

 Để sao chép một tài liệu trong Aspose.Words cho Java, bạn có thể sử dụng`deepClone()` phương pháp. Đây là một ví dụ đơn giản:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
Document clone = doc.deepClone();
clone.save("Your Directory Path" + "CloneAndCombineDocuments.CloningDocument.docx");
```

Mã này sẽ tạo một bản sao sâu của tài liệu gốc và lưu nó dưới dạng tệp mới.

## Bước 2: Chèn tài liệu tại điểm thay thế

Bạn có thể chèn tài liệu tại các điểm thay thế cụ thể trong tài liệu khác. Đây là cách bạn có thể làm điều đó:

```java
Document mainDoc = new Document("Your Directory Path" + "Document insertion 1.docx");
FindReplaceOptions options = new FindReplaceOptions();
options.setDirection(FindReplaceDirection.BACKWARD);
options.setReplacingCallback(new InsertDocumentAtReplaceHandler());
mainDoc.getRange().replace(Pattern.compile("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.save("Your Directory Path" + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

 Trong ví dụ này, chúng tôi sử dụng một`FindReplaceOptions` đối tượng để chỉ định trình xử lý gọi lại để thay thế. Các`InsertDocumentAtReplaceHandler` lớp xử lý logic chèn.

## Bước 3: Chèn tài liệu vào Bookmark

Để chèn tài liệu vào một dấu trang cụ thể trong tài liệu khác, bạn có thể sử dụng đoạn mã sau:

```java
Document mainDoc = new Document("Your Directory Path" + "Document insertion 1.docx");
Document subDoc = new Document("Your Directory Path" + "Document insertion 2.docx");
Bookmark bookmark = mainDoc.getRange().getBookmarks().get("insertionPlace");
insertDocument(bookmark.getBookmarkStart().getParentNode(), subDoc);
mainDoc.save("Your Directory Path" + "CloneAndCombineDocuments.InsertDocumentAtBookmark.docx");
```

 Ở đây, chúng ta tìm dấu trang theo tên và sử dụng`insertDocument` phương pháp chèn nội dung của`subDoc` tài liệu tại vị trí đánh dấu.

## Bước 4: Chèn tài liệu trong quá trình trộn thư

Bạn có thể chèn tài liệu trong quá trình trộn thư trong Aspose.Words for Java. Đây là cách thực hiện:

```java
Document mainDoc = new Document("Your Directory Path" + "Document insertion 1.docx");
mainDoc.getMailMerge().setFieldMergingCallback(new InsertDocumentAtMailMergeHandler());
mainDoc.getMailMerge().execute(new String[] { "Document_1" }, new Object[] { "Your Directory Path" + "Document insertion 2.docx" });
mainDoc.save("Your Directory Path" + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

 Trong ví dụ này, chúng tôi đặt lệnh gọi lại hợp nhất trường bằng cách sử dụng`InsertDocumentAtMailMergeHandler` lớp để xử lý việc chèn tài liệu được chỉ định bởi trường "Document_1".

## Phần kết luận

Nhân bản và kết hợp các tài liệu trong Aspose.Words cho Java có thể được thực hiện bằng nhiều kỹ thuật khác nhau. Cho dù bạn cần sao chép tài liệu, chèn nội dung tại các điểm thay thế, dấu trang hay trong khi trộn thư, Aspose.Words đều cung cấp các tính năng mạnh mẽ để thao tác tài liệu một cách liền mạch.

## Câu hỏi thường gặp

### Làm cách nào để sao chép tài liệu trong Aspose.Words cho Java?

 Bạn có thể sao chép một tài liệu trong Aspose.Words cho Java bằng cách sử dụng`deepClone()` phương pháp. Đây là một ví dụ:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
Document clone = doc.deepClone();
clone.save("Your Directory Path" + "ClonedDocument.docx");
```

### Làm cách nào tôi có thể chèn tài liệu vào dấu trang?

 Để chèn tài liệu vào dấu trang trong Aspose.Words cho Java, bạn có thể tìm dấu trang theo tên rồi sử dụng`insertDocument` phương pháp chèn nội dung. Đây là một ví dụ:

```java
Document mainDoc = new Document("Your Directory Path" + "MainDocument.docx");
Document subDoc = new Document("Your Directory Path" + "SubDocument.docx");
Bookmark bookmark = mainDoc.getRange().getBookmarks().get("MyBookmark");
insertDocument(bookmark.getBookmarkStart().getParentNode(), subDoc);
mainDoc.save("Your Directory Path" + "CombinedDocument.docx");
```

### Làm cách nào để chèn tài liệu trong quá trình trộn thư trong Aspose.Words cho Java?

Bạn có thể chèn tài liệu trong quá trình trộn thư trong Aspose.Words cho Java bằng cách đặt lệnh gọi lại hợp nhất trường và chỉ định tài liệu sẽ được chèn. Đây là một ví dụ:

```java
Document mainDoc = new Document("Your Directory Path" + "MainDocument.docx");
mainDoc.getMailMerge().setFieldMergingCallback(new InsertDocumentAtMailMergeHandler());
mainDoc.getMailMerge().execute(new String[] { "DocumentField" }, new Object[] { "Your Directory Path" + "DocumentToInsert.docx" });
mainDoc.save("Your Directory Path" + "MergedDocument.docx");
```

 Trong ví dụ này,`InsertDocumentAtMailMergeHandler`lớp xử lý logic chèn cho "DocumentField" trong quá trình trộn thư.