---
title: Sử dụng tùy chọn dọn dẹp trong Aspose.Words cho Java
linktitle: Sử dụng tùy chọn dọn dẹp
second_title: API xử lý tài liệu Java Aspose.Words
description: Nâng cao độ rõ ràng của tài liệu với Aspose.Words cho các tùy chọn dọn dẹp Java. Tìm hiểu cách xóa các đoạn trống, các vùng không sử dụng, v.v.
type: docs
weight: 10
url: /vi/java/document-manipulation/using-cleanup-options/
---

## Giới thiệu về Sử dụng Tùy chọn Dọn dẹp trong Aspose.Words cho Java

Trong hướng dẫn này, chúng ta sẽ khám phá cách sử dụng các tùy chọn dọn dẹp trong Aspose.Words cho Java để thao tác và dọn dẹp tài liệu trong quá trình trộn thư. Các tùy chọn dọn dẹp cho phép bạn kiểm soát các khía cạnh khác nhau của việc dọn dẹp tài liệu, chẳng hạn như xóa các đoạn văn trống, các vùng không sử dụng, v.v.

## Điều kiện tiên quyết

 Trước khi chúng ta bắt đầu, hãy đảm bảo rằng bạn đã tích hợp thư viện Aspose.Words for Java vào dự án của mình. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/words/java/).

## Bước 1: Xóa đoạn văn trống

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Chèn các trường hợp nhất
FieldMergeField mergeFieldOption1 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_1");
mergeFieldOption1.setFieldName("Option_1");
builder.write(" ? ");
FieldMergeField mergeFieldOption2 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_2");
mergeFieldOption2.setFieldName("Option_2");

// Đặt tùy chọn dọn dẹp
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS);

// Bật tính năng dọn dẹp đoạn văn có dấu chấm câu
doc.getMailMerge().setCleanupParagraphsWithPunctuationMarks(true);

// Thực hiện trộn thư
doc.getMailMerge().execute(new String[] { "Option_1", "Option_2" }, new Object[] { null, null });

// Lưu tài liệu
doc.save("WorkingWithCleanupOptions.CleanupParagraphsWithPunctuationMarks.docx");
```

Trong ví dụ này, chúng tôi tạo một tài liệu mới, chèn các trường hợp nhất và đặt các tùy chọn dọn dẹp để xóa các đoạn văn trống. Ngoài ra, chúng tôi cho phép loại bỏ các đoạn văn có dấu chấm câu. Sau khi thực hiện phối thư, tài liệu sẽ được lưu với quá trình dọn dẹp đã chỉ định được áp dụng.

## Bước 2: Xóa các vùng chưa được hợp nhất

```java
Document doc = new Document("Your Directory Path" + "Mail merge destination - Northwind suppliers.docx");
DataSet data = new DataSet();

// Đặt tùy chọn dọn dẹp để xóa các vùng không sử dụng
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS);

// Thực hiện trộn thư theo vùng
doc.getMailMerge().executeWithRegions(data);

// Lưu tài liệu
doc.save("WorkingWithCleanupOptions.RemoveUnmergedRegions.docx");
```

Trong ví dụ này, chúng tôi mở một tài liệu hiện có với các vùng phối, đặt các tùy chọn dọn dẹp để loại bỏ các vùng không sử dụng, sau đó thực hiện phối thư với dữ liệu trống. Quá trình này sẽ tự động loại bỏ các vùng không sử dụng khỏi tài liệu.

## Bước 3: Xóa các trường trống

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Đặt tùy chọn dọn dẹp để xóa các trường trống
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_FIELDS);

// Thực hiện trộn thư
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Lưu tài liệu
doc.save("WorkingWithCleanupOptions.RemoveEmptyFields.docx");
```

Trong ví dụ này, chúng tôi mở tài liệu có trường phối, đặt tùy chọn dọn dẹp để xóa trường trống và thực hiện phối thư với dữ liệu. Sau khi hợp nhất, mọi trường trống sẽ bị xóa khỏi tài liệu.

## Bước 4: Xóa các trường không sử dụng

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Đặt tùy chọn dọn dẹp để xóa các trường không sử dụng
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS);

// Thực hiện trộn thư
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Lưu tài liệu
doc.save("WorkingWithCleanupOptions.RemoveUnusedFields.docx");
```

Trong ví dụ này, chúng tôi mở một tài liệu có các trường phối, đặt các tùy chọn dọn dẹp để loại bỏ các trường không sử dụng và thực hiện phối thư với dữ liệu. Sau khi hợp nhất, mọi trường không sử dụng sẽ bị xóa khỏi tài liệu.

## Bước 5: Xóa các trường chứa

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Đặt tùy chọn dọn dẹp để xóa các trường có chứa
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS);

// Thực hiện trộn thư
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Lưu tài liệu
doc.save("WorkingWithCleanupOptions.RemoveContainingFields.docx");
```

Trong ví dụ này, chúng tôi mở một tài liệu có các trường phối, đặt các tùy chọn dọn dẹp để xóa các trường chứa và thực hiện phối thư với dữ liệu. Sau khi hợp nhất, các trường đó sẽ bị xóa khỏi tài liệu.

## Bước 6: Xóa các hàng trống trong bảng

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Đặt tùy chọn dọn dẹp để xóa các hàng trống trong bảng
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS);

// Thực hiện trộn thư
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Lưu tài liệu
doc.save("WorkingWithCleanupOptions.RemoveEmptyTableRows.docx");
```

Trong ví dụ này, chúng tôi mở tài liệu có bảng và hợp nhất các trường, đặt tùy chọn dọn dẹp để xóa các hàng trống trong bảng và thực hiện phối thư với dữ liệu. Sau khi hợp nhất, mọi hàng trống trong bảng sẽ bị xóa khỏi tài liệu.

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách sử dụng các tùy chọn dọn dẹp trong Aspose.Words dành cho Java để thao tác và dọn dẹp tài liệu trong quá trình trộn thư. Các tùy chọn này cung cấp khả năng kiểm soát chi tiết đối với việc dọn dẹp tài liệu, cho phép bạn tạo các tài liệu bóng bẩy và tùy chỉnh một cách dễ dàng.

## Câu hỏi thường gặp

### Các tùy chọn dọn dẹp trong Aspose.Words cho Java là gì?

Tùy chọn dọn dẹp trong Aspose.Words cho Java là các cài đặt cho phép bạn kiểm soát các khía cạnh khác nhau của việc dọn dẹp tài liệu trong quá trình trộn thư. Chúng cho phép bạn loại bỏ các yếu tố không cần thiết như đoạn văn trống, vùng không sử dụng, v.v., đảm bảo tài liệu cuối cùng của bạn có cấu trúc tốt và bóng bẩy.

### Làm cách nào để xóa các đoạn trống khỏi tài liệu của tôi?

 Để xóa các đoạn trống khỏi tài liệu của bạn bằng Aspose.Words cho Java, bạn có thể đặt`MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS` tùy chọn thành đúng. Điều này sẽ tự động loại bỏ những đoạn văn không có nội dung, giúp tài liệu trở nên sạch sẽ hơn.

###  Mục đích của việc này là gì`REMOVE_UNUSED_REGIONS` cleanup option?

 Các`MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS` tùy chọn được sử dụng để xóa các vùng trong tài liệu không có dữ liệu tương ứng trong quá trình trộn thư. Nó giúp giữ tài liệu của bạn gọn gàng bằng cách loại bỏ các phần giữ chỗ không sử dụng.

### Tôi có thể xóa các hàng trong bảng trống khỏi tài liệu bằng Aspose.Words cho Java không?

 Có, bạn có thể xóa các hàng trống khỏi tài liệu bằng cách đặt`MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS`tùy chọn dọn dẹp thành đúng. Thao tác này sẽ tự động xóa bất kỳ hàng nào trong bảng không chứa dữ liệu, đảm bảo bảng có cấu trúc tốt trong tài liệu của bạn.

###  Điều gì xảy ra khi tôi đặt`REMOVE_CONTAINING_FIELDS` option?

 Thiết lập`MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS` tùy chọn sẽ xóa toàn bộ trường phối, bao gồm cả đoạn chứa nó, khỏi tài liệu trong quá trình phối thư. Điều này hữu ích khi bạn muốn loại bỏ các trường hợp nhất và văn bản liên quan của chúng.

### Làm cách nào để xóa các trường hợp nhất không sử dụng khỏi tài liệu của tôi?

 Để loại bỏ các trường hợp nhất không được sử dụng khỏi tài liệu, bạn có thể đặt`MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS` tùy chọn thành đúng. Điều này sẽ tự động loại bỏ các trường phối không được điền trong quá trình phối thư, mang lại tài liệu sạch hơn.

###  Sự khác biệt giữa`REMOVE_EMPTY_FIELDS` and `REMOVE_UNUSED_FIELDS` cleanup options?

 Các`REMOVE_EMPTY_FIELDS` tùy chọn loại bỏ các trường phối không có dữ liệu hoặc trống trong quá trình phối thư. Mặt khác,`REMOVE_UNUSED_FIELDS`tùy chọn loại bỏ các trường hợp nhất không được điền dữ liệu trong quá trình hợp nhất. Lựa chọn giữa chúng phụ thuộc vào việc bạn muốn loại bỏ các trường không có nội dung hay những trường không được sử dụng trong thao tác phối cụ thể.

### Làm cách nào tôi có thể kích hoạt tính năng xóa các đoạn văn có dấu chấm câu?

 Để cho phép loại bỏ các đoạn văn có dấu chấm câu, bạn có thể đặt`cleanupParagraphsWithPunctuationMarks` tùy chọn thành true và chỉ định các dấu chấm câu cần xem xét để dọn dẹp. Điều này cho phép bạn tạo một tài liệu tinh tế hơn bằng cách loại bỏ các đoạn văn chỉ có dấu câu không cần thiết.

### Tôi có thể tùy chỉnh các tùy chọn dọn dẹp trong Aspose.Words cho Java không?

Có, bạn có thể tùy chỉnh các tùy chọn dọn dẹp theo nhu cầu cụ thể của mình. Bạn có thể chọn các tùy chọn dọn dẹp để áp dụng và định cấu hình chúng theo yêu cầu dọn dẹp tài liệu của mình, đảm bảo rằng tài liệu cuối cùng đáp ứng các tiêu chuẩn mong muốn của bạn.