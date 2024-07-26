---
title: Giảm kích thước PDF bằng cách tắt phông chữ nhúng
linktitle: Giảm kích thước PDF bằng cách tắt phông chữ nhúng
second_title: API xử lý tài liệu Aspose.Words
description: Giảm kích thước PDF bằng cách tắt phông chữ được nhúng bằng Aspose.Words for .NET. Hãy làm theo hướng dẫn từng bước của chúng tôi để tối ưu hóa tài liệu của bạn nhằm lưu trữ và chia sẻ hiệu quả.
type: docs
weight: 10
url: /vi/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---
## Giới thiệu

Việc giảm kích thước tệp PDF có thể rất quan trọng để lưu trữ hiệu quả và chia sẻ nhanh chóng. Một cách hiệu quả để thực hiện việc này là tắt các phông chữ được nhúng, đặc biệt khi các phông chữ tiêu chuẩn đã có sẵn trên hầu hết các hệ thống. Trong hướng dẫn này, chúng ta sẽ khám phá cách giảm kích thước PDF bằng cách tắt các phông chữ được nhúng bằng Aspose.Words cho .NET. Chúng tôi sẽ hướng dẫn từng bước để đảm bảo bạn có thể dễ dàng triển khai điều này trong các dự án của riêng mình.

## Điều kiện tiên quyết

Trước khi đi sâu vào mã, hãy đảm bảo bạn có những điều sau:

-  Aspose.Words for .NET: Nếu bạn chưa có, hãy tải xuống và cài đặt nó từ[Liên kết tải xuống](https://releases.aspose.com/words/net/).
- Môi trường phát triển .NET: Visual Studio là một lựa chọn phổ biến.
- Tài liệu Word mẫu: Chuẩn bị sẵn tệp DOCX mà bạn muốn chuyển đổi thành PDF.

## Nhập không gian tên

Để bắt đầu, hãy đảm bảo bạn đã nhập các không gian tên cần thiết vào dự án của mình. Điều này cho phép bạn truy cập các lớp và phương thức cần thiết cho nhiệm vụ của chúng tôi.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Hãy chia nhỏ quy trình thành các bước đơn giản, dễ quản lý. Mỗi bước sẽ hướng dẫn bạn thực hiện nhiệm vụ, đảm bảo bạn hiểu điều gì đang xảy ra ở mọi thời điểm.

## Bước 1: Khởi tạo tài liệu của bạn

Trước tiên, chúng ta cần tải tài liệu Word mà bạn muốn chuyển đổi sang PDF. Đây là nơi cuộc hành trình của bạn bắt đầu.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Đây,`dataDir` là phần giữ chỗ cho thư mục chứa tài liệu của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế.

## Bước 2: Định cấu hình tùy chọn lưu PDF

Tiếp theo, chúng tôi sẽ thiết lập các tùy chọn lưu PDF. Đây là nơi chúng tôi xác định rằng chúng tôi không muốn nhúng phông chữ Windows tiêu chuẩn.

```csharp
// Tệp PDF đầu ra sẽ được lưu mà không cần nhúng phông chữ Windows tiêu chuẩn.
PdfSaveOptions saveOptions = new PdfSaveOptions
{
    FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone
};
```

 Bằng cách thiết lập`FontEmbeddingMode` ĐẾN`EmbedNone`, chúng tôi hướng dẫn Aspose.Words không đưa các phông chữ này vào PDF, làm giảm kích thước tệp.

## Bước 3: Lưu tài liệu dưới dạng PDF

Cuối cùng, chúng tôi lưu tài liệu dưới dạng PDF bằng các tùy chọn lưu đã định cấu hình. Đây là thời điểm thực tế khi DOCX của bạn chuyển đổi thành một bản PDF nhỏ gọn.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thư mục thực tế của bạn một lần nữa. Bây giờ, tệp PDF đầu ra sẽ được lưu trong thư mục được chỉ định mà không cần nhúng phông chữ tiêu chuẩn.

## Phần kết luận

Bằng cách làm theo các bước này, bạn có thể giảm đáng kể kích thước tệp PDF của mình. Tắt phông chữ nhúng là cách đơn giản nhưng hiệu quả để làm cho tài liệu của bạn nhẹ hơn và dễ chia sẻ hơn. Aspose.Words for .NET giúp quá trình này trở nên liền mạch, đảm bảo bạn có thể tối ưu hóa các tệp của mình mà không tốn nhiều công sức.

## Câu hỏi thường gặp

### Tại sao tôi nên tắt phông chữ nhúng trong PDF?
Việc tắt phông chữ nhúng có thể làm giảm đáng kể kích thước tệp PDF, giúp lưu trữ hiệu quả hơn và chia sẻ nhanh hơn.

### Liệu PDF vẫn hiển thị chính xác mà không cần phông chữ nhúng?
Có, miễn là phông chữ là tiêu chuẩn và có sẵn trên hệ thống xem tệp PDF, nó sẽ hiển thị chính xác.

### Tôi có thể chỉ nhúng có chọn lọc một số phông chữ nhất định trong tệp PDF không?
Có, Aspose.Words for .NET cho phép bạn tùy chỉnh phông chữ nào được nhúng, mang lại sự linh hoạt trong cách bạn giảm kích thước tệp.

### Tôi có cần Aspose.Words for .NET để tắt phông chữ nhúng trong tệp PDF không?
Có, Aspose.Words for .NET cung cấp chức năng cần thiết để định cấu hình các tùy chọn nhúng phông chữ trong tệp PDF.

### Làm cách nào để nhận được hỗ trợ nếu tôi gặp sự cố?
 Bạn có thể ghé thăm[Diễn đàn hỗ trợ](https://forum.aspose.com/c/words/8) để được hỗ trợ về mọi vấn đề bạn gặp phải.
