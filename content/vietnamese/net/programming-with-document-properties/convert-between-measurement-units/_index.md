---
title: Chuyển đổi giữa các đơn vị đo lường
linktitle: Chuyển đổi giữa các đơn vị đo lường
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chuyển đổi đơn vị đo lường trong Aspose.Words cho .NET. Làm theo hướng dẫn từng bước của chúng tôi để đặt lề, đầu trang và chân trang của tài liệu theo inch và điểm.
type: docs
weight: 10
url: /vi/net/programming-with-document-properties/convert-between-measurement-units/
---
## Giới thiệu

Này! Bạn có phải là nhà phát triển làm việc với tài liệu Word bằng Aspose.Words cho .NET không? Nếu vậy, bạn có thể thường thấy mình cần đặt lề, đầu trang hoặc chân trang theo các đơn vị đo lường khác nhau. Việc chuyển đổi giữa các đơn vị như inch và điểm có thể khó khăn nếu bạn không quen với các chức năng của thư viện. Trong hướng dẫn toàn diện này, chúng tôi sẽ hướng dẫn bạn quy trình chuyển đổi giữa các đơn vị đo lường bằng Aspose.Words cho .NET. Hãy cùng đi sâu vào và đơn giản hóa những chuyển đổi đó!

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có những điều sau:

1.  Aspose.Words for .NET Library: Nếu bạn chưa có, hãy tải xuống[đây](https://releases.aspose.com/words/net/).
2. Môi trường phát triển: Visual Studio hoặc bất kỳ IDE tương thích .NET nào khác.
3. Kiến thức cơ bản về C#: Hiểu những kiến thức cơ bản về C# sẽ giúp bạn dễ dàng theo dõi.
4.  Giấy phép Aspose: Tùy chọn nhưng được khuyến nghị để có đầy đủ chức năng. Bạn có thể có được giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).

## Nhập không gian tên

Trước tiên, bạn cần nhập các không gian tên cần thiết. Điều này rất quan trọng để truy cập các lớp và phương thức do Aspose.Words cung cấp.

```csharp
using Aspose.Words;
using Aspose.Words.Layout;
```

Hãy chia nhỏ quy trình chuyển đổi đơn vị đo lường trong Aspose.Words cho .NET. Hãy làm theo các bước chi tiết sau để thiết lập và tùy chỉnh lề và khoảng cách cho tài liệu của bạn.

## Bước 1: Tạo một tài liệu mới

Trước tiên, bạn cần tạo một tài liệu mới bằng Aspose.Words.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Thao tác này sẽ khởi tạo một tài liệu Word mới và một`DocumentBuilder` để tạo điều kiện thuận lợi cho việc tạo và định dạng nội dung.

## Bước 2: Truy cập thiết lập trang

 Để đặt lề, đầu trang và chân trang, bạn cần truy cập vào`PageSetup` sự vật.

```csharp
PageSetup pageSetup = builder.PageSetup;
```

Điều này cho phép bạn truy cập vào các thuộc tính thiết lập trang khác nhau như lề, khoảng cách đầu trang và khoảng cách chân trang.

## Bước 3: Chuyển đổi inch thành điểm

 Aspose.Words sử dụng điểm làm đơn vị đo lường theo mặc định. Để đặt lề theo inch, bạn cần chuyển đổi inch thành điểm bằng cách sử dụng`ConvertUtil.InchToPoint` phương pháp.

```csharp
pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
```

Dưới đây là bảng phân tích về chức năng của từng dòng:
- Đặt lề trên và lề dưới thành 1 inch (chuyển đổi thành điểm).
- Đặt lề trái và lề phải thành 1,5 inch (chuyển đổi thành điểm).
- Đặt khoảng cách đầu trang và chân trang thành 0,2 inch (chuyển đổi thành điểm).

## Bước 4: Lưu tài liệu

Cuối cùng, lưu tài liệu của bạn để đảm bảo tất cả các thay đổi được áp dụng.

```csharp
doc.Save("ConvertedDocument.docx");
```

Thao tác này sẽ lưu tài liệu của bạn với lề và khoảng cách được chỉ định theo điểm.

## Phần kết luận

Và bạn có nó! Bạn đã chuyển đổi và đặt thành công lề cũng như khoảng cách trong tài liệu Word bằng Aspose.Words for .NET. Bằng cách làm theo các bước này, bạn có thể dễ dàng xử lý các chuyển đổi đơn vị khác nhau, giúp quá trình tùy chỉnh tài liệu của bạn trở nên dễ dàng. Hãy tiếp tục thử nghiệm các cài đặt khác nhau và khám phá các chức năng phong phú mà Aspose.Words cung cấp. Chúc mừng mã hóa!

## Câu hỏi thường gặp

### Tôi có thể chuyển đổi các đơn vị khác như cm thành điểm bằng Aspose.Words không?
 Có, Aspose.Words cung cấp các phương thức như`ConvertUtil.CmToPoint` để chuyển đổi centimet thành điểm.

### Giấy phép có cần thiết để sử dụng Aspose.Words cho .NET không?
Mặc dù bạn có thể sử dụng Aspose.Words mà không cần giấy phép nhưng một số tính năng nâng cao có thể bị hạn chế. Có được giấy phép đảm bảo đầy đủ chức năng.

### Làm cách nào để cài đặt Aspose.Words cho .NET?
 Bạn có thể tải nó xuống từ[trang web](https://releases.aspose.com/words/net/) và làm theo hướng dẫn cài đặt.

### Tôi có thể đặt các đơn vị khác nhau cho các phần khác nhau của tài liệu không?
 Có, bạn có thể tùy chỉnh lề và các cài đặt khác cho các phần khác nhau bằng cách sử dụng`Section` lớp học.

### Aspose.Words cung cấp những tính năng nào khác?
 Aspose.Words hỗ trợ nhiều tính năng bao gồm chuyển đổi tài liệu, trộn thư và các tùy chọn định dạng mở rộng. Kiểm tra[tài liệu](https://reference.aspose.com/words/net/) để biết thêm chi tiết.