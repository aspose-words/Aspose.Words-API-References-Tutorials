---
title: Chuyển đổi siêu tập tin sang Emf hoặc Wmf
linktitle: Chuyển đổi siêu tập tin sang Emf hoặc Wmf
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để chuyển đổi siêu tệp sang định dạng EMF hoặc WMF khi chuyển đổi tài liệu sang HTML bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---
## Giới thiệu

Chào mừng bạn đến với một bước đi sâu khác vào thế giới của Aspose.Words dành cho .NET. Hôm nay, chúng tôi sẽ giải quyết một mẹo nhỏ: chuyển đổi hình ảnh SVG sang định dạng EMF hoặc WMF trong tài liệu Word của bạn. Điều này nghe có vẻ hơi kỹ thuật nhưng đừng lo lắng. Đến cuối hướng dẫn này, bạn sẽ trở thành chuyên gia về lĩnh vực đó. Cho dù bạn là nhà phát triển dày dạn kinh nghiệm hay mới bắt đầu với Aspose.Words cho .NET, hướng dẫn này sẽ hướng dẫn bạn mọi thứ bạn cần biết, từng bước một.

## Điều kiện tiên quyết

Trước khi đi sâu vào mã, hãy đảm bảo rằng chúng ta đã thiết lập mọi thứ. Đây là những gì bạn cần:

1.  Aspose.Words for .NET Library: Đảm bảo bạn có phiên bản mới nhất. Nếu chưa có, bạn có thể tải xuống từ[đây](https://releases.aspose.com/words/net/).
2. .NET Framework: Đảm bảo bạn đã cài đặt .NET Framework trên máy của mình.
3. Môi trường phát triển: Một IDE như Visual Studio sẽ giúp cuộc sống của bạn dễ dàng hơn.
4. Kiến thức cơ bản về C#: Bạn không cần phải là chuyên gia nhưng hiểu biết cơ bản sẽ giúp ích.

Có mọi thứ? Tuyệt vời! Hãy bắt đầu.

## Nhập không gian tên

Trước tiên, chúng ta cần nhập các không gian tên cần thiết. Điều này rất quan trọng vì nó cho chương trình của chúng ta biết nơi tìm các lớp và phương thức mà chúng ta sẽ sử dụng.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Các không gian tên này bao gồm mọi thứ, từ các chức năng hệ thống cơ bản đến chức năng Aspose.Words cụ thể mà chúng tôi cần cho hướng dẫn này.

## Bước 1: Thiết lập thư mục tài liệu của bạn

Hãy bắt đầu bằng cách xác định đường dẫn đến thư mục tài liệu của bạn. Đây là nơi tài liệu Word của bạn sẽ được lưu sau khi chúng tôi chuyển đổi siêu tệp.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế nơi bạn muốn lưu tài liệu của mình.

## Bước 2: Tạo chuỗi HTML bằng SVG

Tiếp theo, chúng ta cần một chuỗi HTML chứa hình ảnh SVG mà chúng ta muốn chuyển đổi. Đây là một ví dụ đơn giản:

```csharp
string html = 
    @"<html>
        <svg xmlns='http://www.w3.org/2000/svg' width='500' Height='40' viewBox='0 0 500 40'>
            <text x='0' y='35' font-family='Verdana' font-size='35'>Hello world!</text>
        </svg>
    </html>";
```

Đoạn mã HTML này bao gồm một SVG cơ bản có nội dung "Xin chào thế giới!".

## Bước 3: Tải HTML với tùy chọn ConvertSvgToEmf

 Bây giờ, chúng tôi sử dụng`HtmlLoadOptions` để chỉ định cách chúng tôi muốn xử lý hình ảnh SVG trong HTML. Cài đặt`ConvertSvgToEmf` ĐẾN`true` đảm bảo rằng hình ảnh SVG được chuyển đổi sang định dạng EMF.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { ConvertSvgToEmf = true };
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
```

 Đoạn mã này tạo ra một cái mới`Document` đối tượng bằng cách tải chuỗi HTML vào đó với các tùy chọn tải được chỉ định.

## Bước 4: Đặt HtmlSaveOptions cho Định dạng Metafile

 Để lưu tài liệu với định dạng siêu tệp chính xác, chúng tôi sử dụng`HtmlSaveOptions` . Ở đây, chúng tôi thiết lập`MetafileFormat` ĐẾN`HtmlMetafileFormat.Png` , nhưng bạn có thể thay đổi điều này thành`Emf` hoặc`Wmf` tùy thuộc vào nhu cầu của bạn.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Png };
```

## Bước 5: Lưu tài liệu

Cuối cùng, chúng tôi lưu tài liệu bằng các tùy chọn lưu đã chỉ định.

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToPng.html", saveOptions);
```

Thao tác này sẽ lưu tài liệu vào thư mục đã chỉ định với định dạng siêu tệp được chuyển đổi như đã xác định.

## Phần kết luận

Và bạn có nó! Bằng cách làm theo các bước này, bạn đã chuyển đổi thành công hình ảnh SVG sang định dạng EMF hoặc WMF trong tài liệu Word của mình bằng Aspose.Words for .NET. Phương pháp này rất hữu ích để đảm bảo tính tương thích và duy trì tính toàn vẹn trực quan của tài liệu của bạn trên các nền tảng khác nhau. Chúc mừng mã hóa!

## Câu hỏi thường gặp

### Tôi có thể chuyển đổi các định dạng hình ảnh khác bằng phương pháp này không?
Có, bạn có thể chuyển đổi các định dạng hình ảnh khác nhau bằng cách điều chỉnh các tùy chọn tải và lưu cho phù hợp.

### Có cần thiết phải sử dụng phiên bản .NET Framework cụ thể không?
Aspose.Words for .NET hỗ trợ nhiều phiên bản .NET Framework, nhưng bạn nên sử dụng phiên bản mới nhất để có khả năng tương thích và tính năng tốt nhất.

### Ưu điểm của việc chuyển đổi SVG sang EMF hoặc WMF là gì?
Việc chuyển đổi SVG sang EMF hoặc WMF đảm bảo rằng đồ họa vector được giữ nguyên và hiển thị chính xác trong các môi trường có thể không hỗ trợ đầy đủ SVG.

### Tôi có thể tự động hóa quy trình này cho nhiều tài liệu không?
Tuyệt đối! Bạn có thể lặp qua nhiều tệp HTML, áp dụng cùng một quy trình để tự động chuyển đổi để xử lý hàng loạt.

### Tôi có thể tìm thêm tài nguyên và hỗ trợ cho Aspose.Words cho .NET ở đâu?
 Bạn có thể tìm thấy tài liệu toàn diện[đây](https://reference.aspose.com/words/net/) và nhận được sự hỗ trợ từ cộng đồng Aspose[đây](https://forum.aspose.com/c/words/8).