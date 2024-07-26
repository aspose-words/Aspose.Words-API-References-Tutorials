---
title: Xuất sang Markdown với việc căn chỉnh nội dung bảng
linktitle: Xuất sang Markdown với việc căn chỉnh nội dung bảng
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách xuất tài liệu Word sang Markdown với các bảng được căn chỉnh bằng Aspose.Words cho .NET. Hãy làm theo hướng dẫn từng bước của chúng tôi để có bảng Markdown hoàn hảo.
type: docs
weight: 10
url: /vi/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
## Giới thiệu

Này! Bạn đã bao giờ tự hỏi làm cách nào để xuất tài liệu Word của mình sang định dạng Markdown với các bảng được căn chỉnh hoàn hảo chưa? Cho dù bạn là nhà phát triển làm việc về tài liệu hay chỉ là người yêu thích Markdown thì hướng dẫn này là dành cho bạn. Chúng ta sẽ đi sâu vào chi tiết cách sử dụng Aspose.Words cho .NET để đạt được điều này. Bạn đã sẵn sàng biến các bảng Word của mình thành các bảng Markdown được căn chỉnh gọn gàng chưa? Bắt đầu nào!

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào mã, có một số điều bạn cần phải chuẩn bị sẵn:

1.  Aspose.Words for .NET Library: Đảm bảo bạn có thư viện Aspose.Words for .NET. Bạn có thể tải nó xuống từ[Trang phát hành Aspose](https://releases.aspose.com/words/net/).
2. Môi trường phát triển: Thiết lập môi trường phát triển của bạn. Visual Studio là một lựa chọn phổ biến để phát triển .NET.
3. Kiến thức cơ bản về C#: Hiểu C# là điều cần thiết vì chúng ta sẽ viết mã bằng ngôn ngữ này.
4. Tài liệu Word mẫu: Có một tài liệu Word mà bạn có thể sử dụng để kiểm tra.

## Nhập không gian tên

Trước khi bắt đầu viết mã, hãy nhập các không gian tên cần thiết. Những thứ này sẽ cung cấp cho chúng tôi quyền truy cập vào các lớp và phương thức Aspose.Words mà chúng tôi sẽ sử dụng.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Bước 1: Khởi tạo Document và DocumentBuilder

Trước tiên, chúng ta cần tạo một tài liệu Word mới và khởi tạo một`DocumentBuilder` đối tượng để bắt đầu xây dựng tài liệu của chúng tôi.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Tạo một tài liệu mới.
Document doc = new Document();

// Khởi tạo DocumentBuilder.
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 2: Chèn ô và căn chỉnh nội dung

Tiếp theo, chúng ta sẽ chèn một số ô vào tài liệu của mình và căn chỉnh chúng. Điều này rất quan trọng để đảm bảo rằng quá trình xuất Markdown giữ được sự căn chỉnh chính xác.

```csharp
// Chèn một ô và căn chỉnh sang phải.
builder.InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");

// Chèn một ô khác và căn chỉnh vào giữa.
builder.InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

## Bước 3: Đặt căn chỉnh nội dung bảng để xuất Markdown

 Bây giờ là lúc cấu hình`MarkdownSaveOptions` để kiểm soát việc căn chỉnh nội dung bảng trong tệp Markdown đã xuất. Chúng ta sẽ lưu tài liệu với các cài đặt căn chỉnh khác nhau để xem nó hoạt động như thế nào.

```csharp
// Tạo đối tượng MarkdownSaveOptions.
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
    TableContentAlignment = TableContentAlignment.Left
};

// Lưu tài liệu với căn lề trái.
doc.Save(dataDir + "LeftTableContentAlignment.md", saveOptions);

// Thay đổi căn chỉnh sang phải và lưu.
saveOptions.TableContentAlignment = TableContentAlignment.Right;
doc.Save(dataDir + "RightTableContentAlignment.md", saveOptions);

// Thay đổi căn chỉnh về giữa và lưu lại.
saveOptions.TableContentAlignment = TableContentAlignment.Center;
doc.Save(dataDir + "CenterTableContentAlignment.md", saveOptions);
```

## Bước 4: Sử dụng Căn chỉnh nội dung bảng tự động

 Các`Auto`tùy chọn căn chỉnh lấy căn chỉnh từ đoạn đầu tiên trong cột bảng tương ứng. Điều này có thể hữu ích khi bạn có các cách sắp xếp hỗn hợp trong một bảng.

```csharp
// Đặt căn chỉnh thành Tự động.
saveOptions.TableContentAlignment = TableContentAlignment.Auto;

// Lưu tài liệu với tính năng căn chỉnh tự động.
doc.Save(dataDir + "AutoTableContentAlignment.md", saveOptions);
```

## Phần kết luận

Và bạn có nó rồi đấy! Xuất tài liệu Word sang Markdown với các bảng được căn chỉnh bằng Aspose.Words cho .NET thật dễ dàng khi bạn biết cách thực hiện. Thư viện mạnh mẽ này giúp bạn dễ dàng kiểm soát định dạng và căn chỉnh các bảng, đảm bảo rằng tài liệu Markdown của bạn trông giống như cách bạn muốn. Chúc mừng mã hóa!

## Câu hỏi thường gặp

### Aspose.Words cho .NET là gì?
Aspose.Words for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển tạo, sửa đổi, chuyển đổi và xuất tài liệu Word theo chương trình.

### Tôi có thể đặt các cách sắp xếp khác nhau cho các cột khác nhau trong cùng một bảng không?
 Có, bằng cách sử dụng`Auto` tùy chọn căn chỉnh, bạn có thể có các cách sắp xếp khác nhau dựa trên đoạn đầu tiên trong mỗi cột.

### Tôi có cần giấy phép để sử dụng Aspose.Words cho .NET không?
 Có, Aspose.Words for .NET yêu cầu giấy phép để có đầy đủ chức năng. Bạn có thể nhận được một[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) để đánh giá.

### Có thể xuất các thành phần tài liệu khác sang Markdown bằng Aspose.Words không?
Có, Aspose.Words hỗ trợ xuất nhiều phần tử khác nhau như tiêu đề, danh sách và hình ảnh sang định dạng Markdown.

### Tôi có thể nhận hỗ trợ ở đâu nếu gặp vấn đề?
 Bạn có thể nhận được sự hỗ trợ từ[Diễn đàn hỗ trợ Aspose.Words](https://forum.aspose.com/c/words/8).
