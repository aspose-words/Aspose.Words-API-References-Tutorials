---
title: Danh sách có dấu đầu dòng
linktitle: Danh sách có dấu đầu dòng
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tạo và tùy chỉnh danh sách dấu đầu dòng trong tài liệu Word bằng Aspose.Words cho .NET với hướng dẫn từng bước này.
type: docs
weight: 10
url: /vi/net/working-with-markdown/bulleted-list/
---
## Giới thiệu

Bạn đã sẵn sàng đi sâu vào thế giới Aspose.Words dành cho .NET chưa? Hôm nay, chúng ta sẽ hướng dẫn cách tạo danh sách có dấu đầu dòng trong tài liệu Word của bạn. Cho dù bạn đang sắp xếp ý tưởng, liệt kê các mục hay chỉ thêm một chút cấu trúc vào tài liệu của mình, danh sách có dấu đầu dòng đều cực kỳ tiện dụng. Vì vậy, hãy bắt đầu!

## Điều kiện tiên quyết

Trước khi bắt đầu cuộc vui viết mã, hãy đảm bảo bạn có mọi thứ mình cần:

1.  Aspose.Words for .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.Words. Nếu bạn chưa có nó, bạn có thể[tải nó ở đây](https://releases.aspose.com/words/net/).
2. Môi trường phát triển: Môi trường phát triển AC# như Visual Studio.
3. Kiến thức C# cơ bản: Hiểu biết cơ bản về lập trình C# sẽ giúp bạn theo dõi.

## Nhập không gian tên

Trước tiên, hãy nhập các không gian tên cần thiết. Điều này giống như thiết lập giai đoạn để mã của chúng tôi chạy trơn tru.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Lists;
```

Bây giờ, hãy chia quy trình thành các bước dễ dàng và dễ quản lý.

## Bước 1: Tạo một tài liệu mới

Được rồi, hãy bắt đầu bằng cách tạo một tài liệu mới. Đây là nơi tất cả các phép thuật sẽ xảy ra.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Bước 2: Áp dụng định dạng danh sách dấu đầu dòng

Tiếp theo, chúng ta sẽ áp dụng định dạng danh sách dấu đầu dòng. Điều này cho tài liệu biết rằng chúng ta sắp bắt đầu một danh sách có dấu đầu dòng.

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## Bước 3: Tùy chỉnh danh sách dấu đầu dòng

Tại đây, chúng ta sẽ tùy chỉnh danh sách dấu đầu dòng theo ý thích. Trong ví dụ này, chúng tôi sẽ sử dụng dấu gạch ngang (-) làm dấu đầu dòng.

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## Bước 4: Thêm mục danh sách

Bây giờ, hãy thêm một số mục vào danh sách có dấu đầu dòng của chúng ta. Đây là nơi bạn có thể sáng tạo và thêm bất kỳ nội dung nào bạn cần.

```csharp
builder.Writeln("Item 1");
builder.Writeln("Item 2");
```

## Bước 5: Thêm mục phụ

Để làm cho mọi thứ thú vị hơn, hãy thêm một số mục phụ trong "Mục 2". Điều này giúp tổ chức các điểm phụ.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
builder.ListFormat.ListOutdent(); // Quay lại cấp độ danh sách chính
```

## Phần kết luận

Và bạn có nó! Bạn vừa tạo danh sách có dấu đầu dòng trong tài liệu Word bằng Aspose.Words cho .NET. Đó là một quy trình đơn giản nhưng cực kỳ hiệu quả để sắp xếp tài liệu của bạn. Cho dù bạn đang tạo danh sách đơn giản hay danh sách lồng nhau phức tạp, Aspose.Words đều có thể hỗ trợ bạn.

Hãy thoải mái thử nghiệm các kiểu và định dạng danh sách khác nhau để phù hợp với nhu cầu của bạn. Chúc mừng mã hóa!

## Câu hỏi thường gặp

### Tôi có thể sử dụng các ký hiệu dấu đầu dòng khác nhau trong danh sách không?
    Có, bạn có thể tùy chỉnh các ký hiệu dấu đầu dòng bằng cách thay đổi`NumberFormat` tài sản.

### Làm cách nào để thêm nhiều mức thụt lề hơn?
    Sử dụng`ListIndent` phương pháp để thêm nhiều cấp độ hơn và`ListOutdent` để quay trở lại cấp độ cao hơn.

### Có thể trộn lẫn danh sách dấu đầu dòng và số?
   Tuyệt đối! Bạn có thể chuyển đổi giữa định dạng dấu đầu dòng và số bằng cách sử dụng`ApplyNumberDefault`Và`ApplyBulletDefault` phương pháp.

### Tôi có thể tạo kiểu cho văn bản trong các mục danh sách không?
    Có, bạn có thể áp dụng các kiểu, phông chữ và định dạng khác nhau cho văn bản trong các mục danh sách bằng cách sử dụng`Font` tài sản của`DocumentBuilder`.

### Làm cách nào để tạo danh sách có dấu đầu dòng nhiều cột?
   Bạn có thể sử dụng định dạng bảng để tạo danh sách nhiều cột, trong đó mỗi ô chứa một danh sách có dấu đầu dòng riêng biệt.