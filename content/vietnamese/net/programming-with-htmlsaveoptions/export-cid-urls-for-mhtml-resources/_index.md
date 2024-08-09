---
title: Xuất Url Cid Cho Tài Nguyên Mhtml
linktitle: Xuất Url Cid Cho Tài Nguyên Mhtml
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách xuất URL Cid cho tài nguyên MHTML bằng Aspose.Words cho .NET trong hướng dẫn từng bước này. Hoàn hảo cho các nhà phát triển ở mọi cấp độ.
type: docs
weight: 10
url: /vi/net/programming-with-htmlsaveoptions/export-cid-urls-for-mhtml-resources/
---
## Giới thiệu

Bạn đã sẵn sàng để nắm vững nghệ thuật xuất URL Cid cho tài nguyên MHTML bằng Aspose.Words cho .NET chưa? Cho dù bạn là nhà phát triển dày dạn kinh nghiệm hay mới bắt đầu, hướng dẫn toàn diện này sẽ hướng dẫn bạn từng bước. Đến cuối bài viết này, bạn sẽ hiểu rõ ràng về cách xử lý hiệu quả tài nguyên MHTML trong tài liệu Word của mình. Hãy đi sâu vào!

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có mọi thứ bạn cần:

-  Aspose.Words cho .NET: Đảm bảo bạn đã cài đặt phiên bản Aspose.Words cho .NET mới nhất. Nếu không, bạn có thể tải nó từ[đây](https://releases.aspose.com/words/net/).
- Môi trường phát triển: Một môi trường phát triển như Visual Studio.
- Kiến thức cơ bản về C#: Mặc dù tôi sẽ hướng dẫn bạn từng bước nhưng hiểu biết cơ bản về C# sẽ có ích.

## Nhập không gian tên

Trước tiên, hãy nhập các không gian tên cần thiết. Bước này tạo tiền đề cho hướng dẫn của chúng tôi:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

Bây giờ, hãy chia quy trình thành các bước đơn giản, dễ quản lý. Mỗi bước sẽ bao gồm một lời giải thích chi tiết để đảm bảo bạn có thể làm theo dễ dàng.

## Bước 1: Thiết lập dự án của bạn

### Bước 1.1: Tạo một dự án mới
Mở Visual Studio và tạo một dự án C# mới. Chọn mẫu Ứng dụng Console để giữ mọi thứ đơn giản.

### Bước 1.2: Thêm Aspose.Words để tham khảo .NET
Để sử dụng Aspose.Words cho .NET, bạn cần thêm tham chiếu vào thư viện Aspose.Words. Bạn có thể thực hiện việc này thông qua Trình quản lý gói NuGet:

1. Nhấp chuột phải vào dự án của bạn trong Solution Explorer.
2. Chọn "Quản lý gói NuGet".
3. Tìm kiếm "Aspose.Words" và cài đặt nó.

## Bước 2: Tải tài liệu Word

### Bước 2.1: Chỉ định thư mục tài liệu
Xác định đường dẫn đến thư mục tài liệu của bạn. Đây là nơi chứa tài liệu Word của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục của bạn.

### Bước 2.2: Tải tài liệu
Tải tài liệu Word của bạn vào dự án.

```csharp
Document doc = new Document(dataDir + "Content-ID.docx");
```

## Bước 3: Định cấu hình tùy chọn lưu HTML

 Tạo một thể hiện của`HtmlSaveOptions` để tùy chỉnh cách lưu tài liệu của bạn dưới dạng MHTML.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
{
    PrettyFormat = true,
    ExportCidUrlsForMhtmlResources = true
};
```

- `SaveFormat.Mhtml` chỉ định rằng định dạng đầu ra là MHTML.
- `PrettyFormat = true` đảm bảo đầu ra được định dạng gọn gàng.
- `ExportCidUrlsForMhtmlResources = true` cho phép xuất URL Cid cho tài nguyên MHTML.

### Bước 4: Lưu tài liệu dưới dạng MHTML

Bước 4.1: Lưu tài liệu
Lưu tài liệu của bạn dưới dạng tệp MHTML bằng cách sử dụng các tùy chọn đã định cấu hình.

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);
```

## Phần kết luận

Chúc mừng! Bạn đã xuất thành công URL Cid cho tài nguyên MHTML bằng Aspose.Words cho .NET. Hướng dẫn này hướng dẫn bạn cách thiết lập dự án, tải tài liệu Word, định cấu hình các tùy chọn lưu HTML và lưu tài liệu dưới dạng MHTML. Bây giờ bạn có thể áp dụng các bước này cho dự án của riêng mình và nâng cao nhiệm vụ quản lý tài liệu của mình.

## Câu hỏi thường gặp

### Mục đích của việc xuất URL Cid cho tài nguyên MHTML là gì?
Xuất URL Cid cho tài nguyên MHTML đảm bảo rằng tài nguyên được nhúng trong tệp MHTML của bạn được tham chiếu chính xác, cải thiện tính di động và tính toàn vẹn của tài liệu.

### Tôi có thể tùy chỉnh thêm định dạng đầu ra không?
 Có, Aspose.Words for .NET cung cấp các tùy chọn tùy chỉnh mở rộng để lưu tài liệu. Tham khảo[tài liệu](https://reference.aspose.com/words/net/) để biết thêm chi tiết.

### Tôi có cần giấy phép để sử dụng Aspose.Words cho .NET không?
 Có, bạn cần có giấy phép để sử dụng Aspose.Words cho .NET. Bạn có thể nhận bản dùng thử miễn phí[đây](https://releases.aspose.com/) hoặc mua giấy phép[đây](https://purchase.aspose.com/buy).

### Tôi có thể tự động hóa quy trình này cho nhiều tài liệu không?
Tuyệt đối! Bạn có thể tạo tập lệnh để tự động hóa quy trình cho nhiều tài liệu, tận dụng sức mạnh của Aspose.Words dành cho .NET để xử lý các hoạt động hàng loạt một cách hiệu quả.

### Tôi có thể nhận hỗ trợ ở đâu nếu gặp vấn đề?
Nếu bạn cần hỗ trợ, hãy truy cập diễn đàn hỗ trợ Aspose[đây](https://forum.aspose.com/c/words/8) để nhận được sự hỗ trợ từ cộng đồng và các nhà phát triển Aspose.