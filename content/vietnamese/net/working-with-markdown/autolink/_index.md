---
title: Tự động liên kết
linktitle: Tự động liên kết
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chèn liên kết tự động bằng Aspose.Words for .NET Hướng dẫn từng bước.
type: docs
weight: 10
url: /vi/net/working-with-markdown/autolink/
---

Trong ví dụ này, chúng tôi sẽ giải thích cách sử dụng tính năng "Tự động liên kết" với Aspose.Words cho .NET. Tính năng này cho phép bạn tự động chèn siêu liên kết vào tài liệu của mình.

## Bước 1: Sử dụng trình tạo tài liệu

Đầu tiên, chúng tôi sẽ sử dụng trình tạo tài liệu để thêm nội dung vào tài liệu của mình.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Bước 2: Chèn siêu liên kết

 Chúng ta có thể chèn một siêu liên kết bằng cách sử dụng`InsertHyperlink` phương pháp của trình tạo tài liệu. Chúng tôi chỉ định URL và văn bản sẽ hiển thị cho liên kết.

```csharp
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", sai);
```

## Bước 3: Chèn địa chỉ email dưới dạng liên kết

Chúng tôi cũng có thể chèn địa chỉ email dưới dạng liên kết bằng tiền tố "mailto:". Điều này sẽ cho phép người dùng nhấp vào liên kết để mở ứng dụng email khách mặc định của họ.

```csharp
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```

## Bước 4: Lưu tài liệu

Cuối cùng, chúng ta có thể lưu tài liệu ở định dạng mong muốn.

### Mã nguồn mẫu cho Autolink sử dụng Aspose.Words for .NET


```csharp
// Sử dụng trình tạo tài liệu để thêm nội dung vào tài liệu.
DocumentBuilder builder = new DocumentBuilder();

// Chèn siêu liên kết.
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", sai);
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```


Xin chúc mừng! Bây giờ bạn đã học cách sử dụng tính năng "Tự động liên kết" với Aspose.Words cho .NET.


### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể tạo liên kết tự động đến địa chỉ URL trong Aspose.Words?

 Trả lời: Để tạo liên kết tự động đến địa chỉ URL trong Aspose.Words, bạn có thể sử dụng`<a>` gắn thẻ với`href` thuộc tính chứa địa chỉ URL. Ví dụ, bạn có thể sử dụng`<a href="https://www.aspose.com">https://www.aspose.com</a>` để tự động liên kết đến "https://www.aspose.com".

#### Câu hỏi: Có thể tùy chỉnh văn bản hiển thị của liên kết tự động trong Aspose.Words không?

 Trả lời: Có, bạn có thể tùy chỉnh văn bản hiển thị của liên kết tự động trong Aspose.Words. Thay vì sử dụng địa chỉ URL làm văn bản hiển thị, bạn có thể sử dụng bất kỳ văn bản nào khác bằng cách thay thế nội dung giữa`<a>` thẻ. Ví dụ, bạn có thể sử dụng`<a href="https://www.aspose.com">Click here</a>` để hiển thị dòng chữ "Click vào đây" dưới dạng liên kết tự động.

#### Câu hỏi: Làm cách nào tôi có thể thêm các thuộc tính bổ sung vào liên kết tự động trong Aspose.Words?

Trả lời: Để thêm các thuộc tính bổ sung vào liên kết tự động trong Aspose.Words, bạn có thể sử dụng các thuộc tính HTML bổ sung bên trong`<a>` nhãn. Ví dụ, bạn có thể sử dụng`<a href="https://www.aspose.com" target="_blank">Link</a>` để mở liên kết trong một cửa sổ hoặc tab mới bằng cách sử dụng` attribute target="_blank"`.