---
title: Đặt thư mục hình ảnh
linktitle: Đặt thư mục hình ảnh
second_title: API xử lý tài liệu Aspose.Words
description: Chuyển đổi tài liệu Word sang Markdown với căn chỉnh bảng thích hợp bằng Aspose.Words for .NET. Thực hiện theo hướng dẫn chi tiết của chúng tôi để có kết quả hoàn hảo.
type: docs
weight: 10
url: /vi/net/programming-with-markdownsaveoptions/set-images-folder/
---
## Giới thiệu

Bạn đã bao giờ muốn xuất tài liệu Word của mình sang định dạng Markdown trong khi vẫn đảm bảo rằng các bảng và nội dung căn chỉnh hoàn hảo chưa? Aspose.Words for .NET là giải pháp phù hợp cho nhiệm vụ này của bạn. Trong bài viết này, chúng tôi sẽ hướng dẫn bạn quy trình thiết lập Aspose.Words, chuẩn bị tài liệu của bạn và xuất nó sang Markdown với căn chỉnh nội dung bảng phù hợp. Chúng tôi sẽ chia nhỏ từng bước để bạn dễ dàng theo dõi và hiểu. Vì vậy, hãy cùng bắt tay vào chuyển đổi tài liệu Word của bạn thành các tệp Markdown được căn chỉnh đẹp mắt!

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có những điều sau:

-  Aspose.Words for .NET: Bạn có thể tải xuống[đây](https://releases.aspose.com/words/net/).
-  Giấy phép hợp lệ: Nhận bản dùng thử miễn phí[đây](https://releases.aspose.com/) hoặc giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).
- Visual Studio: Hoặc bất kỳ IDE nào khác hỗ trợ phát triển .NET.
- Kiến thức cơ bản về C#: Hiểu biết về ngôn ngữ lập trình C#.

## Nhập không gian tên

Để bắt đầu, bạn cần nhập các vùng tên cần thiết vào dự án C# của mình. Những không gian tên này sẽ cho phép bạn truy cập chức năng Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
using System.IO;
```

## Bước 1: Thiết lập dự án của bạn

Trước tiên, hãy thiết lập dự án .NET trong IDE của bạn. Tạo một ứng dụng bảng điều khiển mới và thêm tham chiếu đến Aspose.Words cho .NET.

### 1.1 Tạo một dự án mới

Mở Visual Studio và tạo dự án Ứng dụng Console mới. Đặt tên là "MarkdownExporter" hoặc tên nào đó tương tự.

### 1.2 Thêm tài liệu tham khảo Aspose.Words

 Để thêm Aspose.Words vào dự án của bạn, bạn có thể tải xuống DLL từ[trang web giả định](https://releases.aspose.com/words/net/) và thêm thủ công hoặc sử dụng Trình quản lý gói NuGet:

```bash
Install-Package Aspose.Words
```

## Bước 2: Viết mã để xuất dưới dạng Markdown

Bây giờ, hãy viết mã để đọc tài liệu Word và lưu nó dưới dạng tệp Markdown với căn chỉnh bảng phù hợp.

### 2.1 Xác định đường dẫn đến tài liệu của bạn

Đặt đường dẫn đến tài liệu Word của bạn và thư mục bạn muốn lưu hình ảnh.

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
```

### 2.2 Tải tài liệu

Tải tài liệu Word của bạn bằng Aspose.Words.

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

### 2.3 Định cấu hình tùy chọn lưu đánh dấu

 Cấu hình`MarkdownSaveOptions` để chỉ định nơi lưu trữ hình ảnh.

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
    ImagesFolder = dataDir + "Images"
};
```

### 2.4 Lưu tài liệu dưới dạng Markdown

 Sử dụng một`MemoryStream` để lưu tài liệu ở định dạng Markdown.

```csharp
using (MemoryStream stream = new MemoryStream())
{
    doc.Save(stream, saveOptions);
}
```

## Phần kết luận

Xuất tài liệu Word sang Markdown với căn chỉnh nội dung bảng bằng Aspose.Words dành cho .NET thật đơn giản khi bạn làm theo các bước sau. Với một vài dòng mã, bạn có thể tự động hóa quá trình chuyển đổi và đảm bảo nội dung của bạn được định dạng đúng. Giờ đây, bạn có thể dễ dàng chia sẻ tài liệu của mình ở định dạng Markdown mà biết rằng chúng sẽ trông đẹp mắt và duy trì cấu trúc của chúng.

## Câu hỏi thường gặp

### Tôi có thể sử dụng Aspose.Words cho .NET với các ngôn ngữ lập trình khác không?

Có, Aspose.Words for .NET có thể được sử dụng với bất kỳ ngôn ngữ nào tương thích với .NET như VB.NET, F#, v.v.

### Làm cách nào để có được giấy phép tạm thời cho Aspose.Words?

 Bạn có thể có được giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).

### Tôi có thể chuyển đổi những loại tài liệu nào sang Markdown?

Bạn có thể chuyển đổi nhiều tài liệu Word khác nhau, bao gồm .doc, .docx, .rtf, v.v.

### Có bất kỳ hạn chế nào trong phiên bản dùng thử của Aspose.Words không?

Phiên bản dùng thử có một số hạn chế như hình mờ trong tệp đầu ra. Bạn có thể dùng thử miễn phí[đây](https://releases.aspose.com/).

### Tôi có thể tìm thêm ví dụ và tài liệu về Aspose.Words ở đâu?

 Bạn có thể tìm thấy tài liệu chi tiết và ví dụ trên[trang web giả định](https://reference.aspose.com/words/net/).
