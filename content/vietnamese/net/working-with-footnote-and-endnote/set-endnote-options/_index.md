---
title: Đặt tùy chọn chú thích cuối
linktitle: Đặt tùy chọn chú thích cuối
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách đặt tùy chọn chú thích cuối trong tài liệu Word bằng Aspose.Words cho .NET với hướng dẫn từng bước toàn diện này.
type: docs
weight: 10
url: /vi/net/working-with-footnote-and-endnote/set-endnote-options/
---
## Giới thiệu

Bạn đang tìm cách cải thiện tài liệu Word của mình bằng cách quản lý hiệu quả các chú thích cuối? Đừng tìm đâu xa! Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình thiết lập các tùy chọn chú thích cuối trong tài liệu Word bằng Aspose.Words cho .NET. Đến cuối hướng dẫn này, bạn sẽ trở thành chuyên gia trong việc tùy chỉnh chú thích cuối để phù hợp với nhu cầu tài liệu của mình.

## Điều kiện tiên quyết

Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

-  Aspose.Words for .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.Words for .NET. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/words/net/).
- Môi trường phát triển: Thiết lập môi trường phát triển, chẳng hạn như Visual Studio.
- Kiến thức cơ bản về C#: Hiểu biết cơ bản về lập trình C# sẽ có ích.

## Nhập không gian tên

Để bắt đầu, bạn cần nhập các không gian tên cần thiết. Các không gian tên này cung cấp quyền truy cập vào các lớp và phương thức cần thiết để thao tác với tài liệu Word.

```csharp
using Aspose.Words;
using Aspose.Words.Notes;
```

## Bước 1: Tải tài liệu

 Trước tiên, hãy tải tài liệu nơi chúng tôi muốn đặt các tùy chọn chú thích cuối. Chúng tôi sẽ sử dụng`Document` class từ thư viện Aspose.Words để thực hiện việc này.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Bước 2: Khởi tạo DocumentBuilder

 Tiếp theo, chúng ta sẽ khởi tạo`DocumentBuilder`lớp học. Lớp này cung cấp một cách đơn giản để thêm nội dung vào tài liệu.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 3: Thêm văn bản và chèn chú thích

 Bây giờ, hãy thêm một số văn bản vào tài liệu và chèn chú thích cuối. các`InsertFootnote` phương pháp của`DocumentBuilder` class cho phép chúng ta thêm chú thích cuối vào tài liệu.

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## Bước 4: Truy cập và đặt tùy chọn Endnote

 Để tùy chỉnh các tùy chọn ghi chú cuối, chúng ta cần truy cập vào`EndnoteOptions` tài sản của`Document` lớp học. Sau đó, chúng ta có thể đặt các tùy chọn khác nhau như quy tắc và vị trí khởi động lại.

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## Bước 5: Lưu tài liệu

 Cuối cùng, hãy lưu tài liệu với các tùy chọn ghi chú được cập nhật. các`Save` phương pháp của`Document` class cho phép chúng ta lưu tài liệu vào thư mục đã chỉ định.

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

## Phần kết luận

Việc đặt tùy chọn chú thích cuối trong tài liệu Word của bạn bằng Aspose.Words cho .NET thật dễ dàng với các bước đơn giản này. Bằng cách tùy chỉnh quy tắc khởi động lại và vị trí của chú thích cuối, bạn có thể điều chỉnh tài liệu của mình để đáp ứng các yêu cầu cụ thể. Với Aspose.Words, khả năng thao tác tài liệu Word nằm trong tầm tay bạn.

## Câu hỏi thường gặp

### Aspose.Words cho .NET là gì?
Aspose.Words for .NET là một thư viện mạnh mẽ để thao tác các tài liệu Word theo chương trình. Nó cho phép các nhà phát triển tạo, sửa đổi và chuyển đổi tài liệu Word ở nhiều định dạng khác nhau.

### Tôi có thể sử dụng Aspose.Words miễn phí không?
 Bạn có thể sử dụng Aspose.Words với bản dùng thử miễn phí. Để sử dụng lâu dài, bạn có thể mua giấy phép từ[đây](https://purchase.aspose.com/buy).

### Chú thích cuối là gì?
Chú thích cuối là tài liệu tham khảo hoặc ghi chú được đặt ở cuối phần hoặc tài liệu. Họ cung cấp thêm thông tin hoặc trích dẫn.

### Làm cách nào để tùy chỉnh hình thức của chú thích cuối?
 Bạn có thể tùy chỉnh các tùy chọn ghi chú cuối như đánh số, vị trí và quy tắc khởi động lại bằng cách sử dụng`EndnoteOptions` lớp trong Aspose.Words cho .NET.

### Tôi có thể tìm thêm tài liệu về Aspose.Words cho .NET ở đâu?
 Tài liệu chi tiết có sẵn trên[Aspose.Words cho tài liệu .NET](https://reference.aspose.com/words/net/) trang.