---
title: Thêm nội dung bằng DocumentBuilder trong Aspose.Words cho Java
linktitle: Thêm nội dung bằng DocumentBuilder
second_title: API xử lý tài liệu Java Aspose.Words
description: Tạo tài liệu bậc thầy với Aspose.Words cho Java. Hướng dẫn từng bước để thêm văn bản, bảng, hình ảnh và hơn thế nữa. Tạo tài liệu Word tuyệt đẹp một cách dễ dàng.
type: docs
weight: 26
url: /vi/java/document-manipulation/adding-content-using-documentbuilder/
---

## Giới thiệu về Thêm nội dung bằng DocumentBuilder trong Aspose.Words cho Java

Trong hướng dẫn từng bước này, chúng ta sẽ khám phá cách sử dụng Aspose.Words cho DocumentBuilder của Java để thêm nhiều loại nội dung khác nhau vào tài liệu Word. Chúng tôi sẽ đề cập đến việc chèn văn bản, bảng, quy tắc ngang, trường biểu mẫu, HTML, siêu liên kết, mục lục, hình ảnh nội tuyến và nổi, đoạn văn, v.v. Bắt đầu nào!

## Điều kiện tiên quyết

 Trước khi bắt đầu, hãy đảm bảo bạn đã thiết lập thư viện Aspose.Words for Java trong dự án của mình. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/words/java/).

## Thêm văn bản

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Chèn một đoạn văn bản đơn giản
builder.write("This is a simple text paragraph.");

// Lưu tài liệu
doc.save("path/to/your/document.docx");
```

## Thêm bảng

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Bắt đầu một bảng
Table table = builder.startTable();

// Chèn ô và nội dung
builder.insertCell();
builder.write("Cell 1");

builder.insertCell();
builder.write("Cell 2");

// Kết thúc bàn
builder.endTable();

// Lưu tài liệu
doc.save("path/to/your/document.docx");
```

## Thêm quy tắc ngang

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Chèn quy tắc ngang
builder.insertHorizontalRule();

// Lưu tài liệu
doc.save("path/to/your/document.docx");
```

## Thêm trường biểu mẫu

### Trường biểu mẫu nhập văn bản

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Chèn trường biểu mẫu nhập văn bản
builder.insertTextInput("TextInput", TextFormFieldType.REGULAR, "", "Default text", 0);

// Lưu tài liệu
doc.save("path/to/your/document.docx");
```

### Trường biểu mẫu hộp kiểm

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Chèn trường biểu mẫu hộp kiểm
builder.insertCheckBox("CheckBox", true, true, 0);

// Lưu tài liệu
doc.save("path/to/your/document.docx");
```

### Trường biểu mẫu hộp tổ hợp

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Xác định các mục cho hộp tổ hợp
String[] items = { "Option 1", "Option 2", "Option 3" };

// Chèn trường biểu mẫu hộp tổ hợp
builder.insertComboBox("DropDown", items, 0);

// Lưu tài liệu
doc.save("path/to/your/document.docx");
```

## Thêm HTML

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Chèn nội dung HTML
builder.insertHtml("<p>This is an HTML paragraph.</p>");

// Lưu tài liệu
doc.save("path/to/your/document.docx");
```

## Thêm siêu liên kết

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Chèn siêu liên kết
builder.write("Visit ");
builder.getFont().setColor(Color.BLUE);
builder.getFont().setUnderline(Underline.SINGLE);
builder.insertHyperlink("Aspose Website", "http://www.aspose.com", sai);
builder.getFont().clearFormatting();
builder.write(" for more information.");

// Lưu tài liệu
doc.save("path/to/your/document.docx");
```

## Thêm mục lục

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Chèn mục lục
builder.insertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Thêm nội dung tài liệu
// ...

// Cập nhật mục lục
doc.updateFields();

// Lưu tài liệu
doc.save("path/to/your/document.docx");
```

## Thêm hình ảnh

### Hình ảnh nội tuyến

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Chèn hình ảnh nội tuyến
builder.insertImage("path/to/your/image.png");

// Lưu tài liệu
doc.save("path/to/your/document.docx");
```

### Hình ảnh nổi

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Chèn hình ảnh nổi
builder.insertImage("path/to/your/image.png", RelativeHorizontalPosition.MARGIN, 100.0, RelativeVerticalPosition.MARGIN, 100.0, 200.0, 100.0, WrapType.SQUARE);

// Lưu tài liệu
doc.save("path/to/your/document.docx");
```

## Thêm đoạn văn

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Đặt định dạng đoạn văn
Font font = builder.getFont();
font.setSize(16.0);
font.setBold(true);
font.setColor(Color.BLUE);
font.setName("Arial");
font.setUnderline(Underline.DASH);

ParagraphFormat paragraphFormat = builder.getParagraphFormat();
paragraphFormat.setFirstLineIndent(8.0);
paragraphFormat.setAlignment(ParagraphAlignment.JUSTIFY);
paragraphFormat.setKeepTogether(true);

// Chèn một đoạn văn
builder.writeln("This is a formatted paragraph.");

// Lưu tài liệu
doc.save("path/to/your/document.docx");
```

## Bước 10: Di chuyển con trỏ

 Bạn có thể điều khiển vị trí con trỏ trong tài liệu bằng nhiều phương pháp khác nhau như`moveToParagraph`, `moveToCell`và hơn thế nữa. Đây là một ví dụ:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Di chuyển con trỏ đến một đoạn cụ thể
builder.moveToParagraph(2, 0);

// Thêm nội dung tại vị trí con trỏ mới
builder.writeln("This is the 3rd paragraph.");
```

Đây là một số thao tác phổ biến mà bạn có thể thực hiện bằng cách sử dụng Aspose.Words dành cho DocumentBuilder của Java. Khám phá tài liệu của thư viện để biết thêm các tính năng nâng cao và tùy chọn tùy chỉnh. Chúc bạn tạo tài liệu vui vẻ!


## Phần kết luận

Trong hướng dẫn toàn diện này, chúng tôi đã khám phá các khả năng của Aspose.Words dành cho DocumentBuilder của Java để thêm nhiều loại nội dung khác nhau vào tài liệu Word. Chúng tôi đã đề cập đến văn bản, bảng, quy tắc ngang, trường biểu mẫu, HTML, siêu liên kết, mục lục, hình ảnh, đoạn văn và chuyển động con trỏ.

## Câu hỏi thường gặp

### Hỏi: Aspose.Words dành cho Java là gì?

Trả lời: Aspose.Words for Java là thư viện Java cho phép các nhà phát triển tạo, sửa đổi và thao tác các tài liệu Microsoft Word theo chương trình. Nó cung cấp nhiều tính năng để tạo tài liệu, định dạng và chèn nội dung.

### Hỏi: Làm cách nào tôi có thể thêm mục lục vào tài liệu của mình?

Đáp: Để thêm mục lục, hãy sử dụng`DocumentBuilder` để chèn trường mục lục vào tài liệu của bạn. Đảm bảo cập nhật các trường trong tài liệu sau khi thêm nội dung để điền vào mục lục. Đây là một ví dụ:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Chèn trường mục lục
builder.insertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Thêm nội dung tài liệu
// ...

// Cập nhật mục lục
doc.updateFields();
```

### Câu hỏi: Làm cách nào để chèn hình ảnh vào tài liệu bằng Aspose.Words cho Java?

 Đáp: Bạn có thể chèn hình ảnh, cả nội tuyến và nổi, bằng cách sử dụng`DocumentBuilder`. Dưới đây là ví dụ của cả hai:

#### Hình ảnh nội tuyến:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Chèn hình ảnh nội tuyến
builder.insertImage("path/to/your/image.png");
```

#### Hình ảnh nổi:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Chèn hình ảnh nổi
builder.insertImage("path/to/your/image.png", RelativeHorizontalPosition.MARGIN, 100.0, RelativeVerticalPosition.MARGIN, 100.0, 200.0, 100.0, WrapType.SQUARE);
```

### Hỏi: Tôi có thể định dạng văn bản và đoạn văn khi thêm nội dung không?

 Đáp: Có, bạn có thể định dạng văn bản và đoạn văn bằng cách sử dụng`DocumentBuilder`. Bạn có thể đặt thuộc tính phông chữ, căn chỉnh đoạn văn, thụt lề, v.v. Đây là một ví dụ:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Đặt định dạng phông chữ và đoạn văn
Font font = builder.getFont();
font.setSize(16.0);
font.setBold(true);
font.setColor(Color.BLUE);
font.setName("Arial");
font.setUnderline(Underline.DASH);

ParagraphFormat paragraphFormat = builder.getParagraphFormat();
paragraphFormat.setFirstLineIndent(8.0);
paragraphFormat.setAlignment(ParagraphAlignment.JUSTIFY);
paragraphFormat.setKeepTogether(true);

// Chèn đoạn văn được định dạng
builder.writeln("This is a formatted paragraph.");
```

### Hỏi: Làm cách nào tôi có thể di chuyển con trỏ đến một vị trí cụ thể trong tài liệu?

 Đáp: Bạn có thể điều khiển vị trí con trỏ bằng các phương pháp như`moveToParagraph`, `moveToCell`và hơn thế nữa. Đây là một ví dụ:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Di chuyển con trỏ đến một đoạn cụ thể
builder.moveToParagraph(2, 0);

// Thêm nội dung tại vị trí con trỏ mới
builder.writeln("This is the 3rd paragraph.");
```

Đây là một số câu hỏi và câu trả lời phổ biến để giúp bạn bắt đầu với Aspose.Words dành cho DocumentBuilder của Java. Nếu bạn có thêm câu hỏi hoặc cần hỗ trợ thêm, hãy tham khảo[tài liệu của thư viện](https://reference.aspose.com/words/java/) hoặc tìm kiếm sự trợ giúp từ cộng đồng Aspose.Words và các tài nguyên hỗ trợ.