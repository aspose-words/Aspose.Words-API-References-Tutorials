---
title: Danh sách có dấu đầu dòng
linktitle: Danh sách có dấu đầu dòng
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tạo danh sách có dấu đầu dòng với Hướng dẫn từng bước của Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/working-with-markdown/bulleted-list/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách tạo danh sách có dấu đầu dòng bằng Aspose.Words cho .NET. Danh sách có dấu đầu dòng được sử dụng để liệt kê các mục mà không sử dụng cách đánh số.

## Bước 1: Sử dụng trình tạo tài liệu

Đầu tiên, chúng tôi sẽ sử dụng trình tạo tài liệu để thêm nội dung vào tài liệu của mình.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Bước 2: Áp dụng danh sách có dấu đầu dòng mặc định

 Chúng ta có thể áp dụng danh sách có dấu đầu dòng mặc định bằng cách sử dụng trình tạo tài liệu`ApplyBulletDefault` phương pháp.

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## Bước 3: Tùy chỉnh định dạng Bullet

 Chúng ta có thể tùy chỉnh định dạng dấu đầu dòng bằng cách truy cập các thuộc tính của`ListFormat.List.ListLevels[0]`. Trong ví dụ này, chúng tôi sử dụng dấu gạch ngang "-" làm dấu đầu dòng.

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## Bước 4: Thêm mục vào danh sách

 Bây giờ chúng ta có thể thêm các mục vào danh sách có dấu đầu dòng bằng cách sử dụng trình tạo tài liệu`Writeln` phương pháp.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Bước 5: Loại bỏ thụt lề khỏi danh sách

 Nếu muốn tạo một danh sách con, chúng ta có thể tăng mức thụt lề bằng cách sử dụng`ListFormat.ListIndent()` phương pháp. Trong ví dụ này, chúng tôi đang thêm danh sách phụ vào mục 2a và 2b.

```csharp
builder.ListFormat.ListIndent();
builder. Writeln("Element 2a");
builder.Writeln("Element 2b");
```
### Mã nguồn mẫu cho Danh sách dấu đầu dòng sử dụng Aspose.Words cho .NET


```csharp
// Sử dụng trình tạo tài liệu để thêm nội dung vào tài liệu.
DocumentBuilder builder = new DocumentBuilder();

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

Xin chúc mừng! Bây giờ bạn đã học cách tạo danh sách có dấu đầu dòng bằng Aspose.Words cho .NET.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào để tạo danh sách có dấu đầu dòng trong Markdown?

Đáp: Để tạo danh sách có dấu đầu dòng trong Markdown, hãy bắt đầu mỗi mục danh sách bằng ký hiệu dấu đầu dòng (`-`, `*` , hoặc`+`), theo sau là khoảng trắng.

#### Câu hỏi: Bạn có thể lồng các danh sách có dấu đầu dòng trong Markdown không?

Trả lời: Có, có thể lồng các danh sách có dấu đầu dòng trong Markdown bằng cách thêm bốn khoảng trắng bù trừ trước mỗi mục danh sách lồng nhau.

#### Q: Làm cách nào để tùy chỉnh biểu tượng dấu đầu dòng?

Trả lời: Trong Markdown tiêu chuẩn, ký hiệu dấu đầu dòng được xác định trước. Tuy nhiên, một số trình chỉnh sửa Markdown cho phép bạn tùy chỉnh chúng bằng các tiện ích mở rộng cụ thể.

#### Câu hỏi: Danh sách có dấu đầu dòng trong Markdown có hỗ trợ thụt lề không?

Đáp: Có, danh sách có dấu đầu dòng trong Markdown hỗ trợ thụt lề. Bạn có thể thêm dịch chuyển trái bằng cách sử dụng dấu cách hoặc tab.

#### Câu hỏi: Có thể thêm liên kết hoặc văn bản nội tuyến vào danh sách các mục không?

Đáp: Có, bạn có thể thêm liên kết hoặc văn bản nội tuyến vào danh sách các mục bằng cú pháp Markdown thích hợp.
