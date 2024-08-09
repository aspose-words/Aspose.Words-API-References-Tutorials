---
title: Danh sách đặt hàng
linktitle: Danh sách đặt hàng
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tạo danh sách có thứ tự trong tài liệu Word bằng Aspose.Words cho .NET với hướng dẫn từng bước của chúng tôi. Hoàn hảo để tự động hóa việc tạo tài liệu.
type: docs
weight: 10
url: /vi/net/working-with-markdown/ordered-list/
---
## Giới thiệu

Vì vậy, bạn đã quyết định đi sâu vào Aspose.Words for .NET để tạo các tài liệu Word tuyệt vời theo chương trình. Sự lựa chọn tuyệt vời! Hôm nay, chúng ta sẽ chia sẻ cách tạo danh sách có thứ tự trong tài liệu Word. Chúng tôi sẽ thực hiện từng bước một, vì vậy, cho dù bạn là người mới viết mã hay một chuyên gia dày dạn kinh nghiệm, bạn sẽ thấy hướng dẫn này cực kỳ hữu ích. Hãy bắt đầu!

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào mã, có một số điều bạn cần:

1. Aspose.Words for .NET: Đảm bảo bạn đã cài đặt Aspose.Words for .NET. Nếu không, bạn có thể tải xuống[đây](https://releases.aspose.com/words/net/).
2. Môi trường phát triển: Visual Studio hoặc bất kỳ IDE tương thích .NET nào khác.
3. Kiến thức cơ bản về C#: Bạn nên nắm vững kiến thức cơ bản về C# để dễ dàng theo dõi.

## Nhập không gian tên

Để sử dụng Aspose.Words trong dự án của bạn, bạn cần nhập các không gian tên cần thiết. Điều này giống như việc thiết lập hộp công cụ của bạn trước khi bắt đầu làm việc.

```csharp
using Aspose.Words;
using Aspose.Words.Lists;
```

Hãy chia mã thành các bước nhỏ và giải thích từng phần. Sẵn sàng? Chúng ta đi đây!

## Bước 1: Khởi tạo tài liệu

Trước tiên, bạn cần tạo một tài liệu mới. Hãy coi điều này giống như việc mở một tài liệu Word trống trên máy tính của bạn.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Ở đây, chúng ta đang khởi tạo một tài liệu mới và một đối tượng DocumentBuilder. DocumentBuilder giống như chiếc bút của bạn, cho phép bạn viết nội dung vào tài liệu.

## Bước 2: Áp dụng định dạng danh sách đánh số

Bây giờ, hãy áp dụng định dạng danh sách được đánh số mặc định. Điều này giống như việc thiết lập tài liệu Word của bạn để sử dụng các dấu đầu dòng được đánh số.

```csharp
builder.ListFormat.ApplyNumberDefault();
```

Dòng mã này thiết lập việc đánh số cho danh sách của bạn. Dễ dàng phải không?

## Bước 3: Thêm mục danh sách

Tiếp theo, hãy thêm một số mục vào danh sách của chúng tôi. Hãy tưởng tượng bạn đang ghi lại một danh sách hàng tạp hóa.

```csharp
builder.Writeln("Item 1");
builder.Writeln("Item 2");
```

Với những dòng này, bạn đang thêm hai mục đầu tiên vào danh sách của mình.

## Bước 4: Thụt lề danh sách

Nếu bạn muốn thêm các mục con vào một mục thì sao? Hãy làm điều đó!

```csharp
builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

 các`ListIndent` phương thức thụt lề danh sách, tạo danh sách phụ. Bây giờ bạn đang tạo một danh sách phân cấp, giống như một danh sách việc cần làm lồng nhau.

## Phần kết luận

Việc tạo danh sách có thứ tự trong tài liệu Word theo chương trình lúc đầu có vẻ khó khăn, nhưng với Aspose.Words cho .NET, điều đó thật dễ dàng. Bằng cách làm theo các bước đơn giản này, bạn có thể dễ dàng thêm và quản lý danh sách trong tài liệu của mình. Cho dù bạn đang tạo báo cáo, tạo tài liệu có cấu trúc hay chỉ tự động hóa quy trình làm việc của mình, Aspose.Words for .NET đều có thể giúp bạn. Vì vậy, tại sao phải chờ đợi? Bắt đầu viết mã và xem điều kỳ diệu diễn ra!

## Câu hỏi thường gặp

### Tôi có thể tùy chỉnh kiểu đánh số của danh sách không?  
 Có, bạn có thể tùy chỉnh kiểu đánh số bằng cách sử dụng`ListFormat`của cải. Bạn có thể đặt các kiểu đánh số khác nhau như chữ số La Mã, chữ cái, v.v.

### Làm cách nào để thêm nhiều mức thụt lề hơn?  
 Bạn có thể sử dụng`ListIndent` nhiều lần để tạo ra các cấp độ danh sách phụ sâu hơn. Mỗi cuộc gọi đến`ListIndent` thêm một mức thụt lề.

### Tôi có thể trộn lẫn các dấu đầu dòng và danh sách đánh số không?  
 Tuyệt đối! Bạn có thể áp dụng các định dạng danh sách khác nhau trong cùng một tài liệu bằng cách sử dụng`ListFormat` tài sản.

### Có thể tiếp tục đánh số từ danh sách trước đó không?  
Có, bạn có thể tiếp tục đánh số bằng cách sử dụng cùng một định dạng danh sách. Aspose.Words cho phép bạn kiểm soát việc đánh số danh sách trên các đoạn văn khác nhau.

### Làm cách nào để xóa định dạng danh sách?  
 Bạn có thể xóa định dạng danh sách bằng cách gọi`ListFormat.RemoveNumbers()`. Điều này sẽ biến các mục trong danh sách trở lại thành các đoạn văn thông thường.