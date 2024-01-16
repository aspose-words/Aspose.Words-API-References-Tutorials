---
title: Quy tắc ngang
linktitle: Quy tắc ngang
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chèn quy tắc ngang với Hướng dẫn từng bước của Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/working-with-markdown/horizontal-rule/
---

Trong ví dụ này, chúng tôi sẽ hướng dẫn bạn cách sử dụng tính năng quy tắc ngang với Aspose.Words cho .NET. Quy tắc ngang được sử dụng để phân tách trực quan các phần của tài liệu.

## Bước 1: Sử dụng trình tạo tài liệu

Đầu tiên, chúng tôi sẽ sử dụng trình tạo tài liệu để thêm nội dung vào tài liệu của mình.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Bước 2: Chèn thước ngang

 Chúng ta có thể chèn một thước ngang bằng cách sử dụng`InsertHorizontalRule` phương pháp của trình tạo tài liệu.

```csharp
builder. InsertHorizontalRule();
```

## Mã nguồn mẫu cho quy tắc ngang với Aspose.Words for .NET

```csharp
// Sử dụng trình tạo tài liệu để thêm nội dung vào tài liệu.
DocumentBuilder builder = new DocumentBuilder();

// Chèn quy tắc ngang.
builder.InsertHorizontalRule();
```

Xin chúc mừng! Bây giờ bạn đã học cách sử dụng tính năng quy tắc ngang với Aspose.Words cho .NET.


### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào để tạo thước ngang trong Markdown?

Trả lời: Để tạo thước ngang trong Markdown, bạn có thể sử dụng một trong các ký hiệu sau trên một dòng trống: ba dấu hoa thị (\***), ba dấu gạch ngang (\---), hoặc ba dấu gạch dưới (\___).

#### Câu hỏi: Tôi có thể tùy chỉnh giao diện của thước ngang trong Markdown không?

Trả lời: Trong Markdown tiêu chuẩn, không có cách nào để tùy chỉnh giao diện của thước ngang. Tuy nhiên, một số trình chỉnh sửa và tiện ích mở rộng Markdown nâng cao cung cấp các tính năng tùy chỉnh bổ sung.

#### Câu hỏi: Tất cả các trình soạn thảo Markdown có hỗ trợ thước ngang không?

Trả lời: Có, hầu hết các trình soạn thảo Markdown phổ biến đều hỗ trợ thước ngang. Tuy nhiên, tốt nhất bạn nên kiểm tra tài liệu của nhà cung cấp cụ thể để đảm bảo tài liệu đó được hỗ trợ.

#### Câu hỏi: Tôi có thể tạo những yếu tố nào khác trong Markdown?

Trả lời: Ngoài thước ngang, bạn có thể tạo tiêu đề, đoạn văn, danh sách, liên kết, hình ảnh, bảng, v.v. trong Markdown.