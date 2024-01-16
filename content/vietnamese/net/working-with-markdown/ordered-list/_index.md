---
title: Danh sách được yêu cầu
linktitle: Danh sách được yêu cầu
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tạo danh sách có thứ tự với Aspose.Words for .NET Hướng dẫn từng bước.
type: docs
weight: 10
url: /vi/net/working-with-markdown/ordered-list/
---

Trong ví dụ này, chúng tôi sẽ giải thích cách sử dụng chức năng danh sách có thứ tự với Aspose.Words cho .NET. Danh sách có thứ tự cho phép bạn sắp xếp các mục một cách tuần tự bằng các con số.

## Bước 1: Sử dụng trình tạo tài liệu

Đầu tiên, chúng ta sẽ sử dụng trình tạo tài liệu để tạo tài liệu mới.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 2: Áp dụng định dạng danh sách có thứ tự

 Chúng tôi sẽ áp dụng định dạng danh sách có thứ tự bằng cách sử dụng trình tạo tài liệu`ApplyBulletDefault`phương pháp. Chúng ta cũng có thể tùy chỉnh định dạng đánh số bằng cách vào các cấp độ danh sách và đặt định dạng mà chúng ta muốn.

```csharp
builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";
```

## Bước 3: Thêm mục vào danh sách

 Chúng ta có thể thêm các mục vào danh sách bằng cách sử dụng trình tạo tài liệu`Writeln` phương pháp.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Bước 4: Thụt lề danh sách

 Chúng ta có thể thụt lề danh sách bằng cách sử dụng trình tạo tài liệu`ListIndent` phương pháp.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

## Bước 5: Lưu tài liệu

Cuối cùng, chúng ta có thể lưu tài liệu ở định dạng mong muốn.

### Mã nguồn mẫu cho danh sách có thứ tự với Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

Xin chúc mừng! Bây giờ bạn đã học cách sử dụng tính năng danh sách có thứ tự với Aspose.Words cho .NET.


### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào để tạo danh sách có thứ tự trong Markdown?

Trả lời: Để tạo danh sách có thứ tự trong Markdown, hãy bắt đầu mỗi mục danh sách bằng một số, theo sau là dấu chấm (`1.`, `2.`, `3.`), theo sau là khoảng trắng.

#### Câu hỏi: Chúng tôi có thể lồng các danh sách theo thứ tự trong Markdown không?

Trả lời: Có, có thể lồng các danh sách có thứ tự trong Markdown bằng cách thêm bốn khoảng trắng bù trừ trước mỗi mục danh sách lồng nhau.

#### Hỏi: Làm cách nào để tùy chỉnh việc đánh số danh sách theo thứ tự?

Trả lời: Trong Markdown tiêu chuẩn, việc đánh số danh sách theo thứ tự được tạo tự động. Tuy nhiên, một số trình chỉnh sửa Markdown cho phép bạn tùy chỉnh nó bằng các tiện ích mở rộng cụ thể.

#### Câu hỏi: Danh sách thứ tự trong Markdown có hỗ trợ thụt lề không?

Đáp: Có, danh sách được sắp xếp theo thứ tự trong Markdown hỗ trợ thụt lề. Bạn có thể thêm dịch chuyển trái bằng cách sử dụng dấu cách hoặc tab.

#### Câu hỏi: Có thể thêm liên kết hoặc văn bản nội tuyến vào danh sách các mục không?

Đáp: Có, bạn có thể thêm liên kết hoặc văn bản nội tuyến vào danh sách các mục bằng cú pháp Markdown thích hợp.