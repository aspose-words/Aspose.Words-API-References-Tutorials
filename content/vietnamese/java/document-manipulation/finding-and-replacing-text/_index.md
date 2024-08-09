---
title: Tìm và thay thế văn bản trong Aspose.Words cho Java
linktitle: Tìm và thay thế văn bản
second_title: API xử lý tài liệu Java Aspose.Words
description: Tìm hiểu cách tìm và thay thế văn bản trong tài liệu Word bằng Aspose.Words cho Java. Hướng dẫn từng bước với các ví dụ về mã. Nâng cao kỹ năng thao tác tài liệu Java của bạn.
type: docs
weight: 15
url: /vi/java/document-manipulation/finding-and-replacing-text/
---

## Giới thiệu về Tìm và Thay thế Văn bản trong Aspose.Words cho Java

Aspose.Words for Java là một API Java mạnh mẽ cho phép bạn làm việc với các tài liệu Word theo chương trình. Một trong những công việc thường gặp khi xử lý văn bản Word là tìm và thay thế văn bản. Cho dù bạn cần cập nhật phần giữ chỗ trong mẫu hay thực hiện các thao tác văn bản phức tạp hơn, Aspose.Words for Java có thể giúp bạn đạt được mục tiêu của mình một cách hiệu quả.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào chi tiết tìm và thay thế văn bản, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

- Môi trường phát triển Java
- Thư viện Aspose.Words cho Java
- Một tài liệu Word mẫu để làm việc

 Bạn có thể tải xuống thư viện Aspose.Words cho Java từ[đây](https://releases.aspose.com/words/java/).

## Tìm và thay thế văn bản đơn giản

```java
// Tải tài liệu
Document doc = new Document("your-document.docx");

// Tạo Trình tạo tài liệu
DocumentBuilder builder = new DocumentBuilder(doc);

// Tìm và thay thế văn bản
builder.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// Lưu tài liệu đã sửa đổi
doc.save("modified-document.docx");
```

 Trong ví dụ này, chúng tôi tải một tài liệu Word, tạo một`DocumentBuilder` , và sử dụng`replace` phương pháp tìm và thay thế "văn bản cũ" bằng "văn bản mới" trong tài liệu.

## Sử dụng biểu thức chính quy

Biểu thức chính quy cung cấp khả năng khớp mẫu mạnh mẽ để tìm kiếm và thay thế văn bản. Aspose.Words for Java hỗ trợ các biểu thức chính quy cho các hoạt động tìm và thay thế nâng cao hơn.

```java
// Tải tài liệu
Document doc = new Document("your-document.docx");

// Tạo Trình tạo tài liệu
DocumentBuilder builder = new DocumentBuilder(doc);

// Sử dụng biểu thức chính quy để tìm và thay thế văn bản
Pattern regex = Pattern.compile("your-pattern");
builder.getRange().replace(regex, "replacement-text", new FindReplaceOptions());

// Lưu tài liệu đã sửa đổi
doc.save("modified-document.docx");
```

Trong ví dụ này, chúng tôi sử dụng mẫu biểu thức chính quy để tìm và thay thế văn bản trong tài liệu.

## Bỏ qua văn bản bên trong các trường

Bạn có thể định cấu hình Aspose.Words để bỏ qua văn bản bên trong các trường khi thực hiện thao tác tìm và thay thế.

```java
// Tải tài liệu
Document doc = new Document("your-document.docx");

// Tạo một phiên bản FindReplaceOptions và đặt IgnoreFields thành true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreFields(true);

// Sử dụng các tùy chọn khi thay thế văn bản
doc.getRange().replace("text-to-replace", "new-text", options);

// Lưu tài liệu đã sửa đổi
doc.save("modified-document.docx");
```

Điều này hữu ích khi bạn muốn loại trừ văn bản bên trong các trường, chẳng hạn như trường hợp nhất, khỏi bị thay thế.

## Bỏ qua văn bản bên trong Xóa bản sửa đổi

Bạn có thể định cấu hình Aspose.Words để bỏ qua văn bản bên trong các bản sửa đổi xóa trong quá trình tìm và thay thế.

```java
// Tải tài liệu
Document doc = new Document("your-document.docx");

// Tạo một phiên bản FindReplaceOptions và đặt IgnoreDeleted thành true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreDeleted(true);

// Sử dụng các tùy chọn khi thay thế văn bản
doc.getRange().replace("text-to-replace", "new-text", options);

// Lưu tài liệu đã sửa đổi
doc.save("modified-document.docx");
```

Điều này cho phép bạn loại trừ văn bản đã được đánh dấu để xóa trong các thay đổi được theo dõi khỏi bị thay thế.

## Bỏ qua văn bản bên trong Chèn bản sửa đổi

Bạn có thể định cấu hình Aspose.Words để bỏ qua văn bản bên trong chèn các bản sửa đổi trong quá trình tìm và thay thế.

```java
// Tải tài liệu
Document doc = new Document("your-document.docx");

// Tạo một phiên bản FindReplaceOptions và đặt IgnoreInserted thành true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreInserted(true);

// Sử dụng các tùy chọn khi thay thế văn bản
doc.getRange().replace("text-to-replace", "new-text", options);

// Lưu tài liệu đã sửa đổi
doc.save("modified-document.docx");
```

Điều này cho phép bạn loại trừ văn bản đã được đánh dấu là đã chèn vào các thay đổi được theo dõi khỏi bị thay thế.

## Thay thế văn bản bằng HTML

Bạn có thể sử dụng Aspose.Words for Java để thay thế văn bản bằng nội dung HTML.

```java
// Tải tài liệu
Document doc = new Document("your-document.docx");

// Tạo một phiên bản FindReplaceOptions bằng lệnh gọi lại thay thế tùy chỉnh
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceWithHtmlEvaluator(options));

// Sử dụng các tùy chọn khi thay thế văn bản
doc.getRange().replace("text-to-replace", "new-html-content", options);

// Lưu tài liệu đã sửa đổi
doc.save("modified-document.docx");
```

 Trong ví dụ này, chúng tôi sử dụng tùy chỉnh`ReplaceWithHtmlEvaluator` để thay thế văn bản bằng nội dung HTML.

## Thay thế văn bản trong đầu trang và chân trang

Bạn có thể tìm và thay thế văn bản trong đầu trang và chân trang của tài liệu Word.

```java
// Tải tài liệu
Document doc = new Document("your-document.docx");

// Nhận bộ sưu tập đầu trang và chân trang
HeaderFooterCollection headersFooters = doc.getFirstSection().getHeadersFooters();

// Chọn loại đầu trang hoặc chân trang mà bạn muốn thay thế văn bản (ví dụ: HeaderFooterType.FOOTER_PRIMARY)
HeaderFooter footer = headersFooters.getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);

// Tạo một phiên bản FindReplaceOptions và áp dụng nó cho phạm vi của chân trang
FindReplaceOptions options = new FindReplaceOptions();
footer.getRange().replace("text-to-replace", "new-text", options);

// Lưu tài liệu đã sửa đổi
doc.save("modified-document.docx");
```

Điều này cho phép bạn thực hiện thay thế văn bản cụ thể ở đầu trang và chân trang.

## Hiển thị các thay đổi cho thứ tự đầu trang và chân trang

Bạn có thể sử dụng Aspose.Words để hiển thị các thay đổi đối với thứ tự đầu trang và chân trang trong tài liệu của mình.

```java
// Tải tài liệu
Document doc = new Document("your-document.docx");

// Lấy phần đầu tiên
Section firstPageSection = doc.getFirstSection();

// Tạo một phiên bản FindReplaceOptions và áp dụng nó vào phạm vi của tài liệu
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceLog());

//Thay thế văn bản ảnh hưởng đến thứ tự đầu trang và chân trang
doc.getRange().replace(Pattern.compile("(header|footer)"), "", options);

// Lưu tài liệu đã sửa đổi
doc.save("modified-document.docx");
```

Điều này cho phép bạn hình dung các thay đổi liên quan đến thứ tự đầu trang và chân trang trong tài liệu của bạn.

## Thay thế văn bản bằng các trường

Bạn có thể thay thế văn bản bằng các trường bằng Aspose.Words cho Java.

```java
// Tải tài liệu
Document doc = new Document("your-document.docx");

// Tạo một phiên bản FindReplaceOptions và đặt lệnh gọi lại thay thế tùy chỉnh cho các trường
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceTextWithFieldHandler(FieldType.FIELD_MERGE_FIELD));

// Sử dụng các tùy chọn khi thay thế văn bản
doc.getRange().replace(Pattern.compile("PlaceHolder(\\d+)"), "", options);

// Lưu tài liệu đã sửa đổi
doc.save("modified-document.docx");
```

 Trong ví dụ này, chúng tôi thay thế văn bản bằng các trường và chỉ định loại trường (ví dụ:`FieldType.FIELD_MERGE_FIELD`).

## Thay thế bằng Người đánh giá

Bạn có thể sử dụng trình đánh giá tùy chỉnh để xác định văn bản thay thế một cách linh hoạt.

```java
// Tải tài liệu
Document doc = new Document("your-document.docx");

// Tạo một phiên bản FindReplaceOptions và đặt lệnh gọi lại thay thế tùy chỉnh
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new MyReplaceEvaluator());

// Sử dụng các tùy chọn khi thay thế văn bản
doc.getRange().replace(Pattern.compile("[s|m]ad"), "", options);

// Lưu tài liệu đã sửa đổi
doc.save("modified-document.docx");
```

Trong ví dụ này, chúng tôi sử dụng bộ đánh giá tùy chỉnh (`MyReplaceEvaluator`) để thay thế văn bản.

## Thay thế bằng Regex

Aspose.Words for Java cho phép bạn thay thế văn bản bằng các biểu thức thông thường.

```java
// Tải tài liệu
Document doc = new Document("your-document.docx");

// Sử dụng biểu thức chính quy để tìm và thay thế văn bản
doc.getRange().replace(Pattern.compile("[s|m]ad"), "bad", new FindReplaceOptions());

// Lưu tài liệu đã sửa đổi
doc.save("modified-document.docx");
```

Trong ví dụ này, chúng tôi sử dụng mẫu biểu thức chính quy để tìm và thay thế văn bản trong tài liệu.

## Nhận biết và thay thế trong các mô hình thay thế

Bạn có thể nhận biết và thực hiện thay thế trong các mẫu thay thế bằng Aspose.Words cho Java.

```java
// Tải tài liệu
Document doc = new Document("your-document.docx");

//Tạo một phiên bản FindReplaceOptions với UseSubstitutions được đặt thành true
FindReplaceOptions options = new FindReplaceOptions();
options.setUseSubstitutions(true);

// Sử dụng các tùy chọn khi thay thế văn bản bằng mẫu
doc.getRange().replace(Pattern.compile("([A-z]+) give money to ([A-z]+)"), "$2 take money from $1", options);

// Lưu tài liệu đã sửa đổi
doc.save("modified-document.docx");
```

Điều này cho phép bạn thực hiện thay thế trong các mẫu thay thế cho các thay thế nâng cao hơn.

## Thay thế bằng một chuỗi

Bạn có thể thay thế văn bản bằng một chuỗi đơn giản bằng Aspose.Words for Java.

```java
// Tải tài liệu
Document doc = new Document("your-document.docx");

// Thay thế văn bản bằng một chuỗi
doc.getRange().replace("text-to-replace", "new-string", new FindReplaceOptions());

// Lưu tài liệu đã sửa đổi
doc.save("modified-document.docx");
```

Trong ví dụ này, chúng tôi thay thế "văn bản cần thay thế" bằng "chuỗi mới" trong tài liệu.

## Sử dụng đơn đặt hàng kế thừa

Bạn có thể sử dụng thứ tự kế thừa khi thực hiện các thao tác tìm và thay thế.

```java
// Tải tài liệu
Document doc = new Document("your-document.docx");

// Tạo một phiên bản FindReplaceOptions và đặt UseLegacyOrder thành true
FindReplaceOptions options = new FindReplaceOptions();
options.setUseLegacyOrder(true);

// Sử dụng các tùy chọn khi thay thế văn bản
doc.getRange().replace(Pattern.compile("\\[(.*?)\\]"), "", options);

// Lưu tài liệu đã sửa đổi
doc.save("modified-document.docx");
```

Điều này cho phép bạn sử dụng thứ tự kế thừa cho các hoạt động tìm và thay thế.

## Thay thế văn bản trong bảng

Bạn có thể tìm và thay thế văn bản trong các bảng trong tài liệu Word của mình.

```java
// Tải tài liệu
Document doc = new Document("your-document.docx");

// Nhận một bảng cụ thể (ví dụ: bảng đầu tiên)
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);

// Sử dụng FindReplaceOptions để thay thế văn bản trong bảng
table.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// Lưu tài liệu đã sửa đổi
doc.save("modified-document.docx");
```

Điều này cho phép bạn thực hiện thay thế văn bản cụ thể trong các bảng.

## Phần kết luận

Aspose.Words for Java cung cấp khả năng toàn diện để tìm và thay thế văn bản trong tài liệu Word. Cho dù bạn cần thực hiện các thay thế văn bản đơn giản hay các thao tác nâng cao hơn bằng cách sử dụng biểu thức thông thường, thao tác trường hoặc bộ đánh giá tùy chỉnh, Aspose.Words for Java đều đáp ứng được nhu cầu của bạn. Đảm bảo khám phá các tài liệu và ví dụ mở rộng do Aspose cung cấp để khai thác toàn bộ tiềm năng của thư viện Java mạnh mẽ này.

## Câu hỏi thường gặp

### Làm cách nào để tải xuống Aspose.Words cho Java?

 Bạn có thể tải xuống Aspose.Words cho Java từ trang web bằng cách truy cập[liên kết này](https://releases.aspose.com/words/java/).

### Tôi có thể sử dụng biểu thức chính quy để thay thế văn bản không?

Có, bạn có thể sử dụng biểu thức chính quy để thay thế văn bản trong Aspose.Words for Java. Điều này cho phép bạn thực hiện các hoạt động tìm và thay thế nâng cao và linh hoạt hơn.

### Làm cách nào tôi có thể bỏ qua văn bản bên trong các trường trong quá trình thay thế?

 Để bỏ qua văn bản bên trong các trường trong quá trình thay thế, bạn có thể đặt`IgnoreFields` tài sản của`FindReplaceOptions` ĐẾN`true`Điều này đảm bảo rằng văn bản trong các trường, chẳng hạn như trường hợp nhất, sẽ bị loại khỏi phần thay thế.

### Tôi có thể thay thế văn bản bên trong đầu trang và chân trang không?

 Có, bạn có thể thay thế văn bản bên trong đầu trang và chân trang của tài liệu Word. Chỉ cần truy cập vào đầu trang hoặc chân trang thích hợp và sử dụng`replace` phương pháp với mong muốn`FindReplaceOptions`.

### Tùy chọn UseLegacyOrder để làm gì?

 các`UseLegacyOrder` tùy chọn trong`FindReplaceOptions` cho phép bạn sử dụng thứ tự kế thừa khi thực hiện các thao tác tìm và thay thế. Điều này có thể hữu ích trong một số trường hợp nhất định khi mong muốn có hành vi đặt hàng kế thừa.