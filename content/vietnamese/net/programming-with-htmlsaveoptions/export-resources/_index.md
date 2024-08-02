---
title: Xuất khẩu tài nguyên
linktitle: Xuất khẩu tài nguyên
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách xuất các tài nguyên như CSS và phông chữ trong khi lưu tài liệu Word dưới dạng HTML bằng Aspose.Words cho .NET. Thực hiện theo hướng dẫn từng bước của chúng tôi.
type: docs
weight: 10
url: /vi/net/programming-with-htmlsaveoptions/export-resources/
---
## Giới thiệu

Này, anh bạn đam mê công nghệ! Nếu bạn từng thấy mình cần chuyển đổi tài liệu Word sang HTML thì bạn đã đến đúng nơi. Hôm nay, chúng ta sẽ đi sâu vào thế giới tuyệt vời của Aspose.Words dành cho .NET. Thư viện mạnh mẽ này giúp bạn dễ dàng làm việc với các tài liệu Word theo chương trình. Trong hướng dẫn này, chúng ta sẽ thực hiện các bước để xuất tài nguyên, chẳng hạn như phông chữ và CSS, khi lưu tài liệu Word dưới dạng HTML bằng Aspose.Words cho .NET. Chuẩn bị sẵn sàng để có một chuyến đi vui vẻ và đầy thông tin!

## Điều kiện tiên quyết

Trước khi đi sâu vào mã, hãy đảm bảo bạn có mọi thứ cần thiết để bắt đầu. Dưới đây là danh sách kiểm tra nhanh:

1.  Visual Studio: Đảm bảo bạn đã cài đặt Visual Studio trên máy của mình. Bạn có thể tải nó xuống từ[Trang web Visual Studio](https://visualstudio.microsoft.com/).
2.  Aspose.Words for .NET: Bạn sẽ cần thư viện Aspose.Words for .NET. Nếu bạn chưa có, hãy lấy bản dùng thử miễn phí từ[Giả định phát hành](https://releases.aspose.com/words/net/) hoặc mua nó từ[Cửa hàngApose Store](https://purchase.aspose.com/buy).
3. Kiến thức cơ bản về C#: Hiểu biết cơ bản về C# sẽ giúp bạn theo dõi các ví dụ về mã.

Có tất cả những thứ đó? Tuyệt vời! Hãy chuyển sang nhập các không gian tên cần thiết.

## Nhập không gian tên

Để sử dụng Aspose.Words cho .NET, bạn cần đưa các không gian tên có liên quan vào dự án của mình. Đây là cách bạn làm điều đó:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Các không gian tên này rất quan trọng để truy cập các lớp và phương thức Aspose.Words mà chúng ta sẽ sử dụng trong hướng dẫn của mình.

Hãy chia nhỏ quy trình xuất tài nguyên khi lưu tài liệu Word dưới dạng HTML. Chúng tôi sẽ thực hiện từng bước một để bạn dễ dàng theo dõi.

## Bước 1: Thiết lập thư mục tài liệu của bạn

Trước tiên, bạn cần chỉ định đường dẫn đến thư mục tài liệu của mình. Đây là nơi đặt tài liệu Word của bạn và nơi lưu tệp HTML.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục của bạn.

## Bước 2: Tải tài liệu Word

 Tiếp theo, hãy tải tài liệu Word bạn muốn chuyển đổi sang HTML. Đối với hướng dẫn này, chúng tôi sẽ sử dụng một tài liệu có tên`Rendering.docx`.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

Dòng mã này tải tài liệu từ thư mục được chỉ định.

## Bước 3: Định cấu hình tùy chọn lưu HTML

Để xuất các tài nguyên như CSS và phông chữ, bạn cần định cấu hình`HtmlSaveOptions`. Bước này rất quan trọng để đảm bảo đầu ra HTML của bạn có cấu trúc tốt và bao gồm các tài nguyên cần thiết.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    CssStyleSheetType = CssStyleSheetType.External,
    ExportFontResources = true,
    ResourceFolder = dataDir + "Resources",
    ResourceFolderAlias = "http://example.com/resource"
};
```

Hãy chia nhỏ chức năng của từng tùy chọn:
- `CssStyleSheetType = CssStyleSheetType.External`: Tùy chọn này chỉ định rằng các kiểu CSS sẽ được lưu trong biểu định kiểu bên ngoài.
- `ExportFontResources = true`: Điều này cho phép xuất tài nguyên phông chữ.
- `ResourceFolder = dataDir + "Resources"`: Chỉ định thư mục cục bộ nơi các tài nguyên (như phông chữ và tệp CSS) sẽ được lưu.
- `ResourceFolderAlias = "http://example.com/resources"`: Đặt bí danh cho thư mục tài nguyên sẽ được sử dụng trong tệp HTML.

## Bước 4: Lưu tài liệu dưới dạng HTML

Với các tùy chọn lưu được định cấu hình, bước cuối cùng là lưu tài liệu dưới dạng tệp HTML. Đây là cách bạn làm điều đó:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

Dòng mã này lưu tài liệu ở định dạng HTML, cùng với các tài nguyên đã xuất.

## Phần kết luận

Và bạn có nó rồi đấy! Bạn đã xuất thành công tài nguyên trong khi lưu tài liệu Word dưới dạng HTML bằng Aspose.Words cho .NET. Với thư viện mạnh mẽ này, việc xử lý tài liệu Word theo chương trình trở nên dễ dàng. Cho dù bạn đang làm việc trên một ứng dụng web hay chỉ cần chuyển đổi tài liệu để sử dụng ngoại tuyến, Aspose.Words đều có thể giúp bạn.

## Câu hỏi thường gặp

### Tôi có thể xuất hình ảnh cùng với phông chữ và CSS không?
 Vâng, bạn có thể! Aspose.Words for .NET cũng hỗ trợ xuất hình ảnh. Chỉ cần đảm bảo cấu hình`HtmlSaveOptions` tương ứng.

### Có cách nào để nhúng CSS thay vì sử dụng biểu định kiểu bên ngoài không?
 Tuyệt đối. Bạn có thể thiết lập`CssStyleSheetType` ĐẾN`CssStyleSheetType.Embedded` nếu bạn thích kiểu nhúng.

### Làm cách nào tôi có thể tùy chỉnh tên tệp HTML đầu ra?
 Bạn có thể chỉ định bất kỳ tên tập tin nào bạn thích trong`doc.Save` phương pháp. Ví dụ,`doc.Save(dataDir + "CustomFileName.html", saveOptions);`.

### Aspose.Words có hỗ trợ các định dạng khác ngoài HTML không?
 Có, nó hỗ trợ nhiều định dạng khác nhau bao gồm PDF, DOCX, TXT, v.v. Kiểm tra[tài liệu](https://reference.aspose.com/words/net/) để có danh sách đầy đủ.

### Tôi có thể nhận thêm hỗ trợ và nguồn lực ở đâu?
Để được trợ giúp thêm, hãy truy cập[Diễn đàn hỗ trợ Aspose.Words](https://forum.aspose.com/c/words/8) . Bạn cũng có thể tìm thấy tài liệu chi tiết và ví dụ trên[trang web giả định](https://reference.aspose.com/words/net/).