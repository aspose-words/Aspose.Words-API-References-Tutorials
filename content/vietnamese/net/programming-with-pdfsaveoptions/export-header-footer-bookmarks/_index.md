---
title: Xuất Dấu trang Đầu trang Chân trang Tài liệu Word sang Tài liệu PDF
linktitle: Xuất Dấu trang Đầu trang Chân trang Tài liệu Word sang Tài liệu PDF
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách xuất dấu trang đầu trang và chân trang từ tài liệu Word sang PDF bằng Aspose.Words cho .NET với hướng dẫn từng bước của chúng tôi.
type: docs
weight: 10
url: /vi/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---
## Giới thiệu

Chuyển đổi tài liệu Word sang PDF là một công việc thường xuyên, đặc biệt khi bạn muốn chia sẻ hoặc lưu trữ tài liệu mà vẫn giữ nguyên định dạng của chúng. Đôi khi, những tài liệu này chứa các dấu trang quan trọng ở đầu trang và chân trang. Trong hướng dẫn này, chúng ta sẽ tìm hiểu quy trình xuất các dấu trang này từ tài liệu Word sang PDF bằng Aspose.Words cho .NET.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào, hãy đảm bảo bạn có những điều sau:

- Aspose.Words for .NET: Bạn cần cài đặt Aspose.Words for .NET. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/words/net/).
- Môi trường phát triển: Thiết lập môi trường phát triển của bạn. Bạn có thể sử dụng Visual Studio hoặc bất kỳ IDE tương thích .NET nào khác.
- Kiến thức cơ bản về C#: Cần phải làm quen với lập trình C# cùng với các ví dụ về mã.

## Nhập không gian tên

Trước tiên, bạn cần nhập các vùng tên cần thiết vào dự án C# của mình. Thêm những dòng này vào đầu tệp mã của bạn:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Hãy chia nhỏ quy trình thành các bước dễ thực hiện.

## Bước 1: Khởi tạo tài liệu

Bước đầu tiên là tải tài liệu Word của bạn. Đây là cách bạn có thể làm điều đó:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

Trong bước này, bạn chỉ cần chỉ định đường dẫn đến thư mục tài liệu của mình và tải tài liệu Word.

## Bước 2: Định cấu hình tùy chọn lưu PDF

Tiếp theo, bạn cần định cấu hình tùy chọn lưu PDF để đảm bảo rằng dấu trang ở đầu trang và chân trang được xuất chính xác.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

 Ở đây, chúng tôi đang thiết lập`PdfSaveOptions` . các`DefaultBookmarksOutlineLevel` thuộc tính đặt mức phác thảo cho dấu trang và`HeaderFooterBookmarksExportMode` thuộc tính đảm bảo rằng chỉ lần xuất hiện đầu tiên của dấu trang trong đầu trang và chân trang mới được xuất.

## Bước 3: Lưu tài liệu dưới dạng PDF

Cuối cùng, lưu tài liệu của bạn dưới dạng PDF với các tùy chọn đã định cấu hình.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

Ở bước này, bạn sẽ lưu tài liệu vào đường dẫn đã chỉ định với các tùy chọn bạn đã định cấu hình.

## Phần kết luận

Và bạn có nó! Bằng cách làm theo các bước này, bạn có thể dễ dàng xuất dấu trang từ đầu trang và chân trang của tài liệu Word sang PDF bằng Aspose.Words for .NET. Phương pháp này đảm bảo rằng các công cụ hỗ trợ điều hướng quan trọng trong tài liệu của bạn được giữ nguyên ở định dạng PDF, giúp người đọc điều hướng qua tài liệu của bạn dễ dàng hơn.

## Câu hỏi thường gặp

### Tôi có thể xuất tất cả dấu trang từ tài liệu Word sang PDF không?

 Vâng, bạn có thể. trong`PdfSaveOptions`, bạn có thể điều chỉnh cài đặt để bao gồm tất cả dấu trang nếu cần.

### Nếu tôi cũng muốn xuất dấu trang từ nội dung tài liệu thì sao?

 Bạn có thể cấu hình`OutlineOptions` TRONG`PdfSaveOptions` để bao gồm các dấu trang từ nội dung của tài liệu.

### Có thể tùy chỉnh mức độ đánh dấu trong PDF không?

 Tuyệt đối! Bạn có thể tùy chỉnh`DefaultBookmarksOutlineLevel` thuộc tính để đặt các mức phác thảo khác nhau cho dấu trang của bạn.

### Làm cách nào để xử lý tài liệu không có dấu trang?

Nếu tài liệu của bạn không có dấu trang, tệp PDF sẽ được tạo mà không có bất kỳ đường viền dấu trang nào. Đảm bảo tài liệu của bạn chứa dấu trang nếu bạn cần chúng trong PDF.

### Tôi có thể sử dụng phương pháp này cho các loại tài liệu khác như DOCX hoặc RTF không?

Có, Aspose.Words for .NET hỗ trợ nhiều loại tài liệu khác nhau, bao gồm DOCX, RTF và các loại khác.