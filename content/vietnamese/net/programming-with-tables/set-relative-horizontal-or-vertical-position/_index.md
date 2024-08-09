---
title: Đặt vị trí ngang hoặc dọc tương đối
linktitle: Đặt vị trí ngang hoặc dọc tương đối
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách đặt vị trí ngang và dọc tương đối cho các bảng trong tài liệu Word bằng Aspose.Words cho .NET với hướng dẫn từng bước này.
type: docs
weight: 10
url: /vi/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---
## Giới thiệu

Bạn đã bao giờ cảm thấy bế tắc với cách định vị bảng theo cách bạn muốn trong tài liệu Word của mình chưa? Vâng, bạn không đơn độc. Cho dù bạn đang tạo một báo cáo chuyên nghiệp hay một tài liệu quảng cáo đầy phong cách, việc căn chỉnh các bảng có thể tạo ra sự khác biệt rất lớn. Đó là lúc Aspose.Words dành cho .NET phát huy tác dụng. Hướng dẫn này sẽ hướng dẫn bạn từng bước cách đặt vị trí ngang hoặc dọc tương đối cho các bảng trong tài liệu Word của bạn. Hãy đi sâu vào!

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có những điều sau:

1.  Aspose.Words for .NET: Nếu chưa có, bạn có thể tải xuống[đây](https://releases.aspose.com/words/net/).
2. Môi trường phát triển: Visual Studio hoặc bất kỳ IDE tương thích .NET nào khác.
3. Kiến thức cơ bản về C#: Hướng dẫn này giả định rằng bạn đã quen thuộc với những kiến thức cơ bản về lập trình C#.

## Nhập không gian tên

Trước tiên, bạn cần nhập các không gian tên cần thiết. Điều này rất cần thiết để truy cập các chức năng của Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

## Bước 1: Tải tài liệu của bạn

Để bắt đầu, bạn cần tải tài liệu Word của mình vào chương trình. Đây là cách bạn có thể làm điều đó:

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Đoạn mã này thiết lập đường dẫn đến thư mục tài liệu của bạn và tải tài liệu cụ thể mà bạn muốn làm việc. Đảm bảo đường dẫn tài liệu của bạn chính xác để tránh mọi sự cố tải.

## Bước 2: Truy cập bảng

Tiếp theo, chúng ta cần truy cập vào bảng trong tài liệu. Thông thường, bạn sẽ muốn làm việc với bảng đầu tiên trong phần nội dung.

```csharp
Table table = doc.FirstSection.Body.Tables[0];
```

Dòng mã này tìm nạp bảng đầu tiên từ nội dung tài liệu. Nếu tài liệu của bạn có nhiều bảng, bạn có thể điều chỉnh chỉ mục cho phù hợp.

## Bước 3: Đặt vị trí nằm ngang

Bây giờ, hãy đặt vị trí nằm ngang của bảng so với một phần tử cụ thể. Trong ví dụ này, chúng tôi sẽ định vị nó so với cột.

```csharp
table.HorizontalAnchor = RelativeHorizontalPosition.Column;
```

 Bằng cách thiết lập`HorizontalAnchor` ĐẾN`RelativeHorizontalPosition.Column`, bạn đang yêu cầu bảng tự căn chỉnh theo chiều ngang đối với cột chứa nó.

## Bước 4: Đặt vị trí dọc

Tương tự như định vị theo chiều ngang, bạn cũng có thể đặt vị trí theo chiều dọc. Ở đây, chúng tôi định vị nó so với trang.

```csharp
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

 Thiết lập`VerticalAnchor` ĐẾN`RelativeVerticalPosition.Page` đảm bảo bảng được căn chỉnh theo chiều dọc theo trang.

## Bước 5: Lưu tài liệu của bạn

Cuối cùng, lưu các thay đổi của bạn vào một tài liệu mới. Đây là một bước quan trọng để đảm bảo những thay đổi của bạn được giữ nguyên.

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

Lệnh này lưu tài liệu đã sửa đổi bằng tên mới, đảm bảo bạn không ghi đè lên tệp gốc của mình.

## Phần kết luận

Và bạn có nó! Bạn đã đặt thành công vị trí ngang và dọc tương đối cho bảng trong tài liệu Word bằng Aspose.Words for .NET. Với kỹ năng mới này, bạn có thể nâng cao bố cục và khả năng đọc tài liệu của mình, khiến chúng trông chuyên nghiệp và bóng bẩy hơn. Hãy tiếp tục thử nghiệm các vị trí khác nhau và xem vị trí nào phù hợp nhất với nhu cầu của bạn.

## Câu hỏi thường gặp

### Tôi có thể định vị các bảng so với các phần tử khác không?  
Có, Aspose.Words cho phép bạn định vị các bảng tương ứng với các thành phần khác nhau như lề, trang, cột, v.v.

### Tôi có cần giấy phép để sử dụng Aspose.Words cho .NET không?  
 Có, bạn có thể mua giấy phép[đây](https://purchase.aspose.com/buy) hoặc lấy giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).

### Có bản dùng thử miễn phí dành cho Aspose.Words cho .NET không?  
 Tuyệt đối! Bạn có thể tải về dùng thử miễn phí[đây](https://releases.aspose.com/).

### Tôi có thể sử dụng Aspose.Words với các ngôn ngữ lập trình khác không?  
Aspose.Words được thiết kế chủ yếu cho .NET, nhưng có sẵn các phiên bản dành cho Java, Python và các nền tảng khác.

### Tôi có thể tìm tài liệu chi tiết hơn ở đâu?  
Để biết thêm thông tin chuyên sâu, hãy xem tài liệu Aspose.Words[đây](https://reference.aspose.com/words/net/).