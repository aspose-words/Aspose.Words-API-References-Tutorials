---
title: Chèn mục lục vào tài liệu Word
linktitle: Chèn mục lục vào tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chèn mục lục vào tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/add-content-using-documentbuilder/insert-table-of-contents/
---
Trong hướng dẫn toàn diện này, bạn sẽ tìm hiểu cách chèn mục lục vào tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ hướng dẫn bạn thực hiện quy trình và cung cấp cho bạn các đoạn mã C# cần thiết. Đến cuối hướng dẫn này, bạn sẽ có thể tạo mục lục với các tiêu đề và số trang thích hợp.

## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo rằng bạn có các điều kiện tiên quyết sau:
- Thư viện Aspose.Words for .NET được cài đặt trên hệ thống của bạn.

## Bước 1: Tạo một tài liệu mới và DocumentBuilder
Để bắt đầu, hãy tạo một tài liệu mới bằng lớp Document và khởi tạo đối tượng DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 2: Chèn mục lục
Tiếp theo, sử dụng phương thức InsertTableOfContents của lớp DocumentBuilder để chèn mục lục. Chỉ định các tùy chọn định dạng cần thiết trong phương thức:

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## Bước 3: Thêm nội dung tài liệu
Sau khi chèn mục lục, hãy thêm nội dung tài liệu thực tế. Đặt kiểu tiêu đề thích hợp bằng StyleIdentifier:

```csharp
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## Bước 4: Cập nhật Mục lục
Mục lục mới được chèn ban đầu sẽ trống. Để điền nó, hãy cập nhật các trường trong tài liệu:

```csharp
doc.UpdateFields();
```

## Bước 5: Lưu tài liệu
Sau khi chèn mục lục và cập nhật các trường, hãy lưu tài liệu vào file bằng phương thức Save của lớp Document:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### Mã nguồn ví dụ để chèn mục lục bằng Aspose.Words cho .NET
Đây là mã nguồn hoàn chỉnh để chèn mục lục bằng Aspose.Words cho .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo DocumentBuilder với đối tượng Document
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Chèn bảng nội dung
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Bắt đầu nội dung tài liệu thực tế trên trang thứ hai.
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");


// Mục lục mới được chèn ban đầu sẽ trống.
// Nó cần được điền bằng cách cập nhật các trường trong tài liệu.
doc.UpdateFields();


doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

## Phần kết luận

Chúc mừng! Bạn đã học thành công cách chèn mục lục vào tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này và sử dụng mã nguồn được cung cấp, giờ đây bạn có thể tạo mục lục với các tiêu đề và số trang thích hợp cho tài liệu của mình.

### Hỏi đáp chèn mục lục vào văn bản word

#### Hỏi: Tôi có thể tùy chỉnh hình thức của mục lục không?

 Đáp: Có, bạn có thể tùy chỉnh hình thức của mục lục bằng cách sửa đổi các tùy chọn định dạng được chỉ định trong`InsertTableOfContents` phương pháp. Các tham số cho phép bạn kiểm soát số trang, thụt lề và các kiểu khác.

#### Hỏi: Điều gì sẽ xảy ra nếu tôi muốn đưa các cấp tiêu đề cụ thể vào mục lục?

 Đáp: Bạn có thể chỉ định mức tiêu đề mong muốn được đưa vào mục lục bằng cách điều chỉnh giá trị trong`InsertTableOfContents` phương pháp. Ví dụ, sử dụng`"\\o \"1-3\""` sẽ bao gồm các tiêu đề cấp 1 đến 3.

#### Hỏi: Tôi có thể tự động cập nhật mục lục nếu tôi thay đổi nội dung tài liệu không?

 Đáp: Có, bạn có thể cập nhật mục lục một cách tự động bằng cách gọi`UpdateFields` phương pháp trên tài liệu. Điều này sẽ đảm bảo rằng mọi thay đổi được thực hiện đối với nội dung tài liệu, chẳng hạn như thêm hoặc xóa tiêu đề, đều được phản ánh trong mục lục.

#### Câu hỏi: Làm cách nào để tạo kiểu khác nhau cho các cấp tiêu đề trong mục lục?

 Đáp: Bạn có thể tạo kiểu cho các cấp độ tiêu đề khác nhau bằng cách sử dụng các kiểu đoạn văn khác nhau cho từng cấp độ tiêu đề. Bằng cách phân công khác nhau`StyleIdentifier` các giá trị để`ParagraphFormat` sau đó`DocumentBuilder`, bạn có thể tạo các kiểu riêng biệt cho từng cấp độ tiêu đề.

#### Hỏi: Có thể thêm định dạng bổ sung cho các tiêu đề trong mục lục không?

 Đáp: Có, bạn có thể thêm định dạng bổ sung cho các tiêu đề trong mục lục, chẳng hạn như kiểu phông chữ, màu sắc hoặc các thuộc tính khác. Bằng cách điều chỉnh`Font` thuộc tính của`DocumentBuilder`, bạn có thể áp dụng định dạng tùy chỉnh cho các tiêu đề.