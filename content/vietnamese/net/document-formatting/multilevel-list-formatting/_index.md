---
title: Định dạng danh sách đa cấp trong tài liệu Word
linktitle: Định dạng danh sách đa cấp trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tạo danh sách nhiều cấp độ và áp dụng định dạng tùy chỉnh trong tài liệu word với Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/document-formatting/multilevel-list-formatting/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách sử dụng tính năng định dạng danh sách đa cấp trong tài liệu word với Aspose.Words cho .NET. Hãy làm theo các bước bên dưới để hiểu mã nguồn và áp dụng các thay đổi.

## Bước 1: Tạo và cấu hình tài liệu

Để bắt đầu, hãy tạo một tài liệu mới và đối tượng DocumentBuilder liên quan. Đây là cách thực hiện:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 2: Định dạng danh sách đa cấp

Bây giờ chúng ta sẽ áp dụng định dạng danh sách đa cấp bằng cách sử dụng các phương thức có sẵn trong đối tượng DocumentBuilder. Đây là cách thực hiện:

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder. Writen("Element 2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.1");
builder.Writeln("Element 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.2.1");
builder.Writeln("Element 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 3");

builder.ListFormat.RemoveNumbers();
```

## Bước 3: Lưu tài liệu

 Sau khi chèn trường biểu mẫu nhập văn bản, hãy lưu tài liệu vào vị trí mong muốn bằng cách sử dụng`Save` phương pháp. Đảm bảo cung cấp đường dẫn tệp thích hợp:

```csharp
doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");
```

### Mã nguồn mẫu cho Định dạng danh sách đa cấp bằng Aspose.Words cho .NET

Đây là mã nguồn hoàn chỉnh cho tính năng định dạng danh sách đa cấp với Aspose.Words cho .NET:


```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyNumberDefault();
builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.1");
builder.Writeln("Item 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.2.1");
builder.Writeln("Item 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 3");

builder.ListFormat.RemoveNumbers();

doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");

```

Với mã này, bạn sẽ có thể tạo danh sách nhiều cấp và áp dụng định dạng phù hợp cho từng cấp bằng cách sử dụng Aspose.Words for .NET.


## Phần kết luận

Trong hướng dẫn này, chúng ta đã khám phá quy trình sử dụng tính năng định dạng danh sách đa cấp trong tài liệu Word với Aspose.Words cho .NET. Bằng cách làm theo các bước đã nêu, bạn có thể tạo danh sách được tổ chức tốt với nhiều cấp độ, nâng cao cấu trúc và khả năng đọc tài liệu của mình.

### Câu hỏi thường gặp

#### Hỏi: Danh sách đa cấp trong tài liệu Word là gì?

Trả lời: Danh sách nhiều cấp trong tài liệu Word là danh sách phân cấp cho phép bạn sắp xếp các mục thành nhiều cấp độ mục phụ khác nhau. Nó giúp trình bày thông tin một cách có cấu trúc, giúp người đọc dễ hiểu nội dung hơn.

#### Câu hỏi: Tôi có thể tùy chỉnh giao diện của danh sách đa cấp không?

Trả lời: Có, bạn có thể tùy chỉnh giao diện của danh sách đa cấp trong tài liệu Word của mình. Bằng cách áp dụng các kiểu khác nhau, chẳng hạn như dấu đầu dòng, số hoặc chữ cái, đồng thời điều chỉnh thụt lề và khoảng cách, bạn có thể tạo một danh sách có tổ chức và hấp dẫn về mặt trực quan.

#### Câu hỏi: Aspose.Words for .NET có hỗ trợ các tùy chọn định dạng danh sách khác không?

Đáp: Có, Aspose.Words for .NET cung cấp một bộ tính năng toàn diện để định dạng danh sách. Nó hỗ trợ nhiều loại danh sách khác nhau, bao gồm danh sách có dấu đầu dòng, danh sách được đánh số và danh sách đa cấp. Bạn có thể thao tác định dạng danh sách, thêm hoặc xóa các mục và tùy chỉnh giao diện của chúng.

#### Câu hỏi: Tôi có thể sử dụng Aspose.Words cho .NET để làm việc với các thành phần tài liệu khác không?

Đáp: Có, Aspose.Words for .NET cung cấp các khả năng mở rộng để làm việc với nhiều thành phần tài liệu khác nhau, chẳng hạn như đoạn văn, bảng, hình ảnh, v.v. Nó cho phép bạn tạo, sửa đổi và chuyển đổi tài liệu Word theo chương trình, hợp lý hóa các tác vụ xử lý tài liệu.