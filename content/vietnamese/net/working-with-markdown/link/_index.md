---
title: liên kết
linktitle: liên kết
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chèn liên kết bằng Aspose.Words cho .NET. Hướng dẫn từng bước một.
type: docs
weight: 10
url: /vi/net/working-with-markdown/link/
---

Trong ví dụ này, chúng tôi sẽ hướng dẫn bạn cách sử dụng tính năng liên kết với Aspose.Words cho .NET. Liên kết được sử dụng để tạo tài liệu tham khảo có thể nhấp vào các trang web hoặc tài liệu khác.

## Bước 1: Sử dụng trình tạo tài liệu

Đầu tiên, chúng tôi sẽ sử dụng trình tạo tài liệu để thêm nội dung vào tài liệu của mình.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Bước 2: Chèn liên kết

 Chúng ta có thể chèn một liên kết bằng cách sử dụng`Insertlink` phương pháp của trình tạo tài liệu. Chúng ta cần chỉ định văn bản liên kết, ở đây là "Aspose", cũng như URL đích.

```csharp
builder.Insertlink("Aspose", "https://www.aspose.com", sai);
```

### Mã nguồn ví dụ cho các liên kết với Aspose.Words cho .NET


```csharp
// Sử dụng trình tạo tài liệu để thêm nội dung vào tài liệu.
DocumentBuilder builder = new DocumentBuilder();

// Chèn đường dẫn.
builder.Insertlink("Aspose", "https://www.aspose.com", sai);
```
Xin chúc mừng! Bây giờ bạn đã học cách sử dụng tính năng liên kết với Aspose.Words cho .NET.


### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể liên kết tới một URL trong Aspose.Words?

 Trả lời: Để liên kết đến một địa chỉ URL trong Aspose.Words, bạn có thể sử dụng`<a>` gắn thẻ với`href` thuộc tính chứa địa chỉ URL. Ví dụ, bạn có thể sử dụng`<a href="https://www.aspose.com">Click Here</a>` để siêu liên kết đến URL "https://www.example.com " với văn bản hiển thị "Nhấp vào đây".

#### Câu hỏi: Có thể liên kết tới dấu trang nội bộ trong Aspose.Words không?

 Trả lời: Có, có thể liên kết đến dấu trang nội bộ trong Aspose.Words. Bạn có thể dùng`<a>` gắn thẻ với`href` thuộc tính chứa tên của dấu trang đứng trước dấu thăng (#). Ví dụ,`<a href="#bookmark1">Go to bookmark 1</a>` sẽ liên kết đến dấu trang có tên "bookmark1" trong tài liệu.

#### Câu hỏi: Làm cách nào tôi có thể tùy chỉnh văn bản hiển thị của liên kết trong Aspose.Words?

Trả lời: Để tùy chỉnh văn bản hiển thị của một liên kết trong Aspose.Words, bạn có thể sửa đổi nội dung giữa`<a>` thẻ. Ví dụ,`<a href="https://www.aspose.com">Click here</a>` sẽ hiển thị dòng chữ "Click here" dưới dạng siêu liên kết.

#### Câu hỏi: Tôi có thể chỉ định mục tiêu cho liên kết trong Aspose.Words không?

 Trả lời: Có, bạn có thể chỉ định mục tiêu cho liên kết trong Aspose.Words bằng cách sử dụng`target` thuộc tính của`<a>` nhãn. Ví dụ,`<a href="https://www.aspose.com" target="_blank">Open in new window</a>` sẽ mở liên kết trong một cửa sổ hoặc tab mới.