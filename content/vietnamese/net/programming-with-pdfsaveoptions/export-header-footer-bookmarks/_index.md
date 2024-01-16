---
title: Xuất Dấu trang Đầu trang Chân trang Tài liệu Word sang Tài liệu PDF
linktitle: Xuất Dấu trang Đầu trang Chân trang Tài liệu Word sang Tài liệu PDF
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để xuất dấu trang chân trang đầu trang tài liệu word sang dấu trang tài liệu pdf bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

Bài viết này cung cấp hướng dẫn từng bước về cách xuất dấu trang chân trang đầu trang tài liệu word sang tính năng tài liệu pdf bằng Aspose.Words cho .NET. Chúng tôi sẽ giải thích chi tiết từng phần của mã. Khi kết thúc hướng dẫn này, bạn sẽ có thể hiểu cách xuất dấu trang từ đầu trang và chân trang của tài liệu và tạo tệp PDF với các dấu trang thích hợp.

Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt và định cấu hình thư viện Aspose.Words cho .NET trong dự án của mình. Bạn có thể tìm thấy thư viện và hướng dẫn cài đặt trên trang web Aspose.

## Bước 1: Xác định thư mục tài liệu

 Để bắt đầu, bạn cần xác định đường dẫn đến thư mục chứa tài liệu của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải tài liệu lên

Tiếp theo, chúng ta cần tải tài liệu mà chúng ta muốn xử lý. Trong ví dụ này, chúng tôi giả sử tài liệu có tên là "Dấu trang trong đầu trang và chân trang.docx" và nằm trong thư mục tài liệu được chỉ định.

```csharp
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

## Bước 3: Định cấu hình tùy chọn lưu dưới dạng PDF

 Để xuất dấu trang đầu trang và chân trang, chúng ta cần định cấu hình`PdfSaveOptions` sự vật. Trong ví dụ này, chúng tôi đặt mức phác thảo dấu trang mặc định thành 1 và chế độ xuất dấu trang đầu trang và chân trang thành "Đầu tiên".

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

## Bước 4: Lưu tài liệu dưới dạng PDF với dấu trang đầu trang và chân trang

Cuối cùng, chúng ta có thể lưu tài liệu ở định dạng PDF bằng cách sử dụng các tùy chọn lưu đã định cấu hình trước đó.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

Đó là tất cả ! Bạn đã xuất thành công dấu trang đầu trang và chân trang từ tài liệu và tạo tệp PDF có dấu trang thích hợp bằng Aspose.Words cho .NET.

### Mã nguồn mẫu để xuất dấu trang đầu trang và chân trang bằng Aspose.Words cho .NET

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
	saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);

```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã giải thích cách xuất dấu trang đầu trang và chân trang từ tài liệu Word sang tài liệu PDF bằng Aspose.Words cho .NET. Dấu trang đã xuất cho phép điều hướng dễ dàng và tham khảo nhanh đến đầu trang và chân trang tương ứng trong tài liệu PDF được tạo. Thực hiện theo các bước được mô tả để xuất dấu trang đầu trang và chân trang từ tài liệu và tạo tệp PDF có dấu trang thích hợp bằng Aspose.Words cho .NET. Đảm bảo chỉ định đường dẫn chính xác tới tài liệu của bạn và định cấu hình các tùy chọn lưu nếu cần.

### Các câu hỏi thường gặp

### Hỏi: Xuất dấu trang đầu trang và chân trang từ tài liệu Word sang tài liệu PDF là gì?
Trả lời: Xuất dấu trang đầu trang và chân trang từ tài liệu Word sang tài liệu PDF là một tính năng giúp giữ và tạo dấu trang trong tài liệu PDF từ đầu trang và chân trang. chân trang của tài liệu Word gốc. Điều này cho phép người dùng điều hướng nhanh chóng và dễ dàng qua tài liệu PDF bằng cách sử dụng dấu trang tương ứng với đầu trang và chân trang.

### Câu hỏi: Làm cách nào tôi có thể sử dụng Aspose.Words cho .NET để xuất dấu trang đầu trang và chân trang từ tài liệu Word sang tài liệu PDF?
Trả lời: Để xuất dấu trang đầu trang và chân trang từ tài liệu Word sang tài liệu PDF bằng Aspose.Words cho .NET, hãy làm theo các bước sau:

 Đặt đường dẫn thư mục nơi chứa tài liệu của bạn bằng cách thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế của thư mục tài liệu của bạn.

 Tải tài liệu bạn muốn xử lý bằng cách sử dụng`Document` class và chỉ định đường dẫn đến tài liệu Word trong thư mục tài liệu đã chỉ định.

 Định cấu hình tùy chọn lưu dưới dạng PDF bằng cách tạo một phiên bản của`PdfSaveOptions` class và thiết lập các tùy chọn đánh dấu đầu trang và chân trang thích hợp.

 Lưu tài liệu ở định dạng PDF bằng cách sử dụng`Save` phương pháp của`Document` lớp chỉ định đường dẫn và các tùy chọn lưu.

### Câu hỏi: Lợi ích của việc xuất dấu trang đầu trang và chân trang sang tài liệu PDF là gì?
Đáp: Ưu điểm của việc xuất dấu trang đầu trang và chân trang thành tài liệu PDF là:

Điều hướng dễ dàng: Dấu trang cho phép người dùng dễ dàng điều hướng tài liệu PDF bằng cách tham khảo các đầu trang và chân trang cụ thể.

Tham khảo nhanh: Dấu trang cho phép người dùng nhanh chóng tìm thấy các phần có liên quan của tài liệu PDF dựa trên đầu trang và chân trang.